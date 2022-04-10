# 26. The JavaScript global execution context creates two things for you: the global object, and the "this" keyword.

A: true
B: false
C: it depends

# 요약

A: true

실행 컨텍스트 생성 시 생성되는 객체로는 변수객체, 스코프체인, this키워드 등이 있다. 하지만 전역 실행 컨텍스트 생성 시 전역이 스코프체인의 종점이기 떄문에 null이 할당된다. 따라서 전역 실행 컨텍스트가 생성 시 변수객체와 this키워드 총 2개가 생성된다.

# null

객체 타입이 아닌 기본 데이터 타입으로 아무것도 존재하지 않다는 의미이다.

## typeof null

typeof로 확인해본 null의 타입은 Object이다. 이는 typeof 함수내 null채크 로직이 누락되어 생기는 버그이다.

## null타입 체크방법

'==='연산자(값과 타입이 일치해야 true를 반환)를 사용하여 채크한다.
