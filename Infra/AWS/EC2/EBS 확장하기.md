# EBS 확장하기

1. ec2 console > volumes > modify volume애서 용량 설정
2. "is-use completed" 상태가 될때까지 기다림
3. `lsblk` 명령으로 스토리지 블록 상태 확인
4. `sudo growpart /dev/nvme0n1 1` 명령으로 디스크 확장
5. `sudo resize2fs /dev/nvme0n1p1` 명령으로 리눅스 파일시스템 확장
6. df -h로 디스크 공간 확인
