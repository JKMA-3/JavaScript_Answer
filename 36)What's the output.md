# 36. What's the output?

```javascript
console.log(typeof typeof 1);
```

1. "number"
2. "string"
3. "object"
4. "undefined"

# 요약

2. "string"<br>
   피연산자의 자료형을 문자열로 반환하는 typeof 함수를 중복 사용하였다. typeof 1 은 "number"을 반환한다. 이후 typeof를 사용하여 "number" 문자열의 타입을 반환하기 때문에 "string"이 반환된다.
