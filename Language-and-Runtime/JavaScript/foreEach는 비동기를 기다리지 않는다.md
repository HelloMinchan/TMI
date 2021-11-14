# foreEach는 비동기를 기다리지 않는다

forEach문은 배열 요소를 병렬로 돌기에 loop에서 비동기 작업을 기다려주지 않는다

- ex)

```js
array.forEach(async);
```
