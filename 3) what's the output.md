# 3. What is output

```javascript
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

1. <code>20</code> and <code>62.83185307179586</code>
2. <code>20</code> and <code>NaN</code>
3. <code>20</code> and <code>63</code>
4. <code>NaN</code> and <code>63</code>

# 요약

# this키워드

## this 키워드가 가리키는 대상

# 화살표 함수
