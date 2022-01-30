# Ubuntu 도커 설치

> sudo apt update

> sudo apt install apt-transport-https ca-certificates curl software-properties-common

> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

> sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"

> sudo apt update

> apt install docker-ce

- 도커 실행 확인  
  sudo systemctl status docker
