# 7. What's the output

```javascript
class Chameleon {
  static colorChange(newColor) {
    this.newColor = newColor;
    return this.newColor;
  }

  constructor({ newColor = "green" } = {}) {
    this.newColor = newColor;
  }
}

const freddie = new Chameleon({ newColor: "purple" });
console.log(freddie.colorChange("orange"));
```

1.  <code>Orange</code>
2.  <code>Green</code>
3.  <code>Purple</code>
4.  <code>Type error</code>

# 요약

# Prototype

## 필요한 이유

객체지향 언어는 <code>상속</code>(객체의 프로퍼티 혹은 메서드를 다른 객체에서 사용하는 특징)을 통하여 불필요한 중복을 제거하며 <code>자바스크립트는 프로토타입을 사용하여 상속을 구현한다.</code>
<br><br>

## \_ _ prototype _ \_

[[prototype]] 내부 슬롯에 간접 접근할 수 있는 접근자 프로퍼티로[[Get]], [[Set]]으로 이루어진다. \_ _ prototype _ \_는 객체가 소유한 프로퍼티가 아닌 Object.prototype의 프로토타입으로 상속을 통하여 객체가 사용 가능하다.
<br>

### 어째서 접근자 프로퍼티를 사용할까?

상호 참조로 인하여 프로토타입 체인이 단방향이 아닌 순환참조가 되어 프로토타입 체인으로 프로퍼티를 탐색하는 경우 종점이 없어 무한 루프에 빠지기 때문에 접근자 프로퍼티를 이용하여 접근한다.
<br><br>

## 함수객체 프로토타입 프로퍼티

함수객체만 가지고 있는 프로토타입 프로퍼티는 생성자 함수가 생성 할 객체의 프로토타입을 가리킨다. 하지만 non-constructor 함수인 화살표 함수 축약표현으로 정의한 메서드는 프로토타입과 프로토타입 프로퍼티를 소유하지 않는다.
<br>

## \_ _prototype _ \_ == 프로토타입 프로퍼티??

모든 객체가 소유하는 \_ _prototype _ \_과 함수 객체만이 가지고 있는 프로토타입 프로퍼티는 같은 프로토타입을 가리킨다. 하지만 이를 사용하는 주체와 사용하는 목적이 다르다.
|구분|소유|주체|목적|
|:---:|:---:|:---:|:---:|
|\_ _ prototype _ \_| 모든 객체 |모든 객체 | 자신의 프로토타입에 접근 및 설정을 위하여 |
| 프로토타입 프로퍼티 | 함수 객체 | 함수 객체 | 생성 할 객체의 프로토타입을 할당하기 위하여|
<br><br>

## 프로토타입의 constructor

모든 프로토타입은 constructor 프로퍼티를 가지고 있다. 이는 <code>함수 객체가 생성될 시 생성되며 프로토타입 프로퍼티로 자신을 참조하고 있는 생성자 함수를 가리킨다. 또한 생성자 함수로 생성한 객체의 프로토타입은 생성자함수의 프로토타입을 상속받는다.</code>

## 리터럴표기법으로 생성한 객체

리터럴 표기법과 같이 생성자 함수를 호출하여 객체를 생성하지 않는 객체 생성 방식 리터럴 표기법으로 생성된 객체도 상속을 위한 프로토타입이 필요하기 때문에 추상연산을 호출하여 각각의 프로토타입을 가진 객체를 생성한다.
|리터럴표기법|생성자 함수|프로토타입|
|:---:|:---:|:---:|
|객체 리터럴|Object|Object.prottype|
|함수 리터럴|Function|Function.prottype|
|배열 리터럴|Array|Array.prottype|
|정규 표현식 리터럴|RegExp|RegExp.prottype|

<code>**프로토타입은 생성자 함수와 항상 쌍으로 존재하기 때문에 생성자 함수가 생성되는 시점에 프로토타입도 동시에 생성된다.**

- 생성자 함수:생성자 함수 정의가 평가되어 함수 객체를 생성하는 시점
- 빌트인 생성자 함수(Object, String, Number ...):전역객체가 생성되는 시점에 생성<br>
  이 후 객체 생성 시 프로토타입은 객체의 내부 슬롯([[prototype]])에 할당</code>
  <br><br>

# Class

# Static
