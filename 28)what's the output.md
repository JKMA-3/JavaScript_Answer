# 28. What's the output?

```javascript
String.prototype.giveLydiaPizza = () => {
  return "Just give Lydia pizza already!";
};

const name = "Lydia";

name.giveLydiaPizza();
```

1. "Just give Lydia pizza already!"
2. TypeError: not a function
3. SyntaxError
4. undefined

# 요약

1. "Just give Lydia pizza already!"<br>
   표준 빌트인 객체인 String의 프로토타입에 메서드를 선언하였다. string타입 변수(name)를 선언 후 변수를 마침표 표기법으로 접근 시 래퍼 객체가 생성되어 표준 빌트인 객체의 프로토타입이 상속된다. 따라서 프로토타입 선언된 메서드 giveLydiaPizza()를 사용 가능하다.

# 표준 빌트인 객체

40여개의 표준 빌트인 객체가 있으며 이 중 Math, Reflect, Json을 제외한 표준 빌트인 객체는 인스턴스를 생성하는 생성자 함수 객체이며 프로토타입 메서드와 정적 메서드를 제공한다. 생성자 함수 표준 빌트인 객체가 생성한 인스턴스의 프로토타입은 표준 빌트인 객체의 prototype 프로퍼티에 바인딩된 객체이다.

## 래퍼 객체

래퍼 객체란 String, Number, Boolean 값을 객체처럼 접근 시 생성되는 임시 객체를 말한다.

1. 래퍼 객체 생성 시 값은 래퍼 객체의 내부 슬롯에 저장된다.
2. 이 때 생성된 래퍼 객체는 표준 빌트인 객체의 prototype 메서드를 상속받아 사용 가능하다.
3. 래퍼 객체의 처리가 종료되면 내부 슬롯에 저장된 원시 값으로 되돌리고 래퍼 객체는 가비지콜렉터의 대상이되어 삭제된다.
