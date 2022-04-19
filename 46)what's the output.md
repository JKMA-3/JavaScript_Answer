# 46. What's the output?

```javascript
let person = { name: "Lydia" };
const members = [person];
person = null;

console.log(members);
```

1. null
2. [null]
3. [{}]
4. [{ name: "Lydia" }]

# 요약

4. [{ name: "Lydia" }]<br><br><br>
   1. person 변수에 객체 { name: "Lydia" }를 선언하고 members 내에 할당하였다.<br>
      {name : "Lydia"} 참조 -> person, members<br>
   2. person는 let으로 선언한 변수이기 때문에 null으로 재할당이 가능하다. members는 person내 참조값을 복사하였기 때문에 변경되지 않고 {name : "Lydia"}객체를 참조한다.<br>
      {name : "Lydia"} 참조 -> members<br>
      null -> person<br>
   3. console.log(members); -> [{name: "Lydia"}]<br>
