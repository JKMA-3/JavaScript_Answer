# 52. What's the output?

```javascript
function greeting() {
  throw "Hello world!";
}

function sayHi() {
  try {
    const data = greeting();
    console.log("It worked!", data);
  } catch (e) {
    console.log("Oh no an error:", e);
  }
}

sayHi();
```

1. It worked! Hello world!
2. Oh no an error: undefined
3. SyntaxError: can only throw Error objects
4. Oh no an error: Hello world!

# 요약

4. Oh no an error: Hello world!<br><br>
   throw는 험수의 실행을 중지하고 catch블록으로 전달된다. greeting()에서는 "Hello world!"를 throw 하므로 catch(e)의 e에 전달되어 "Oh no an error: Hello world!"가 출력된다.
