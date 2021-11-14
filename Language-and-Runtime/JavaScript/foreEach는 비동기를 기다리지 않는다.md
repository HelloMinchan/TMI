# foreEach는 비동기를 기다리지 않는다

forEach문은 배열 요소를 병렬로 돌기에 loop에서 비동기 작업을 기다려주지 않는다

- ex)

```js
const idList = [1, 2, 3];
const result = [];

idList.forEach(async (id) => {
  const response = await axiosRequest.get(`URL/${id}`);
  result.push(response.data);
});

console.log(response); // 결과는 []
```

따라서 순차처리를 위해선 for of(혹은 기본 for)를 사용하자!

- ex)

```js
const idList = [1, 2, 3];
const result = [];

for (const id of idList) {
  const response = await axiosRequest.get(`URL/${id}`);
  result.push(response.data);
});

console.log(response); // 결과는 [data(id:1), data(id:2), data(id:3)]
```
