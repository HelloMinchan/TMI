# swap 파일 크기 확장

t2.micro 인스턴스 기준

메모리 1GB => 2GB 만들기

> sudo dd if=/dev/zero of=/swapfile bs=128M count=16

스왑 파일 읽기 쓰기 권한 부여

> sudo chmod 600 /swapfile

리눅스 스왑 영역 설정

> sudo mkswap /swapfile

스왑 공간에 스왑 파일 추가, 스왑 파일 즉시 사용

> sudo swapon /swapfile

성공 여부 확인

> sudo swapon -s

부팅 시 스왑 파일 활성화

> sudo vi /etc/fstab

파일 끝에 아래 코드 삽입

> /swapfile swap swap defaults 0 0

마지막, 메모리 확인

> free
