# 34. What's the output?

```javascript
function sayHi() {
  return (() => 0)();
}

console.log(typeof sayHi());
```

1. "object"
2. "number"
3. "function"
4. "undefined"

# 요약

2. "number"<br>
   typeof sayHi() 에서 sayHi()를 호출하였기에 즉시 0이 return된다. 따라서 typeof 0이 되기 떄문에 0의 타입인 Number가 출력된다.
