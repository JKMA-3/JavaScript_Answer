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
  <figure text-align="center">
    <img src="https://user-images.githubusercontent.com/67920695/158004539-b74b35c1-b1c2-490b-a696-24362410361c.png"/>
    <figcaption>Block 내 var 변수 션언 = 전역 변수 선언</figcaption>
    <br/><br/>
    <img src="https://user-images.githubusercontent.com/67920695/158004614-81c71736-c6e2-434b-8b1c-6b93040222fe.png"/>
    <figcaption>Function 내 var 변수 선언 = 지역 변수 선언</figcaption>
  </figure>
  
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

</div>
</details>

# 클로저

함수가 선언 시 생성되는 정적 환경(변수 및 상위 스코프)을 저장하여 외부에서 접근 가능한 함수

```javascript
var color = "red";
function foo() {
  var color = "blue"; // 2
  function bar() {
    console.log(color); // 1
  }
  return bar;
}
var baz = foo(); // 3
baz(); // 4
```

<code>bar()</code> 선언 시 outer에 foo의 Environment가 저장된다.
baz() 호출 시 bar() 내에 'color'라는 변수가 없기 때문에 outer Environment에 저장되어 있는 foo의 정적환경에서 'color'를 찾아 출력한다.

# 정적 환경(Lexical Environment)

실행 컨텍스트에서 식별자(함수, 변수)와 상위 스코프를 저장하는 자료구조로서 식별자를 관리하는 환경 레코드(Environment Record)와 상위 스코프를 저장하는 외부 렉시컬 환경에 대한 참조(Outer)로 구성되어 있다.
