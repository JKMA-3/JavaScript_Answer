<<<<<<< HEAD
# 5. Which one is true
=======
# 4. Which one is true
>>>>>>> origin/main

```javascript
const bird = {
  size: "small",
};

const mouse = {
  name: "Mickey",
  small: true,
};
```

1.  <code>mouse.bird.size</code> is not valid
2.  <code>mouse[bird.size]</code> is not valid
3.  <code>mouse[bird["size"]]</code> is not valid
4.  <code> All of them</code> are valid

# 요약

1. <code>mouse.bird.size</code>is not valid<br>
   자바스크립트 엔진은 mouse.bird를 먼저 평가한다. 하지만 mouse란 객체에는 bird라는 키는 없기 때문에 undefined가 반환한 후 undefined.bird를 탐색하기 때문<code>Cannot read properties of undefined (reading 'size')</code>를 발생한다.<br/>
   <code>mouse.bird = undefined -> undefined.size = Error 발생</code>

# 프로퍼티 접근 방법

총 2가지 방법이 있으며 객체에 없는 프로퍼티 접근 시 오류가 발생하지 않고 undefined를 반환한다.

## 마침표 표기법

마침표 프로퍼티 접근 연산자(.)를 사용하는 접근 방법으로 좌측에는 객체를 나타내는 연산자가 우측에는 프로퍼티의 키를 지정하여 사용한다.

## 대괄호 표기법

대괄호 프로퍼티 접근 연산자([])를 사용하는 접근 방법으로 좌측에는 객체를 나타내는 연산자를 대괄호[]내부에는 프로퍼티의 키를 지정하여 사용한다.([] 내부는 따옴표(', ")로 감싸야한다. 감싸지 않을경우 Reference Error가 발생한다.)
