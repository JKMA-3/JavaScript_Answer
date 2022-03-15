# 6. What's the output

```javascript
let c = { greeting: "Hey!" };
let d;

d = c;
c.greeting = "Hello";
console.log(d.greeting);
```

1.  <code>Hello</code>
2.  <code>Hey!</code>
3.  <code>undefined</code>
4.  <code>ReferenceError</code>
5.  <code>TypeError</code>

# 요약

1. <code>Hello</code><br>
   자바스크립트 엔진은 mouse.bird를 먼저 평가한다. 하지만 mouse란 객체에는 bird라는 키는 없기 때문에 undefined가 반환한 후 undefined.bird를 탐색하기 때문<code>Cannot read properties of undefined (reading 'size')</code>를 발생한다.<br/>
   <code>mouse.bird = undefined -> undefined.size = Error 발생</code>

# 원시 값(변경 불가능한 값)

원시값이 변수에 할당하면 변수에는 실제 값이 저장된다. 원시 값은 변경이 불가능한 값이지만 변수에 할당된 값은 재할당으로 변경이 가능하다.

## 값에 의한 전달(Call by Value)

```javascript
var number = 30;
var copy; = score;

console.log(number, copy); //30 30
console.log(number === copy); //true

number = 100;

console.log(number, copy); //100 30
console.log(number === copy); //false
```

number 변수에 원시 값 30을 할당한 후 이를 copy변수에 복사하면 원시 값을 복사하여 샤로운 원시 값 30을 할당한다. number, copy 변수에 할당된 값은 서로 같다.<br>
하지만 이는 서로 별개의 값이기 때문에 하나의 값을 바꾼다고 하여도 서로에게 영향을 주지 않는다. 따라서 number 변수의 값을 100으로 재할당하여도 copy의 값은 그대로 30을 유지한다.

---

ECMAScript에는 변수를 통해 메모리를 어떻게 관리하는지 명확하게 정의되어 있지 않으며 실제 자바스크립트 엔진을 구현하는 제조사에 따라 실제 내부 동작에는 미묘한 차이가 있다.

---

# 객체(참조)타입의 값(변경 가능한 값)

참조 타입의 값을 변수에 할당하면 변수에는 실제 값이 아닌 값이 저장된 메모리의 참조 값이 저장된다. 할당된 메모리 주소을 통해 메모리 공간에 접근하면 값이 저장되어 있는 메모리 공간 그 자체인 참조 값에 접근이 가능하다. 참조 타입의 값은 원시 값과 달리 변경 가능한 값이기 때문에 메모리에 저장된 값을 직접 수정 가능하며 재할당이 아니기 때문에 참조 값도 바뀌지 않는다.

## 참조에 의한 전달(Call by Reference)

참조에 의한 전달은 값을 복사하는 것이 아닌 참조 값을 복사한다. 참조 값을 복사한다는 말은 복수의 변수가 하나의 객체를 공유한다는 의미로 한 쪽에서 값 변경한다면 다른 변수에도 영향이 간다.

```javascript
var number = {
  one: "1",
};

var copy = number;
console.log(number === copy); //true

copy.one = "one";
copy.two = "Two";

console.log(copy);
console.log(number);
console.log(copy === number); //true
```

## 참조에 의한 전달? 값에 의한 전달?

두 가지 전달 방법은 식별자에 저장된 값을 복사한다는 점이 동일하다. 다만 그 값이 참조 값이냐 원시 값이냐의 차이이다. 따라서 <code>자바스크립트 내에는 값에 의한 전달만 있다고 할 수 있다.</code><br>
