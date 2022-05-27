# 78. What is the output?

```javascript
const add = () => {
  const cache = {};
  return (num) => {
    if (num in cache) {
      return `From cache! ${cache[num]}`;
    } else {
      const result = num + 10;
      cache[num] = result;
      return `Calculated! ${result}`;
    }
  };
};

const addFunction = add();
console.log(addFunction(10));
console.log(addFunction(10));
console.log(addFunction(5 * 2));
```

1. Calculated! 20 Calculated! 20 Calculated! 20
2. Calculated! 20 From cache! 20 Calculated! 20
3. Calculated! 20 From cache! 20 From cache! 20
4. Calculated! 20 From cache! 20 Error

# 정리

3. Calculated! 20 From cache! 20 From cache! 20

add()을 addFunction 변수에 저장하였다. 후에 addFunction을 총 3번 호출하였다.
1 번 호출 -> num=10이기 때문에 cache객체 내에 값이 없기 때문에 if()에서 false가 반환되어 cache[10] = 20이 실행되며 "Calculated! 20"이 출력된다.
2 번 호출 -> num=10이기 때문에 cache={10:20}이 존재하기 때문에 if()에서 true가 반환되어 "From cache! 20"이 출력된다.
3 번 호출 -> 5\*2를 인자 값으로 addFunction을 호출하지만 addFunction(10)으로 호출되기 때문에 2 번 호출 했을 때와 같은 결과가 출력된다.
