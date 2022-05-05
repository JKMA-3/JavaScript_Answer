# 60. What's the output

```javascript
const settings = {
  username: "lydiahallie",
  level: 19,
  health: 90,
};

const data = JSON.stringify(settings, ["level", "health"]);
console.log(data);
```

1. "{"level":19, "health":90}"
2. "{"username": "lydiahallie"}"
3. "["level", "health"]"
4. "{"username": "lydiahallie", "level":19, "health":90}"

# 요약

1. "{"level":19, "health":90}"<br>
   객체 settings를 JSON문자열로 변환한다. 두번째 매개변수인 값을 구분하는 배열이 있으므로 배열에 해당하는 값만 가져온다. 따라서 setting객체의 'level', 'health'만 가져오기 때문에 {"level":19, "health":90}으로 변환된다.

# JSON.strubgfy()

Javascript값이나 객체를 JSON문자열로 변환하는 메서드이다.

## 매개변수

1. value <br>
   JSON 문자열로 변환할 값<br>
2. replacer(Option)<br>
   JSON문자열로 변환할 방식을 정하는 함수 혹은 화이트리스트 방식으로 값을 구분하는 string, Number객체들의 배열 지정되지 않는 경우 모든 값을 변환한다.<br>
3. space(Options)<br>
   가독성을 목적으로 JSON문자열 출력에 공백을 삽입할 때 사용하는 String, Number객체 Number객체라면 공백의 수를 String일 경우 문자열을 공백으로 사용 지정하지 않을 경우 공백을 넣지 않는다. <br>
