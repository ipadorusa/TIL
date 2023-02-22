---
title: "Javscript Memo"
date: "2023-02-20 14:00:30"
---

## 스크립트로 n갯수만큼 증가 되는 수를 배열로 만들기

```typescript
function generateArray(startNumber: number, length: number): number[] {
  return Array.from({ length }, (_, i) => startNumber + i * startNumber);
}
```

# 주어진 배열에서 시작 인덱스부터 배열의 마지막 숫자까지 합 구하기

```typescript
function sumFromIndex(array:number[], startIndex: number): number {
  const sum = array.slice(startIndex - 1).reduce((acc, cur) => acc + cur, 0);
  return sum;
}
```

```javascript
const array = generateArray(2000, 26); // [2000, 4000, 6000, ..., 52000]

sumFromIndex(array, 7);
```
