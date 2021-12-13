# Redis shutdown

## 문제

ecs fargate에 올려놓은 레디스가 갑자기 셧다운 됨

## 원인

(추정)
bull task 성공 로그가 메모리에 계속 쌓여 인스턴스 메모리 한계를 초과했다.

## 해결

1. bull의 removeOnComplete: true 옵션 추가하여 task 성공 로그 미적재

## 통찰

1. ttl 없이 레디스에 캐싱 할 때 쌓이기만 하는 데이터가 없는지 확인을 잘해야겠다.
