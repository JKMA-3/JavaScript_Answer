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

## 변수 선언
  JavaScript에서 var, let, const 키워드를 사용하여 변수를 선언한다.
  
## Var 키워드
  함수 선언 시 <code>함수 호이스팅(함수 선언문만 코드의 상단으로 끌어올려 런타임 이전에 선언)</code> 발생하여 함수 초기화 이전에 참조 가능(값은 undefined로 고정)
  
## let 키워드
함수 선언 시 함수 호이스팅이 발생하지만 let, const 키워드는 변수 선언, 초기화 단계 나누어져서 초기화 단계 이전에는 참조가 불가능한 선언되지만 <code>일시적 사각지대</code>로 인하여 초기화 이전에 참조 시 Refference Error 발생

