# 20. What's the output

```javascript
function getAge() {
  "use strict";
  age = 21;
  console.log(age);
}

getAge();
```

1. 21
2. undefined
3. ReferenceError
4. TypeError

# 요약

3. ReferenceError<br>

스트릭트 모드를 적용시킨 함수에 선언하지 않은 변수를 참조하였으므로 reference error가 발생한다.

# Strict Mode

함수의 선두 혹은 전역의 선두에 'use strict';를 추가하여 적용 가능하지만 strict 와 non-strict가 혼용되어 오류를 발생시킬 수 있기 때문에 즉시 실행 함수로 감싼 스크립트 단위로 적용 시키는 것이 좋다.

## 발생하는 오류

### 1. 암묵적 전역

선언하지 않은 변수를 참조할 경우 암묵적으로 전역 객체로 동적 생성되어 전역 변수처럼 사용 가능한 현상으로 암묵적 전역이라고 하며 reference error 가 발생한다.

### 2. 변수 함수 매개변수의 삭제

변수, 함수 매개변수를 delete로 삭제할 경우 syntax error가 발생한다.

### 3. 중복된 매개변수

매개변수 이름이 중복될 경우 syntax error가 발생한다.

### 4.with 문의 사용

with문은 동일한 객체의 프로퍼티를 반복해서 사용할 경우 코드가 간단해지지만 성능과 가독성이 나빠지기에 사용하지 않는 편이 좋으며 사용할 경우 syntax error가 발생한다.
