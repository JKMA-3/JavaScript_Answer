# 40. What's the output?

```javascript
[
  [0, 1],
  [2, 3],
].reduce(
  (acc, cur) => {
    return acc.concat(cur);
  },
  [1, 2]
);
```

1. [0, 1, 2, 3, 1, 2]
2. [6, 1, 2]
3. [1, 2, 0, 1, 2, 3]
4. [1, 2, 6]

# 요약

3. [1, 2, 0, 1, 2, 3]<br>
   reduce()의 콜백함수와 초기값([1, 2])를 선언하였으므로 acc의 초기 값은 [1, 2]이다. concat()으로 인하여 주이진 배열([[0, 1], [2, 3]])이 초기 값인 [1, 2]에 합쳐져 [1, 2, 0, 1, 2, 3]이 반환된다.

# Array.protptype.reduce(callback[, initialValue])

reduce()는 배열의 요소에 대하여 reducer를 실행하고 하나의 값을 반환하는 메서드이며 콜백함수와 초기 값(initialValue)을 매개변수로 받을 수 있다. <br>

## 콜백 함수

배열의 각 요소에 대해 실행 할 함수이며 4개의 인자를 받을 수 있다.<br>

1. 리듀서 함수의 반환 값(accumulator)<br>
2. 현재 값(currentValue)<br>
3. 현재 인덱스 (currentIndex)<br>
4. 원본 배열 (array)<br>

## 초기 값(initialValue)

콜백함수 최초 호출 시 첫 번째 인수(accumulator)에 제공하는 값 선언하지 않을 경우 원본 배열(Array)의 첫 번째 요소를 사용한다.

# Array.prototype.concat()

여러개의 배열이나 값을 기존의 배열에 합쳐서 하나의 새로운 배열을 반환하는 메서드이다.
