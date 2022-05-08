# 66. With which constructor can we successfully extend the Dog class?

```javascript
class Dog {
  constructor(name) {
    this.name = name;
  }
};

class Labrador extends Dog {
  // 1
  constructor(name, size) {
    this.size = size;
  }
  // 2
  constructor(name, size) {
    super(name);
    this.size = size;
  }
  // 3
  constructor(size) {
    super(name);
    this.size = size;
  }
  // 4
  constructor(name, size) {
    this.name = name;
    this.size = size;
  }

};
```

1. 1
2. 2
3. 3
4. 4

# 요약

2. 2<br>
   extend는 class를 상속하는 문법으로 super()는 부모의 생성자(constructor)를 호출하는 함수이다. 부모 class인 Dog의 생성자(constructor)는 name이라는 매개변수를 받으며 자식 class인 Labrador의 생성자(constructor)는 size를 매개변수로 받는다. 따라서 super()의 매개변수에는 name을 전달해야하며 size는 Labrador의 생성자(constructor)에서 초기화해야한다.
