# 32.When you click the paragraph, what's the logged output?

```javascript
<div onclick="console.log('div')">
  <p onclick="console.log('p')">Click here!</p>
</div>
```

1. p div
2. div p
3. p
4. div

# 요약

1. p div<br>
   이벤트 발생 시 이벤트 전파 단계인 Capturing, Target, Bubbling를 거친다. <br>
1. div -> p로 가는 Capturing<br>
1. 이벤트 타겟인 p에 도달한 Targeting<br>
1. p -> div로 가는 Bubbling<br>
   p에서 발생한 click 이벤트가 div로 전파되었기 때문에 콘솔에는 p div가 출력된다.

# addEventListener

document.addEventListener(event, function, useCapture);<br>
함수에서 useCapture이 true라면 Capturing단계에서 이벤트가 발생된다.

# 이벤트 전파를 막기 위한 방법

## event.preventDefault()

이벤트의 default 동작을 중단한다.

## event.stopPropagation()

이벤트가 bubbling 혹은 capturing 되는 것을 막는다.

## event.stopImmediatePropagation()

bubbling 혹은 capturing 뿐만 아니라, 해당 개체에 걸린 현재 이벤트를 제외한, 다른 이벤트까지 막는다.

## return false

jQuery event handler의 경우는, stopPropagation()과 stopImmediatePropagation()을 모두 수행한 것과 같고 그 외의 handler 경우(non-jQuery)에서는, preventDefault()를 수행한 것과 같다.
