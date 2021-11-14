# label

label은 `break`, `continue`문과 함께 쓰이며, 참조 대상의 prefixing을 한다.  
참조 대상은 block(`{}`), for loop, function이다.

이 label을 적용한 예시 중 하나로, 이중 반복문에서 첫 반복문의 흐름제어가 가능해진다.

- ex)

  ```js
  let i, j;

  loop1: for (i = 0; i < 3; i++) {
    loop2: for (j = 0; j < 3; j++) {
      // i가 1이 되면, loop1을 continue
      if (i === 1 && j === 0) {
        continue loop1;
        // break loop1; 도 가능함.
      }
      console.log("i = " + i + ", j = " + j);
    }
  }

  // i = 0, j = 0
  // i = 0, j = 1
  // i = 0, j = 2
  // i = 2, j = 0
  // i = 2, j = 1
  // i = 2, j = 2
  ```

일반적인 로직은 아닌 것 같지만, 프로덕트에 적용시키면 재밌을 것 같다.
