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

``` 인스턴스 이름 수정 ```

![Alt text](/assets/img/posts/sucloud-root-instancelist-detail-name.png)

인스턴스의 이름을 바꾸고 싶을 경우 인스턴스 상세페이지에서 인스턴스 이름을 클릭하거나 인스턴스 이름 옆에 있는 연필 아이콘을 클릭하면 모달 창에서 수정가능합니다.

``` 인스턴스 태그 수정 ```

![Alt text](/assets/img/posts/sucloud-root-instancelist-detail-tag.png)

인스턴스의 태그을 바꾸고 싶을 경우 인스턴스 상세페이지에서 인스턴스 태그를 클릭하거나 인스턴스 태그 왼쪽에 연필 아이콘을 클릭하면 모달 창에서 수정가능합니다.

![Alt text](/assets/img/posts/sucloud-instancelist-detail-ip.png)

IP설정 버튼을 클릭 할 시 나오는 모달 창입니다. (시스템 설정에서 IP제외 게이트웨이 IP 대역, 및 서브넷마스크가 설정이 되어있어야합니다.)
원하는 아이피를 넣거나 *AUTO*를 넣어주시면 됩니다. AUTO 셋팅시 같은 대역대의 비어있는 제일 작은수의 IP가 설정 됩니다.


``` 인스턴스 그룹 수정 ```

![Alt text](/assets/img/posts/sucloud-root-instancelist-group.png)

보여지는 그룹을 클릭 할 시 수정할 수 있는 모달이 나옵니다. 팀내에 있는 그룹 어디든지 옮겨 놓을 수 있습니다.

``` 인스턴스 포트포워딩 ```

![Alt text](/assets/img/posts/sucloud-root-instancelist-detail-port.png)

인스턴스에 접속할 수 있거나 웹페이지에 연결 가능하도록 하는 포트포워드 기능입니다.
처음에 CUSTOM 이나 RDP, HTTP, SSH의 설정을 기본적으로 제공하고있으며 자신이 원하는 원본포트를 적어 사용할 수 있습니다.

원본포트는 인스턴스에서 열 포트이고 외부포트는 호스트에 열 포트입니다. 기본적으로 AUTO로 설정 되어있으나 자기가 원하는 포트로 설정 할 수 있습니다 (3306, 443 등 기본적으로 안되는 포트 존재) 타임아웃은 그 시간동안 아무 입력이 없으면 자동적으로 연결을 끊어버리게 되어있습니다.(7200초를 추천 드립니다.)

### 5. 이미지 

1. Virtual Machine

![Alt text](/assets/img/posts/sucloud-root-instancelist-img.png)

호스트에 생성이 가능한 이미지를 표시해줍니다. (Hyper-v 또는 KVM)

2. Snapshot

![Alt text](/assets/img/posts/sucloud-root-instancelist-snap.png)

인스턴스들의 스냅샷을 찍을 수 있는 페이지입니다. 해당아이디의 소유자만 인스턴스를 만들 수 있고 팀내의 팀장이 모든 인스턴스들의 권한을 가질 수 있습니다. (관리자 불가)

또한, SnapShot List 에서는 인스턴스 스냅샷에 대한 정보를 확인 할 수 있습니다.

3. BackupList

![Alt text](/assets/img/posts/sucloud-root-instancelist-backup.png)

팀내의 인스턴스에 대한 백업 정보입니다. 백업한 날짜와 시간 및 인스턴스 이름 소유자만 표시합니다.
삭제는 기본 인스턴스 백업 정책에 따라 삭제가 되며 임의로 삭제 하실 수 없습니다.


### 6. 관리자 계정 관리


![Alt text](/assets/img/posts/sucloud-root-account.png)

header 부분의 오른쪽 이름을 클릭하시면 dropdown 형태로 계정에 대한 정보가 보입니다.

```
 첫 줄 : 계정의 이름이 보입니다.
 
 My team : 계정이 속해 있는 팀에 대한 정보 및 SSH키를 다운로드 할 수 있습니다.

 Account Setting : 계정에 대한 비밀번호, 연락처, 이메일등을 수정 가능합니다.

 Logout :  보인 그대로의 기능

```

1. 팀 관련 정보 및 RDCMan 파일 다운로드 

![Alt text](/assets/img/posts/sucloud-root-account-myteam.png)

계정이 속한 팀에 대한 정보를 보여주며 팀원들, 팀 인스턴스 그룹을 보여줍니다. 
마지막으로 Hyper-v을 사용 하실 경우에는 접속을 위한 rdg 파일을 다운로드 받을 수 있습니다. 
* RDG 파일은 원격접속을 위한 파일이며 팀내에 위치한 모든 Hyper-v 인스턴스들이 그룹별로 묶여 접속정보들을 저장한 파일입니다.

2. 계정이 속한 팀 정보 및 SSH키 리스트

![Alt text](/assets/img/posts/sucloud-root-account-myinfo.png)

계정 이름과 아이디 및 연락처를 확인 할 수 있습니다. 수정을 누를 경우 계정에 대한 정보를 수정할 수 있습니다.
또한, SSH키를 다운로드 받을 수 있습니다.

![Alt text](/assets/img/posts/sucloud-root-account-myinfo-change.png)

아이디와 이름을 제외한 모든 것을 수정 할 수 있습니다.

 
### 7. 시스템 설정

1. 시스템 프로필

![Alt text](/assets/img/posts/sucloud-root-system-profile.png)

```
sucloud 플랫폼에 대한 정보입니다.

1번 박스는 최신버전으로 업데이트 할 수 있는 버튼입니다.

2번 박스는 제품등록을 위한 곳입니다. 제품등록이 안되어있을 경우 나타납니다.

```
2. 시스템 팀관리 

![Alt text](/assets/img/posts/sucloud-root-system-team.png)

관리자에서 모든 팀을 볼 수 있습니다. 
팀명, 팀 관리자, 팀원이 몇명인지 표시됩니다.
리소스는 현재 사용중인 인스턴스에 대하여 나타냅니다.

![Alt text](/assets/img/posts/sucloud-root-system-team-info1.png)

팀에 관련하여 모든 정보가 표시됩니다. 사용중인 리소스 및 팀에 할당 되어있는 리소스를 수정 할 수 있습니다. (팀명 수정 및 리소스 제한 가능)


![Alt text](/assets/img/posts/sucloud-root-system-team-info2.png)

팀원들의 상태 리스트를 표시합니다. 팀원들의 등급, 비밀번호, 탈퇴 를 기능이 있습니다.

팀을 완전히 삭제가 가능하며 팀 삭제 시 팀에 연관된 모든 정보 및 인스턴스, 백업 데이터 등은 모두 삭제되어 없어지기 때문에 삭제시 신중해야합니다.

3. 클러스터 관리

![Alt text](/assets/img/posts/sucloud-root-system-cluster.png)

호스트를 연결 할 수 있습니다. 일반적으로 ALL-in-one 모델 일 경우 컨트롤러와 노드의 IP는 동일합니다. 노드는 여러개로 추가가능 합니다.

4. 이미지 관리

![Alt text](/assets/img/posts/sucloud-root-system-img.png)

등록되어있는 이미지들을 보여줍니다. 가상머신 이미지와 컨테이너 이미지를 등록 또는 삭제 할 수 있습니다. 삭제시 이미지에 연결되어 있는 이미지 파일을 삭제 또는 데이터베이스에서만 삭제 할 수 있도록 선택할 수 있습니다.

![Alt text](/assets/img/posts/sucloud-root-system-img-add.png)

이미지 등록 화면입니다. (파일 선택은 사용 불가)

타입은 Hyper-v 인지 KVM 인지 선택을 해줘야합니다. (Hyper-v 와 KVM은 기본적으로 파일 확장자가 다릅니다.)

이름은 원하시는 이름을 적어주시면 되고, OS는 저희가 제공하는 이미지에 이름이 있는데 **Centos 기반이면 centos, 우분투 기반이면 Ubuntu를 입력해 주셔야합니다.**

버전과 비트는 이미지에 맞게 입력하시면 되고, 비트는 이미지에 표시 되어있지 않으면 64비트를 기본으로 합니다.

파일명은 현재 베이스 이미지가 연결되어있는곳에 있는 파일을 나타내주며 연결하실 이미지를 선택하시면 됩니다.

5. 리소스 단위 관리

![Alt text](/assets/img/posts/sucloud-root-system-resource.png)

인스턴스 생성 시 리소스 단위를 등록하는 곳이다. 코어, 메모리 및 디스크 용량을 설정 할 수 있으며 삭제 할 수 도있다. 최대 코어, 메모리, 디스크 제한은 없으나 호스트의 스펙에 따라 적절히 사용하는 것을 추천한다.

6. 로그인 이력 조회 및 사용 이력 조회

![Alt text](/assets/img/posts/sucloud-root-system-loginhis.png)

로그인 이력을 조회 할 수 있다.

![Alt text](/assets/img/posts/sucloud-root-system-usehis.png)

인스턴스 생성 내역 등 사용자의 사용내역을 조회 할 수 있다.

7. 백업 및 장애 현황

![Alt text](/assets/img/posts/sucloud-root-system-backup.png)

전체 팀의 백업 현황과 장애를 확인 할 수 있는 페이지이다.

8. 설정

![Alt text](/assets/img/posts/sucloud-root-system-setting.png)

대부분의 기능을 설정 할 수 있는 공간입니다. 

 * 과금

 ![Alt text](/assets/img/posts/sucloud-root-system-setting-invoice.png)

> 인스턴스 사용량의 요금 관리 기준입니다. (사용할 수 없음)

* 백업

![Alt text](/assets/img/posts/sucloud-root-system-setting-backupweek.png)

> 자동 백업 주기를 설정 할 수 있다. 일별 및 요일별, 백업 보존기간등을 설정한다. 

* 공인아이피 연결설정

![Alt text](/assets/img/posts/sucloud-root-system-setting-ipset.png)

> Public IP를 설정 하기 위해서 선행 되어야하는 설정입니다. IP 대역 (ex]192.168.0) 처럼 셋팅을 해줘야합니다.
> Gateway나 Subnetmask는 맞게 설정하면 됩니다.

* 포트 포워딩 설정

![Alt text](/assets/img/posts/sucloud-root-system-setting-portdomain.png)

> Sucloud가 연결되어있는 IP나 도메인 주소를 입력하면 된다. 
> 입력시 인스턴스 상세페이지에서 연결된 도메인 주소가 나온다.

* 서브 도메인 설정

![Alt text](/assets/img/posts/sucloud-root-system-setting-subdomain.png)

> 도메인이 연결되어 있다면 서브도메인으로 인스턴스를 연결해서 사용할 수 있다. 단, sucloud IP가 *.domain 으로 연결이 되어있어야한다.
> ex] [subdomain].domain주소

* 모니터링 주기 설정

![Alt text](/assets/img/posts/sucloud-root-system-setting-matric.png)

> 인스턴스들의 상태 모니터링 주기를 설정 할 수 있습니다. 기본 초단위로 설정 할 수 있으면 기본 세팅은 1분입니다.

* Slack 봇 설정

![Alt text](/assets/img/posts/sucloud-root-system-setting-slack.png)

> 인스턴스 생성, 실패 등 모든 에러를 슬랙봇 알람으로 받을 수 있게 설정 됩니다. 기본으로는 저희 유지 보수를 위해 씁니다. 하지만 슬랙을 사용하고 알림을 받고 싶으면 설정이 가능합니다.