# 9. What's the output

```javascript
let greeting;
greetign = {}; // Typo!
console.log(greetign);
```

1. {}
2. ReferenceError: greetign is not defined
3. undefined

# 요약

1. {}
   let으로 greeting변수를 선언하였지만 오타로 인하여 키워드가 없는 greetign 변수에 객체를 할당하였다. 하지만 현재 코드는 strict모드가 아니기 때문에 greetign변수는 전역 변수로 선언되어 값이 할당된다. 이로 인하여 {}가 출력된다.
