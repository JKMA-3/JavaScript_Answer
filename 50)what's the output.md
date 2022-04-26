# 50. What's the output?

```javascript
[1, 2, 3].map((num) => {
  if (typeof num === "number") return;
  return num * 2;
});
```

1. []
2. [null, null, null]
3. [undefined, undefined, undefined]
4. [ 3 x empty ]

# 요약

3. [undefined, undefined, undefined]<br><br>
   [1,2,3]의 각 요소에 대하여 타입이 "number"일 경우 <code>return;</code>을 실행하며 아닐 경우 <code>return num\*2;</code>를 실행한다. 각 요소는 숫자형 데이터 이므로 <code>return;</code>을 실행한다. return 명령문에 반환 값이 없을 경우 undefined를 반환하기 때문에 map()의 반환 값은 [undefined, undefined, undefined]가 된다.

# Array.prototype.map()

배열 메서드로 콜백함수를 인자로 매개변수로 받으며 콜백함수는 총 3개의 인자를 받을 수 있다. 각 요소에 콜백함수를 호출한 후 결과를 모아 새로운 배열로 반환한다.

## current Value

처리할 현재 요소

## index

처리할 현재 요소인 current Value의 인덱스

## array

map() 메서드를 호출한 배열

# return

함수 실행을 종료하며 주어진 값을 함수 호출 지점으로 반환하는 명령문으로 반환 값이 없을 경우 undefined를 반환한다.
