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
