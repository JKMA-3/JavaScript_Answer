# 10. What happens when we do this?

```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

const lydia = new Person("Lydia", "Hallie");
const sarah = Person("Sarah", "Smith");

console.log(lydia);
console.log(sarah);
```

1. Person {firstName: "Lydia", lastName: "Hallie"} and undefined
2. Person {firstName: "Lydia", lastName: "Hallie"} and Person {firstName: "Sarah", lastName: "Smith"}
3. Person {firstName: "Lydia", lastName: "Hallie"} and {}
4. Person {firstName: "Lydia", lastName: "Hallie"} and ReferenceError

# 요약

1. Person {firstName: "Lydia", lastName: "Hallie"} and undefined
   <br/>
   함수 Person을 생성자 함수로 호출한 lydia -> this는 생성할 인스턴스 즉, lydia를 가리키며 변수 lydia 내의 firstname, lastname에 생성된다.
   함수 Person을 일반 함수로 호출한 Sarah -> this는 전역객체를 가리키며 window.fistname, window.lastname에 생성된다.
   console.log로 출력 시 lydia는 Lydia, Halie가 출력되며 sarah는 전역 객체에 생성되었기 때문에 undefined가 출력된다.

# [[call]], [[constructor]]

함수는 객체가 가지고 있는 내부 슬롯 [[Environment]], [[Formal Parameters]]와 함수가 가지고 있는 내부 메서드 [[call]]. [[constructor]]를 가지고 있다. 함수가 일반 함수로 호출되는 경우 [[call]]이 호출되며 new연산자와 함께 생성자 함수로 호출될 경우 [[constructor]]이 호출된다.
함수는 호출하기 위한 [[call]]을 항상 가지고 있지만 생성자 함수로 호출 가능한 [[constructor]](함수 선언문, 함수 표현식, 쿨래스)와 생성자 함수로 호출이 불가능한 [[non-constructor]](화살표 함수, ES6축약표현)등으로 나누어진다.

# new 연산자

new연산자와 함께 함수를 호출 시 생성자 함수로 호출 가능하다. new연산자 없이 호출 시 일반 함수([[call]])로 호출되며 new연산자와 함께 호출 시 생성자 함수([[constructor]])로 호출된다.
