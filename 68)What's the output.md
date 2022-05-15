# 68. What's the output?

```javascript
console.log(Number(2) === Number(2));
console.log(Boolean(false) === Boolean(false));
console.log(Symbol("foo") === Symbol("foo"));
```

1. true, true, false
2. false, true, false
3. true, false, true
4. true, true, true

# 요약

1. true, true, false<br>
   Number(), Boolean() 메서드는 반환 값이 원시 타입이며 Symbol()의 반환 값은 객체이다. 원시 값은 일치 연산자 ('===')에서 같은 값일 경우 true를 반환하지만 객체인 경우 참조 값을 비교하기 때문에 값이 같다고 해도 저장하는 주소인 참조 값이 다르기 때문에 false를 반환한다. 따라서 true, true, false를 출력한다.
