# HTTP response status codes

응답 뿌려줄 때, 유념하며 사용하자!

링크 : [여기](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses)

## Successful responses

- 200 : OK (요청이 성공했다)
- 201 : Created (요청이 성공했고, 그 결과로 새 리소스가 생성 되었다)

## Redirection messages

- 301 : Moved Permanently (URL이 영구적으로 변경되었을 때)

## Client error responses

- 400 : Bad Request (잘못된 요청, 혹은 손상된 데이터)
- 401 : Unauthorized (인증 에러)
- 404 : Not Found (제일 흔한 에러, 컨트롤러를 찾을 수 없을 때)
- 405 : Method Not Allowed (요청에 해당하는 HTTP 메소드가 없음)
- 409 : Conflict (리소스가 충돌난 상황, 나의 경우 요청에 의해 처리되어야 하는 데이터가 이미 처리되어 있는 상황에 적용함)

## Server error responses

- 500 : Internal Server Error (서버 내부로직에서 에러 난 경우 ex. DB 연결 실패)
