# 16. What's the output

```javascript
function checkAge(data) {
  console.log(data);
  if (data === { age: 18 }) {
    console.log("You are an adult!");
  } else if (data == { age: 18 }) {
    console.log("You are still an adult.");
  } else {
    console.log(`Hmm.. You don't have an age I guess`);
  }
}

checkAge({ age: 18 });
```

1. You are an adult!
2. You are still an adult.
3. Hmm.. You don't have an age I guess

# 요약

3. Hmm.. You don't have an age I guess<br>
   객체 {age:18}이 data에 저장되어 '===' 혹은 '==' 연산자로 {age:18}을 비교한다. 허자먼 갹채끼리 비교하는 것은 참조 값이기 때문에 같은 프로퍼티 값이 저장되어도 다른 메모리 주소에 저장되어 있기 때문에 false를 반환한다. 따라서 Hmm.. You don't have an age I guess를 출력한다.

# 객체와 원시 값의 비교

## 원시 값의 비교

원시 값의 비교는 저장되어 있는 원시 값을 비교하기 때문에 같은 값을 비교하는 경우 '=='연산자는 true를 반환한다.

## 객체의 비교

객체는 2개의 객체 내 프로퍼티 값이 같아도 비교하는 것은 참조값(변수의 메모리 공간에 저장되는 객체가 저장된 메모리 주소)이기 때문에 서로 다른 메모리 주소에 저장된 객체를 동등연산자로 비교할 경우, false를 반환한다.
