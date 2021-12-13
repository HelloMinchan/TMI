# SQS consume delay

## 문제

SQS 메시지 consume이 바로바로 되지 않고 지연됨

## 원인

consume 서버에 트래픽 부하가 심해져 SQS에서 메시지를 꺼내오지 못함

## 해결

1. consume 서버 scale out

## 통찰

1. 서비스가 점차 성장함에 따라 잘 돌던 서버가 트래픽이 높아져 견디지 못하는 좋은 경험을 얻었다.
