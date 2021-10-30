# Symbol

심볼은 새롭게 추가된 자바스크립트(ES)의 7번째 원시 타입임  
특징으로는 원시 타입처럼 값이 변경되지 않지만, 여러 인스턴스를 만들어도 값이 일치하지 않는다.(객체 타입 처럼)  
기존 타입생성 방식과 달리 new 연산자를 사용하지 않는다.

- 기존 자바스크립트(ES)의 6개 원 타입

  - Boolean
  - null
  - undefined
  - Number
  - String

- 객체 타입
  - Object

```js
let sb = Symbol();
let sb_error = new Symbol(); // Uncaught TypeError: Symbol is not a constructor

console.log(sb); // Symbol()
console.log(typeof sb); // symbole
```

그럼, 이 심볼을 어따 쓰냐하면  
객체 property의 key로 쓴다.

```js
const obj = {};
const sb = Symbol();
obj[sb] = "foo";
obj.bar = "bar";
console.log(obj); // { bar: 'bar' }
console.log(sb in obj); // true
console.log(obj[sb]); // foo
console.log(Object.keys(obj)); // ['bar']
```

재밌는 점은 Object.keys()가 오래 되어서 심볼을 키로 인식하지 못한다는 것이며,  
문자열만 key로 인식하는 기존 json 구조를 파괴하지 않는다는 것을 알 수 있다.  
또한, 라이브러리를 만들 때 사용하는 object가 다른 곳에서 참조될 우려가 있는 경우 Symbol을 사용하여 key값 충돌을 방지할 수 있는 장점이 있다.

```js
const library1Property = Symbol("lib1");
function lib1Tag(obj) {
  obj[library1Property] = 17;
}
const library2Property = Symbol("lib2");
function lib2Tag(obj) {
  obj[library2Property] = 777;
}
```
