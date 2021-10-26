# Unary plus

JavaScript에서 문자열을 숫자로 변경할 때, 단일 덧셈 연산자로 변경이 가능함

```js
const x = 1;
const y = -1;
const z = "123";

console.log(+x); // 1
console.log(+y); // -1
console.log(+z); // 123
console.log(+""); // 0
console.log(+true); // 1
console.log(+false); // 0
console.log(+"hello"); // NaN
```
