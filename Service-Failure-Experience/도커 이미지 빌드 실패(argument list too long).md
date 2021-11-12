# 도커 이미지 빌드 실패(argument list too long)

## 문제

젠킨스에서 잘 빌드되던 이미지가 fail나는 문제

## 원인

해당 이미지에서 사용하는 환경 변수를 젠킨스를 통해 외부에서 주입하는데, 환경 변수의 길이가 OS 한도를 초과해 빌드가 깨짐

> 에러 메시지 : exec user process caused "argument list too long"

문제의 환경 변수를 [Redirection](https://github.com/HelloMinchan/TMI/blob/main/OS/Redirection.md)을 통해 파일화하여 주입하는데,  
`>` 명령어가 아닌 `>>` 명령어로 만드는 바람에 덮어씌어 지지 않고 Append되어 계속 쌓이고 있었음

## 해결

1. 환경변수를 만들던 `>>` 명령어를 `>`로 변경

## 통찰

1. 쉘 명령어 헷갈리지 말자..
