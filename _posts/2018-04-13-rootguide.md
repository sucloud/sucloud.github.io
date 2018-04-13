---
layout: post
title: Sucloud 관리자 사용가이드
summary: Sucloud 관지라 사용가이드 입니다.
featured-img: emile-perron-190221
---

# 관리자 사용가이드
### 1. 로그인 화면

![Alt text](/assets/img/posts/root_1.png)

*sucloud 기본 로그인 화면입니다. 관리자 및 사용자 모두  로그인이 가능합니다.*

기본 관리자 비밀번호입니다. 꼭 변경해주세요.

``` ID : root ```

``` password : 11111111 ```

### 2. 대시보드

![Alt text](/assets/img/posts/sucloud-dashboard.png)

기본적인 대시보드 화면입니다. 현재 사용하고 있는 인스턴스, 메모리 및 디스크 용량을 확인 할 수 있고, 총 가상머신의 개수와 하이퍼바이저 종류를 즉시 볼 수 있습니다.

### 3. App 스토어

![Alt text](/assets/img/posts/sucloud-app.png)

Sucloud에서 기본적으로 제공하는 인스턴스 이미지들입니다. 현재 KVM용 qcow2 파일과 Hyper-v용 vhdx 파일을 제공하고있습니다.
각 인스턴스당 ubuntu 기반과 centos기반으로 접속 아이디가 설정 되어있습니다. 

![Alt text](/assets/img/posts/sucloud-app-detail.png)

각 인스턴스 이미지의 상세페이지에는 앱 사용 방법 및 접속방법이 자세하게 기술 되어있습니다. 또한 빨간 박스 안에 버튼클릭시 원하는 앱의 이미지를 받아 올 수 있습니다.


### 4. 인스턴스 (KVM, Hyper-v)

1. 인스턴스 리스트 페이지

![Alt text](/assets/img/posts/sucloud-root-instancelist.png)

root 계정으로 로그인하면 로그인한 호스트의 모든 팀의 인스턴스 리스트들을 확인 할 수 있다.

* 노란줄 : 팀명
* 초록 박스 : 인스턴스가 속한 그룹(인스턴스 그룹)

![Alt text](/assets/img/posts/sucloud-root-instancelist-status.png)
 
 인스턴스 리스트에서는 각각의 해당 인스턴스를 전원끄기, 전원켜기, 일시정지, 시작, 재부팅을 할 수 있다. 기본적으로 이미 실행이 되고 있다면 인스턴스는 전원끄기, 일시정지, 재부팅만 가능하다.

2. 인스턴스 상세페이지


![Alt text](/assets/img/posts/sucloud-root-instancelist-detail1.png)

인스턴스 이름을 클릭해서 들어가면 인스턴스 상세페이자가 나온다. 

인스턴스 상세페이지에서는 인스턴스의 자세한 정보를 얻을 수 있다.
``` 
 상태 : 인스턴스가 실행, 일시정지, 종료중인지 실시간으로 확인 할 수 있다.

 호스트 : 지금 실행 중인 인스턴스가 어느 호스트에서 생성이 되어있는지 알 수 있다.

 타입 : 인스턴스의 종류를 보여줍니다.

 IP 주소 : 인스턴스가 가지고 있는 내부 아이피를 보여줍니다.

 Public IP 주소 : 인스턴스가 가지고 있는 외부 아이피를 보여줍니다.

 운영체제 : 인스턴스의 OS를 보여줍니다.

 소유자 : 인스턴스의 소유자 이름이 표시됩니다.

 SSH 키 : 인스턴스에 연결되어있는 PEM 파일의 이름이 표시됩니다. (KVM 한정)

 그룹  :  인스턴스가 포함되어있는 그룹이 표시됩니다. 클릭시 그룹 이동 가능 

 포트 포워딩 : 인스턴스에 연결되어 있는 포트포워딩을 표시합니다. 
``` 
![Alt text](/assets/img/posts/sucloud-root-instancelist-detail2.png)

``` 
CPU : 인스턴스의 CPU사용량을 1분단위로 표시합니다(초단위로 설정가능)

MEMORY : 인스턴스의 Memory 사용량을 1분단위로 표시합니다.

DISK : 인스턴스의 Diks 사용량을 1분단위로 표시합니다.
``` 

![Alt text](/assets/img/posts/sucloud-root-instancelist-detail3.png)

``` 
백업 : 인스턴스를 설정 값에 따라 지정된 날짜에 [00:00] 자동으로 백업을 합니다.

소유권 이전 : 인스턴스의 소유권을 이전 할 수 있으며 관리자와 팀장 및 인스턴스를 소유자에 한합니다. (관리자는 팀과 팀을 이동 시킬 수 있습니다.)

삭제 : 인스턴스를 삭제 합니다. 모든 백업 데이터 및 설정이 삭제 됩니다.

``` 




