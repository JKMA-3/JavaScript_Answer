# 19. What's the output

```javascript
function getAge(...args) {
  console.log(typeof args);
}

getAge(21);
```

1. "number"
2. "array"
3. "object"
4. "NaN"

# 요약

3. "object"<br>

rest 파라미터를 이용하여 21을 인자로 함수를 호출하였다. rest파라미터는 인자 값을 배열 객체로 받기 때문에 args의 타입은 Object이다.

# 레스트 파라미터

매개변수 앞에 ...을 붙여 정의하는 매개변수를 의미하며 함수에 전달된 인수들을 배열(Array)로 변경한다. Rest 파라미터는 한개만 정의 가능하며 함스 객체의 length에 영향을 주지 않는다.

## arguments객체

매개변수의 개수를 파악 불가능한 가변 인자 함수일 경우 arguments객체를 이용하여 인자를 전달하여 지역변수와 같이 사용하였다. 하지만 arguments객체는 유사 배열 객체이기 때문에 배열 메서드를 사용하기 위해서는 arguments객체를 배열로 변경해야하는 번거로움이 있었다. ES6부터는 rest파라미터를 이용하여 배열로 인자를 전달 가능하여 배열로 변경하지 않아도 되며 화살표 함수에서는 arguments객체를 생성할 수 없기 때문에 rest파라미터를 사용해야 한다.
