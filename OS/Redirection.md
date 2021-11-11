# Redirection

Redirection(재지향)이란 OS 단에서 쉘이 표준 입출력을 파일 형태로 열고 있고 결과를 출력 장치로 내보내는데,  
이 출력을 가로채 다른 파일 혹은 프로그램의 표준 입력으로 보내는 것을 의미한다.

- `command > fileWrite`  
  standard output of command to file
- `command 1> fileWrite`  
  standard output of command to file (same as previous)
- `command 2> file`  
  Write standard error of command to file (OS/2 and NT)
- `command > file 2>&1`  
  Write both standard output and standard error of command to file (OS/2 and NT)
- `command >> file`  
  Append standard output of command to file
- `command 1>> file`  
  Append standard output of command to file (same as previous)
- `command 2>> file`  
  Append standard error of command to file (OS/2 and NT)
- `command >> file 2>&1`  
  Append both standard output and standard error of command to file (OS/2 and NT)
- `commandA | commandB`  
  Redirect standard output of commandA to standard input of commandB
- `commandA 2>&1 |commandB`  
  Redirect standard output and standard error of commandA to standard input of commandB(OS/2 and NT)
- `command < file`  
  command gets standard input from file
- `command 2>&1`  
  command's standard error is redirected to standard output (OS/2 and NT)
- `command 1>&2`  
  command's standard output is redirected to standard error (OS/2 and NT)
