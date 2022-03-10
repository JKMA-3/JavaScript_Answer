# 3. What is output

```javascript
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

1. <code>20</code> and <code>62.83185307179586</code>
2. <code>20</code> and <code>NaN</code>
3. <code>20</code> and <code>63</code>
4. <code>NaN</code> and <code>63</code>

# 요약

# this키워드

자신이 속한 객체 혹은 생성할 인스턴스를 가리키는 자기 참조 변수로 프로퍼티, 메서드를 참조 가능하다 this키워드가 바인딩하는 대상은 동적(호출되는 시점)으로 결정된다.

## this 키워드가 가리키는 대상

### 일반 함수 호출

일반 함수로 호출 시 <code>전역 객체</code>가 바인딩된다. strict mode가 적용된 일반 함수의 this는 undefined가 바인딩된다.

```javascript
function(){
  console.dir(this);
}
foo() // window

function zoo(){
  'strict mode';
  console.log(this);
}
zoo(); //undefined
```

### 메서드 호출

<code>메서드를 호출한 객체(마침표' . '연산자 앞에 기술한 객체)</code>가 바인딩된다.

```javascript
const person = {
  name: "lee",
  getName() {
    return this.name;
  },
};
console.log(person.getName()); // lee
```

### 생성자 함수 호출

생성자 함수로 <code>생성할 인스턴스</code>에 바인딩된다.

```javascript
function Circle(radius) {
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

const circle = new Circle(5);

console.log(circle.getDiameter()); //10
```

### prototype.apply/call/bind에 의한 간접 호출

apply, call, bind는 function.prototype의 메서드이다. 모든 함수는 사용 가능하며 this바인딩은 첫번째 인수로 전달한 객체가 된다.

# 화살표 함수

function키워드 대신 =>를 사용하여 함수 정의를 간략화 되었으며 콜백함수 내부 this가 전역 객체를 가리키는 문제를 해결하기 위한 대응방안으로 유명하다.

```javascript
const foo = (x, y) => x + y;
foo(3, 5); //8
```

## 일반함수와 차이

### 인스턴스 생성 불가능

생성자 함수로서 호출이 불가능하다.

```javascript
const Foo = () => {};
new Foo(); //Type Error
```

### 중복 매개변수 선언 불가능

중복된 매개변수 선언 시 오류 발생

```javascript
const arrow = (a, a) => a + a; //Syntax Error
```

### this, argument, super, new.target 바인딩X

this, argument, super, new.target 참조 시 스코프 체인으로 상위 스코프의 this, argument, super, new.target을 참조

>     화살표 함수는 함수 자체의 this바인딩이 없기 때문에 상위 this를 참조한는 lexical this
