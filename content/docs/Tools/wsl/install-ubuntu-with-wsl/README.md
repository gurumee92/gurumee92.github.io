---
title: "wsl로 우분투 설치하기"
weight: 3
bookCollapseSection: true
---

# wsl로 우분투 설치하기

## 개요

안녕하세요! 이제 막 개발의 세계에 발을 들인 분들이라면 **"리눅스 환경에서 작업해야 한다"**는 말을 자주 들으실 겁니다. 하지만 잘 쓰던 윈도우를 지우고 리눅스를 깔기엔 너무 부담스럽죠?

오늘은 윈도우를 그대로 쓰면서 가상 머신보다 훨씬 가볍고 빠르게 리눅스를 사용할 수 있는 WSL2 설치법을 핵심만 콕콕 집어 알려드리겠습니다!

## wsl은 무엇인가?

**WSL(Windows Subsystem for Linux)**은 이름 그대로 **'윈도우용 리눅스 하위 시스템'**입니다.

기존에는 윈도우에서 리눅스를 쓰려면 'VirtualBox'나 'VMware' 같은 무거운 가상 머신 프로그램을 따로 설치해야 했습니다. 하지만 WSL은 마이크로소프트가 직접 만든 기능으로, 윈도우와 리눅스가 마치 한 몸처럼 작동하게 해줍니다.

`WSL`로 리눅스를 설치하면 다음과 같은 장점을 얻을 수 있습니다.

* 가벼움: 메모리와 CPU 점유율이 매우 낮습니다.
* 빠름: 윈도우 파일과 리눅스 파일을 자유롭게 주고받으며 초고속으로 작동합니다.
* 편의성: 윈도우 터미널에서 바로 우분투를 실행해 개발 도구를 설치할 수 있습니다.

## wsl로 우분투 설치하기

**1. 터미널 열기**
윈도우 하단 검색창에 **'PowerShell'**을 검색한 뒤, **[관리자 권한으로 실행]**을 눌러주세요. 

**2. 설치 명령어 입력**
다음 명령어를 입력하고 엔터를 누릅니다.

```
$ wsl --install -d Ubuntu   
```

이 명령어는 `WSL` 기능을 켜고, 최신 버전의 우분투를 자동으로 다운로드합니다.


**3. 우분투 설정**
그 후 파워쉘에서 다시 한 번 다음을 입력합니다. 잠시 기다리면 사용자 정보를 입력하라고 나옵니다.

```
$ wsl ~
Provisioning the new WSL instance Ubuntu
This might take a while...
Create a default Unix user account: # <- 유저 이름 입력
New password:  # <- 유저 비밀번호 입력
Retype new password:  # <- 유저 비밀번호 입력
```


이 때 쓰이는 유저 이름과 특히 **비밀 번호**는 관리자 권한을 얻는 `sudo` 명령어를 쓸 때 반드시 입력해야하니 꼭 기억하세요.

한 번 바로 해볼까요? 유저 이름과 비밀번호 입력이 모두 끝나면 다음 화면이 뜰 것입니다.
```bash
# ...
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 5.15.167.4-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Thu Jan 15 23:07:34 KST 2026

  System load:  0.03                Processes:             31
  Usage of /:   0.1% of 1006.85GB   Users logged in:       0
  Memory usage: 2%                  IPv4 address for eth0: 192.168.177.190
  Swap usage:   0%


This message is shown once a day. To disable it please create the
/home/gurumee/.hushlogin file.
gurumee@test:~$ # <- 여기서 입력을 기다림
```

이제 `exit` 명령어를 입력하여 `WSL`에서 빠져 나옵니다

```bash
gurumee@test:~$ exit
logout
```

## 기타 명령어들

`WSL`로 관리되고 있는 리눅스 서버들을 확인하거나 제거하고 싶을 때가 있을 수 있습니다. 이 때를 위해 몇 가지 명령어들을 알아보겠습니다.

**현재 WSL로 생성된 서버들 확인하기**
내가 설치한 리눅스 목록과 현재 실행 중인지 확인합니다.

```bash
$ wsl -l -v
  NAME      STATE           VERSION
* Ubuntu    Stopped         2
```

**기본 리눅스 설정하기**
여러 개의 리눅스를 설치했을 때, wsl만 쳤을 때 바로 실행될 녀석을 정합니다.

```bash
# wsl --set-default <배포판이름>
$ wsl --set-default Ubuntu
작업을 완료했습니다.
```


**리눅스 삭제하기 (초기화)**
연습용으로 쓰다가 꼬였거나, 더 이상 필요 없을 때 깨끗하게 지우는 방법입니다. (내부 데이터가 다 날아가니 주의하세요!)

```bash
# wsl --unregister <배포판이름>
$ wsl --unregister Ubuntu  
등록 취소 중입니다.
작업을 완료했습니다. 
``` 

## 마치며: 개발 초보를 위한 꿀팁
WSL을 더 편하게 쓰시려면 마이크로소프트 스토어에서 **'Windows Terminal'**과 **'VS Code(Visual Studio Code)'**를 설치해 보세요. VS Code에서 WSL 확장 프로그램을 설치하면 윈도우에서 코딩하면서 실행은 리눅스에서 하는 마법 같은 경험을 할 수 있습니다!

이제 윈도우에서도 강력한 리눅스 개발 환경을 갖추게 되신 것을 축하드립니다. 즐거운 코딩 하세요!