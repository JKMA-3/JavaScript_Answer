# 42. What does the setInterval method return in the browser?

```javascript
function* generator(i) {
  yield i;
  yield i * 2;
}

const gen = generator(10);

console.log(gen.next().value);
console.log(gen.next().value);
```

1. [0, 10], [10, 20]
2. 20, 20
3. 10, 20
4. 0, 10 and 10, 20

# 요약

3. 10, 20
   첫 번째 Generator함수 호출 시 <code>yeild i;</code>가 실행되어 함수를 호출할 때 인자로 선언한 10이 출력되며 두 번째 호출 시 중지되었던 위치애서 시작하므로 <code>yield i \* 2;</code>가 실행되어 20이 출력된다.

# Gernerator Function

function\*으로 선언 시 생성되며 Iterator 객체를 반환한다. Iterator의 next() 메서드 호출 시 Generator 함수가 실행된다. yield문을 만날 때까지 진행된다. yeild\*문을 만날 경우 다른 Generator함수를 실행한다. 이 후에 next()메서드를 호출한다면 멈췄던 위치에서 다시 함수를 실행한다. 반환 값 내에는 <code>반환하는 값을 나타내는 value</code>와 <code>Generator함수 내의 yeild문을 전부 실행 여부를 boolean값으로 나타내는 done</code>가 저장되어 있다.
