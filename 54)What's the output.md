# 42. What does the setInterval method return in the browser?

```javascript
(() => {
  let x = (y = 10);
})();

console.log(typeof x);
console.log(typeof y);
```

1. "undefined", "number"
2. "number", "number"
3. "object", "number"
4. "number", "undefined"

# 요약

현재 정의된 함수는 즉시 실행 함수이며 <code>let x = (y = 10);</code>는 <code>y=10; let x = y;</code>로 해석된다. 키워드 없이 선언된 변수 y는 암묵적으로 var키워드로 선언되며 따라서 전역변수로 선언된다. let키워드로 선언된 변수 x 는 함수 내부에서 선언된 지역변수이다. 따라서 외부에서 변수 x 접근 시 undefined가 출력되며 변수 y는 10이 출력된다.
