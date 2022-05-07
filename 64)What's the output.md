# 60. What's the output

```javascript
const value = { number: 10 };

const multiply = (x = { ...value }) => {
  console.log((x.number *= 2));
};

multiply();
multiply();
multiply(value);
multiply(value);
```

1. 20, 40, 80, 160
2. 20, 40, 20, 40
3. 20, 20, 20, 40
4. NaN, NaN, 20, 40

# 요약

3. 20, 20, 20, 40<br>
   multiply() 호출 시 매개변수를 지정하지 않는다면 x내에 value값을 복사한다. x={number:10}; 이므로 20이 출력된다. 이는 x.number이기 때문에 value.number 값은 적용되지 않는다. 따라서 20이 2번 출력된다.<br>
   이 후 multify() 내에 매개변수로 value를 지정해주었기 때문에 x.number === value.number이다. 따라서 x.number \*= 2 실행 시 value.number에도 적용되기 때문에 20, 40이 출력된다.
