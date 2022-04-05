# 4. What is output

```javascript
const sum = eval("10*10+5");
```

1. 105
2. "105"
3. TypeError
4. "10\*10+5"

# 요약

1. 105
   eval()는 문자로 표현된 JavaScript코드를 실행하여 얻은 값을 반환하거나 값이 없다면 undefined를 반환하는 함수이다. 즉 "10*10*+5"를 계산한 값을 반환하기 때문에 105가 반환되어 sum에 저장된다.
