# 1. What is output

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
}

sayHi();
```

1. <code>0 1 2</code> and <code>0 1 2</code>
2. <code>0 1 2</code> and <code>3 3 3</code>
3. <code>3 3 3</code> and <code>0 1 2</code>

# 요약

<code>var</code>키워드는 <code>함수 레벨 스코프</code>로 코드 블록인 for문에서 선언하여도 전역 변수로 생성되어 setTImeout()함수로 인한 지연된 시간동안 <code>전역변수 i=3</code>이 되기 때문에 <code>3 3 3</code>이 출력

<code>let</code>키워드는 <code>블록 레벨 스코프</code>로 for문 내에 지역 변수로 생성되며 반복될 때 마다 클로저로 인하여 정적환경이 저장되어 setTimeout()로 인하여 시간이 지연되어도 각각의 <code>정적환경에 저장된 i의 값</code>이 출력

# 스코프

변수, 함수, 클래스에 접근 가능한 범위

## var과 let,const의 차이

<code>var</code>키워드는 <code>함수 레벨 스코프</code>

<details>
<summary>함수 레벨 스코프</summary>
<div markdown="1">

함수 레벨 스코프란 var 변수 선언 및 함수 선언문으로 함수 선언 시 함수만을 지역 스코프로 인정하기 때문에 함수 내부에서 선언된 변수만 지역변수 이며 함수 외부에서 선언된 변수는 전역 변수로 선언되는 방식

```javascript
if (true) {
  var scope = `Window`;
}
function foo() {
  var scope = `Local`;
  console.log(scope); //Local
}
foo();
console.log(scope); //Window
```
  위의 코드를 실행 하면 if문이라는 블록내에서 선언한 var변수는 전역 변수로 선언되며
   ![Block내 var 변수 선언 = 전역변수 선언](https://user-images.githubusercontent.com/67920695/158004539-b74b35c1-b1c2-490b-a696-24362410361c.png)
  foo()라는 함수내에서 선언한 변수는 지역변수가 되는 것을 확인할 수 있다.
   ![Function 내 var 변수 선언 = 지역 변수 선언](https://user-images.githubusercontent.com/67920695/158004614-81c71736-c6e2-434b-8b1c-6b93040222fe.png)
  ![코드 실행 결과](https://user-images.githubusercontent.com/67920695/158005117-f3a80499-76f9-4a6c-8662-d04a63b443d8.png)
  코드실행결과
</div>
</details>
<code>let, const</code>키워드는 <code>블록 레벨 스코프</code>
<details>
<summary>블록레벨 스코프</summary>
<div markdown="2">

모든 코드블록(함수, if, for, try/catch)을 지역 스코프로 인정하여 코드 블록 내부에서 선언된 변수는 지역 변수로 외부에서는 참조가 불가능한 방식

```javascript
if (true) {
  let scope = `Local(Block)`;
  console.log(scope); //Local(Block)
}
function foo() {
  let scope_2 = `Local(Function)`;
  console.log(`scope_2`); //Local(Function)
}
foo();
console.log(scope); //Uncaught ReferenceError: scope is not defined
```
위의 코드 실행 시 let으로 선언한 변수는 블록 레벨 스코프이기 때문에 if(), function에 각각 지역변수가 생성된다.
![Block내 let 변수 선언 = 전역변수 선언](https://user-images.githubusercontent.com/67920695/158021558-56da33b7-78cf-41b5-8c93-ca9721e24549.png)
![Function 내 var 변수 선언 = 지역 변수 선언](https://user-images.githubusercontent.com/67920695/158021560-3a72ab76-67ad-4f7f-8dcf-1209fe22f8c5.png)
따라서 코드실행 결과 if()문 에서 "Local(Block)"이 출력되며 function foo()내에서는 "Local(Function)"가 출력된다. 또한 전역에서는 선언된 변수가 없기 때문에 오류가 발생한다. 
![let코드 실행 결과](https://user-images.githubusercontent.com/67920695/158021328-41dd8914-97dc-448a-a349-5f4816bf9183.png)
  
</div>
</details>

# 클로저

함수가 선언 시 생성되는 정적 환경(변수 및 상위 스코프)을 저장하여 외부에서 접근 가능한 함수

```javascript
const color = "red";
function foo() {
  const color = "blue"; 
  function bar() {
    console.log(color); 
  }
  return bar;
}
var baz = foo(); 
baz(); 
```

Global Execution Context를 생성되며 foo()함수의 [[Environment]]내에 Global Lexical Environment가 저장된다.
![1.Global Exe.Cont생성](https://user-images.githubusercontent.com/67920695/158022820-be5fb572-038a-4652-b147-7fc9a3caa25c.png)
전역 스코프에 foo()가 정의되며 bar() 함수의 [[Environment]]내에 foo()의 Lexical Environment가 저장된다.
![2.foo.Exe.Cont 생성](https://user-images.githubusercontent.com/67920695/158022822-3608d9c3-e483-45fa-baa3-fb7ea5c5e897.png)
전역 변수 baz에 중첩함수인 bar()가 저장되며 foo()함수가 실행 컨텍스트에서 제거되지만 bar()의 [[Environment]]내에 저장된 Lexical Environment는 삭제되지 않는다.
![3.변수내 저장](https://user-images.githubusercontent.com/67920695/158022825-e47f5927-8bc0-4cf6-9a7a-b1eac5fce772.png)
baz() 호출 시 bar() 내에 'color'라는 변수가 없기 때문에 bar()의 [[Environment]]에 저장되어 있는 foo의 Lexical Environment에서 'color'를 찾아 출력한다
![4.bar실행](https://user-images.githubusercontent.com/67920695/158022827-40924acb-0942-4d44-b45d-66926997148b.png)

# 정적 환경(Lexical Environment)

실행 컨텍스트에서 식별자(함수, 변수)와 상위 스코프를 저장하는 자료구조로서 식별자를 관리하는 환경 레코드(Environment Record)와 상위 스코프를 저장하는 외부 렉시컬 환경에 대한 참조(Outer)로 구성되어 있다.
