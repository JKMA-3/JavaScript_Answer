# 38. What's the output?

```javascript
(() => {
  let x, y;
  try {
    throw new Error();
  } catch (x) {
    (x = 1), (y = 2);
    console.log(x);
  }
  console.log(x);
  console.log(y);
})();
```

1. 1 undefined 2
2. undefined undefined undefined
3. 1 1 2
4. 1 undefined undefined

# 요약

1. 1 undefined 2
   let키워드를 사용하여 x,y변수를 생성하였다. (let x, y = undefined)<br>
   try...catch문에서 Error()를 생성하여 catch문에 걸리도록 하였다. catch(x)에서 x라는 변수가 생성되었다. let키워드는 블록레벨 스코프를 따르기 때문에 try...catch문 밖에서 선언한 x변수와 안에서 생성한 x변수는 다른 변수이다.<br>
   (x =1), (y = 2);로 인하여 각 변수에 값이 할당된다. x는 catch(x)에서 선언된 변수 x에 할당되며 y는 let 키워드로 선언한 y에 할당된다.(let x = undefined, let y = 2, catch(x = 1))<br>
   catch문 내에 있는 console.log(x); => 1이 출력된다.<br>
   catch문 외에 있는 x,y는 let키워드로 선언된 x,y이기 떄문에 x= undefined, y = 2가 출력된다.
