# 72. What's the output?

```javascript
console.log(String.raw`Hello\nworld`);
```

1. Hello world!
2. Hello
   world
3. Hello\nworld
4. Hello\n
   world

# 요약

3. Hello\nworld
   템플릿 리터럴을 원시 문자열로 변경하는 함수인 String.raw()는 \n과 같은 문자는 개행문자가 아닌 문자열로 받기 때문에 '\n'을 문자열에 포함한 상태로 반환한다.

## String.raw()

템플릿 리터럴의 태그 함수로서 템플릿 리터럴의 원시 문자열 형식으로 반환하는 함수이다.
