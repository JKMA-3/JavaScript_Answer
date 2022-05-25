# 13. What are the three phases of event propagation?

1. Target > Capturing > Bubbling
2. Bubbling > Target > Capturing
3. Target > Bubbling > Capturing
4. Capturing > Target > Bubbling

# 요약

이벤트 전파단계는 캡쳐링 > 타깃 > 버블링 과정으로 진행된다.

# 이벤트란?

## 이벤트 전파 단계

DOM트리 상에 있는 DOM요소 노드에서 발생한 이벤트가 DOM트리를 통하여 전파되는 것을 이벤트 전파 단계라고 하며 캡쳐링, 타깃, 버블링 총 3단계로 진행된다.

### 1. Capturing

이벤트 객체 발생 시 이벤트 객체가 생성되며 window에서 부터 이벤트 타깃(상위에서 하위)으로 전파되는 단계이다.

### 2. Target

이벤트 객체가 이벤트 타깃에 도달하는 단계이다.

### 3. Bubbling

타깃 단계 후 이벤트 객체가 이벤트 타깃으로 부터 window로 전파되는 단계이다.
