# proxy_pass에 https 사용하는법

upstream의 서버를 80포트로 해놓고 proxy_pass에 https:// 로 해놓으면 502 bad gateway 에러가 난다.
따라서 https로 proxy_pass를 사용하고 싶다면, upstream의 서버포트를 443으로 설정해야 한다.

```
upstream target {
    server target.com:443;
}

location / {
    proxy_pass https://target;
}
```
