# 10. What happens when we do this?

```javascript
function bark() {
  console.log("Woof!");
}

bark.animal = "dog";
//console.log(bark.animal); -> dog 출력
```

1. <code>Nothing, this is totally fine!</code>
2. <code>SyntaxError. You cannot add properties to a function this way.</code>
3. <code>"Woof" gets logged.</code>
4. <code>ReferenceError</code>

# 요약

함수 bark()를 생성하고 함수 내에 동적 프로퍼티가 생성하였다. 함수는 객체이기 때문에 동적 프로퍼티 생성이 성립되어 bark()내에 animal : "dog"이라는 프로퍼티가 생성된다.
