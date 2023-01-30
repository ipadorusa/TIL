---
title: "나만 헛갈리는 중첩된 디스트럭처링"
date: "2023-01-30 22:46:30"
---

# 자바스크립트 중첩된 디스트럭처링

```javascript
const obj = { a: [1, 2, 3], b: [4, 5, 6] };
let {
  a: [first, second],
} = obj;
console.log(first, second); // 1, 2
```

```javascript
const arr = { first: { a: 1, b: 2 }, second: { a: 3, b: 4 } };
const {
  first: { a },
  second: { b },
} = arr;
console.log(a, b); // 1, 4
```

```javascript
const arr = { {a:1, b:2}, {a:3,b:4}};
const [{a}, {b}] = arr;
console.log(a, b); // 1, 4
```

## 매개변수 디스트럭처링

```javascript
function example({ a, b }) {
  console.log(a, b);
}
const o = { a: "ayy", b: "bee", c: "see", d: "dee" };
example(o); // 'ayy', 'bee'
example({ a: 1, b: 2 }); // 1, 2
```

```javascript
function example(first, { a, b }, last) {
  console.log(first, a, b, last);
}

const o = { a: "ayy", b: "bee", c: "see", d: "dee" };
example("alpha", o, "omega"); // 'alpha', 'ayy', 'bee', 'omega'
exmpale("primero", { a: 1, b: 2 }, "ultimo"); // 'primero', 1,2, 'ultimo'
```
