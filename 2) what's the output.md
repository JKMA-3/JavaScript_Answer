# 1. What is output

```javascript
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}

for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
}

sayHi();
```

1. <code>0 1 2</code> and <code>0 1 2</code>
2. <code>0 1 2</code> and <code>3 3 3</code>
3. <code>3 3 3</code> and <code>0 1 2</code>

# 요약

<code>var</code>키워드는 <code>함수 레벨 스코프</code>로 코드 블록인 for문에서 선언하여도 전역 변수로 생성되어 setTImeout()함수로 인한 지연된 시간동안 <code>전역변수 i=3</code>이 되기 때문에 <code>3 3 3</code>이 출력

<code>let</code>키워드는 <code>블록 레벨 스코프</code>로 for문 내에 지역 변수로 생성되며 반복될 때 마다 클로저로 인하여 정적환경이 저장되어 setTimeout()로 인하여 시간이 지연되어도 각각의 <code>정적환경에 저장된 i의 값</code>이 출력

# 스코프

변수, 함수, 클래스에 접근 가능한 범위

## var과 let,const의 차이

<code>var</code>키워드는 <code>함수 레벨 스코프</code>

<details>
<summary>함수 레벨 스코프</summary>
<div markdown="1">

함수 레벨 스코프란 변수 선언 시 함수만을 지역 스코프로 인정하기 때문에 함수 내부에서 선언된 변수만 지역변수 이며 함수 외부에서 선언된 변수는 전역 변수로 선언되는 방식

</div>
</details>
<code>let, const</code>키워드는 <code>블록 레벨 스코프</code>
<details>
<summary>블록레벨 스코프</summary>
<div markdown="2">

모든 코드블록(함수, if, for, try/catch)을 지역 스코프로 인정하여 코드 블록 내부에서 선언된 변수는 지역 변수로 외부에서는 참조가 불가능한 방식

</div>
</details>

# 클로저

함수가 선언되었을 때의 정적 환경을 저장하여 외부에서 접근 가능한 함수

# 정적 환경(Lexical Environment)

식별자와 상위 스코프에 대한 참조를 저장하는 자료구조
