# 17. What's the output

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

2. 2. ["", " is ", " years old"] "Lydia" 21<br>
      태그 탬플릿 리터럴을 사용하여 함수에 파싱하였기 떄문에 "one"에는 문자열 값이 배열로 저장되기에 ["", " is ", " years old"], two와 three는 표현식이 저장되기에 two = "Lydia" three = 21이 저장된다.

# 탬플릿 리터럴

(`)을 사용한 문자열 리터럴로 ${}내에 변수명을 삽입하는 것으로 표현식을 삽입할 수 있다.

# 태그 탬플릿 리터럴

탬플릿 리터럴을 함수에 파싱할 수 있으며 첫 번쨰 인자에는 문자열 값이 두 번쨰 인자부터는 가장 왼쪽에 있는 표현식 부터 저장된다.
