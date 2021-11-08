# Index Signature

객체의 키 값이 동적으로 변할때 타입을 어떻게 잡을까?

예를 들어

```js
person = {};

person["Kim"] = 23;
person["Jung"] = 25;
```

이런 경우, person의 타입을 어떻게 잡느냔 말이다...

그럴 땐 타입스크립트의 Index Signature를 사용한다.

```ts
interface Person {
  [name: string]: number;
}
```

Index Signature란 객체의 새로운 추가 속성을 명시적으로 any 타입으로 설정하는 것이다.
