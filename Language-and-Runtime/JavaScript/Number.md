# Number

자바스크립트는 오직 한가지 숫자 타입을 가진다. (64비트 이중 정밀도)

## Decimal

### 10진수에 정확히 매핑 되지 않음

```js
console.log(0.1 + 0.2); // 0.30000000000000004
```

## Integer

### 정수의 한계

```js
console.log({ max: Number.MAX_SAFE_INTEGER, min: Number.MIN_SAFE_INTEGER });
// {max: 9007199254740991, min: -9007199254740991}
```

### 한계를 넘어가면 +1 -1의 오차가 발생

```js
console.log(Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2); // true!
console.log(Number.MIN_SAFE_INTEGER - 1 === Number.MIN_SAFE_INTEGER - 2); // true!
```

## NaN

### Not a Number, 숫자 계산이 number로 반환될 수 없는 경우 반환됨

```js
console.log(Math.sqrt(-1)); // NaN
```

### 일치 연산자가 먹히지 않으므로, Number.isNaN을 사용해 확인할 것

```js
// Wrong Way
console.log(NaN === NaN); // false!!

// Right Way
console.log(Number.isNaN(NaN)); // true
```

## Infinity

### 최대 최소 값

```js
console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
console.log(-Number.MAX_VALUE); // -1.7976931348623157e+308
```

### Infinity/-Infinity

```js
console.log(1 / 0); // Infinity
console.log(-1 / 0); // -Infinity

console.log(Number.POSITIVE_INFINITY === Infinity); // true
console.log(Number.NEGATIVE_INFINITY === -Infinity); // true

// 부등호 연산 사용가능
console.log(Infinity > 1); // true
console.log(-Infinity < -1); // true
```

## Infinitesimal

### 숫자로 사용할 수 있는 0이 아닌 가장 작은 값

```js
console.log(Number.MIN_VALUE); // 5e-324
```

### MIN_VALUE보다 작은 값은 0으로 고정

```js
console.log(Number.MIN_VALUE / 10); // 0
```
