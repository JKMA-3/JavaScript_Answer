# 42. What does the setInterval method return in the browser?

```javascript
const name = "Lydia";
age = 21;

console.log(delete name);
console.log(delete age);
```

1. false, true
2. "Lydia", 21
3. true, true
4. undefined, undefined

# 요약

delete는 객체의 속성을 제거하는 연산자로 제거가 되면 true 제거에 실패 시 false를 반환한다. 현재 const로 선언한 name과 키워드 없이 선언한 age를 delete하였다. delete연산자는 var, let, const 키워드로 선언한 변수를 삭제 불가능 하므로 false를 반환하며 키워드 없이 선언한 age는 암묵적으로 전역객체에 생성되었기 때문에 제거가되어 true를 반환한다.
