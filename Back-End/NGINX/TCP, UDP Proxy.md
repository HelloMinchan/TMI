# TCP, UDP Proxy

기존 HTTP 프록시를 태울때와 달리 stream 블록을 만들고 그안에서 설정을 해줘야한다.  
(HTTP는 http 블록 안에서 설정)

```
stream {
        upstream proxy_target {
                server www.example.com:7777;
        }

        server {
                listen 7777;  # udp일 경우 포트 옆에 udp 명시 (default tcp)
                proxy_pass proxy_target;
                proxy_responses 1;
        }
}
```
