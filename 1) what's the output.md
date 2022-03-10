# 1. What is output
```javascript
function sayHi() {
console.log(name);
console.log(age);
var name = 'Lydia';
let age = 21;
}

sayHi();
```
1. <code>Lydia</code> and <code>undefined</code>
2. <code>Lydia</code> and <code>Refference Error</code>
3. <code>Refference Error</code> and <code>21</code>
4. <code>Undefined</code> and <code>Refference Error</code>

# 요약
  <code>var name</code>은 <code>변수 호이스팅</code>으로 인하여 undefined 출력
  <code>let age </code>는 <code>변수 호이스팅</code>가 발생하지만 일시적 사각지대로 인하여 Refference Error 발생
## 변수 호이스팅
  변수 선언 시 선언문을 코드 상단으로 끌어올린 듯이 실행하여 런타임 이전에 변수가 선언되는 방식으로 값은 할당되기 전 undefined로 고정
  
### Var 키워드
  변수 선언 시 <code>변수 호이스팅</code>으로 인하여 변수 선언문 이전에 참조가 가능하지만 값은 undefined로 고정
  
### let 키워드
  변수 선언 시 <code>변수 호이스팅</code>이 발생하지만 일시적 사각지대로 인하여 선언문 이전에 참조 시 Refference Error 발생

# 일시적 사각지대
  <code>let, const 키워드</code>로 변수 선언시 선언, 초기화 총 2가지 단계로 진행된다. 이 두가지 단계 사이를 일시적 사각지대라고 하며 이 때 변수 참조시 Refference Error가 발생한다.
