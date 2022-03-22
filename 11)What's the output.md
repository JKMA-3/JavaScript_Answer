# 10. What happens when we do this?

```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}

const member = new Person("Lydia", "Hallie");
Person.getFullName = function () {
  return `${this.firstName} ${this.lastName}`;
};

console.log(member.getFullName());
```

1. TypeError
2. SyntaxError
3. Lydia Hallie
4. undefined undefined

# 요약

1. TypeError
   함수이자 객체인 Person()이 선언되고 변수 member내에 new연산자를 사용하여 새로운 객체를 생성하였다. 후에 Person객체에 getFullName이라는 메서드를 추가한 후에 member.getFullName()을 호출하였다. 이 때 <code>getFullName()이라는 메서드는 객체 member가 아닌 Person()객체 내에 선언하였기에 member.getFullName()은 호출할 수 없다.</code>

   ```javascript
   member.getFullName으로 선언하여 member내에서만 호출이 가능하거나 Person.prototype.getFullName()으로 선언하여 Person 생성자 함수로 선언한 객체는 사용가능하도록 선언해야 한다.
   ```
