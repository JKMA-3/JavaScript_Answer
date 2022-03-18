# 7. What's the output

```javascript
let a = 3;
let b = new Number(3);
let c = 3;

console.log(a == b);
console.log(a === b);
console.log(b === c);
```

1.  <code>true false true</code>
2.  <code>false false false</code>
3.  <code>true false false</code>
4.  <code>false true true</code>

# 요약

3. <code>true false false</code>
   변수 <code>a,c는 3이라는 숫자형 값이 할당</code>되며 <code>변수 c는 Number함수를 이용하여 생성한 Number객체가 할당</code>되기 때문에 비교 연산자 중 값만을 비교하는 '=='로는 3으로 동일하기 때문에 ture가 반환되며 'a === b'와 'b === c'는 값과 타입을 비교하는 '==='연산자로 숫자형 데이터와 객체는 타입이 다르기 때문에 false가 반환된다.

# 객체 타입

1. 객체
2. 함수
3. 배열

# 갹체 타입 외의 데이터

1. 숫자타입
2. 문자열 타입
3. Boolean 타입
4. Undefined 타입
5. Null 타입
6. Symbol 타입
