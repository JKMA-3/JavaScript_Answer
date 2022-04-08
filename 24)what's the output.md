# 24. What's the output

```javascript
const obj = { 1: "a", 2: "b", 3: "c" };
const set = new Set([1, 2, 3, 4, 5]);

obj.hasOwnProperty("1");
obj.hasOwnProperty(1);
set.has("1");
set.has(1);
```

1. false true false true
2. false true true true
3. true true false true
4. true true true true

# 요약

고른 답 : 1. false true false true
정답 : 3. true true false true

객체의 키로 사용가능한 타입으로는 문자형과 심볼형이 있다. 이외의 타입을 사용하여 선언한 경우 문자열로 자동변환되기 때문에 객체 obj 내에 선언한 {1:"a", 2:"b", c:"3"}은 {"1":"a", "2":"b", "c":"3"}로도 볼 수 있다. 따라서 hasOwnProperty("1")은 true이며 hasOwnProperty(1)은 false를 반환한다.<br>
set객체는 중복을 제외한 모든 타입의 값을 저장 가능한 객체로 객체set 내에 선언된 [1,2,3,4,5]는 숫자타입이다. 그러므로 has(1)은 true를 반환하지만 has("1")은 false를 반환한다.

# hasOwnProperty()

객체 내에 해당 프로퍼티가 존재한다면 true, 존재하지 않는다면 false를 반환한다. 단 프로토타입 체인은 확인하지 않으며 오직 해당 객체에서 정의된 프로퍼티만 탐색한다.

# has()

Set객체 내에 해당 프로퍼티가 존재한다면 true, 존재하지 않는다면 false를 반환한다.('=='연산자와 비슷하지만 +0과 -0이 같다고 여긴다)
