# Access Modifiers

class의 접근 제한자로 자바와 비슷함 (default가 없고, 살짝 다름)  
`public`, `private`, `protected`의 3개가 있으며, 접근 수식어를 명시하지 않은 경우 암묵적으로 `public`이 명시됨

- `public`  
  접근 제한이 전혀 존재하지 않음

- `private`  
   해당 클래스 내부의 코드만 접근이 가능해지며, 클래스 바깥의 코드에서 멤버에 접근 시 에러 발생  
   (이는, 상속을 받는 서브클래스에서도 동일함)

- `protected`  
  기본적으로 private과 같지만, 상속을 받는 서브클래스에서는 접근이 허용됨
