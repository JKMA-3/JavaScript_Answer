# 30. What's the output?

```javascript
const foo = () => console.log("First");
const bar = () => setTimeout(() => console.log("Second"));
const baz = () => console.log("Third");

bar();
foo();
baz();
```

1. First Second Third
2. First Third Second
3. Second First Third
4. Second Third First

# 요약

2. First Third Second<br><br>

1. bar()함수가 호출되어 setTimeout()가 실행된다. delay가 없기 때문에 즉시 테스크 큐에 콜백함수가 푸쉬된다.<br>
1. foo()함수가 호출되어 "First"가 출력된다.<br>
1. baz()함수가 호출되어 "Third"가 출력된다.<br>
1. 모든 코드가 끝나고 콜스택이 빈 시점에 테스크 큐에 있던 콜백함수가 푸쉬 및 실행되어 "Second"가 출력된다.<br>
