# 16. What's the output

```javascript
function getPersonInfo(one, two, three) {
  console.log(one);
  console.log(two);
  console.log(three);
}

const person = "Lydia";
const age = 21;

getPersonInfo`${person} is ${age} years old`;
```

1. "Lydia" 21 ["", " is ", " years old"]
2. ["", " is ", " years old"] "Lydia" 21
3. "Lydia" ["", " is ", " years old"] 21

# 요약

2. 2. ["", " is ", " years old"] "Lydia" 21
