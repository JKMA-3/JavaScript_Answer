# 60. What's the output

```javascript
const user = { name: "Lydia", age: 21 };
const admin = { admin: true, ...user };

console.log(admin);
```

1. { admin: true, user: { name: "Lydia", age: 21 } }
2. { admin: true, name: "Lydia", age: 21 }
3. { admin: true, user: ["Lydia", 21] }
4. { admin: true }

# 요약

2. { admin: true, name: "Lydia", age: 21 }<br>
   ES9부터 spread Operator에 객체에 관련된 사항이 추가되어 배열만이 아닌 객체의 복사, 업데이트에도 사용이 가능하다. <br>
   user내에 프로퍼티가 admin 객체 내에 저장된다. 따라서 { admin: true, name: "Lydia", age: 21 }가 출력된다.
