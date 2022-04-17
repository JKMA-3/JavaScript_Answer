# 42. What does the setInterval method return in the browser?

```javascript
setInterval(() => console.log("Hi"), 1000);
```

1. a unique id
2. the amount of milliseconds specified
3. the passed function
4. undefined

# 요약

1. a unique id<br>
   setInterval() 메서드는 특정 함수 혹은 코드를 일정 주기마다 실행시키는 코드로 반환 값은 타이머 고유의 ID이다. 반환된 고유의 ID는 clearInterval() 메서드를 통해 삭제가 가능하다.

# setInterval()

특정 주기로 코드 혹은 함수를 반복하여 실행하는 메서드로 타이머 고유의 ID(Interval ID)를 반환하며 cleaerInterval()을 통하여 타이머를 삭제할 수 있다.

## 파라미터

<code>const intervalID = setInterval(func, [delay, arg1, arg2, ...])</code>

### 1. func

    특정 주기마다 실행하는 함수 첫 번째 실행은 [delay] 이후에 실행된다.

### 2. delay

    함수의 실행 간의 지연 시간으로 기본 값은 0이다.

### 3. args

    함수 실행마다 전달되는 추가 인수
