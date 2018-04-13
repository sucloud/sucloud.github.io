---
layout: post
title: Sucloud Debug 하는 방법
summary: how to debug sucloud platform
featured-img: emile-perron-190221
---

### Sucloud Debug 하는 방법 
 sucloud는 docker, python을 이용하여 개발되어있는 클라우드 플랫폼이다. 마이크로 아키텍쳐를 채용하여 모든 컨트롤러들이 분리되어있다.

 1. sucloud platform 시작 및 중지 재시작.

    - 본인이 sucloud-all-in-one을 설치 하였다면 $/root/sucloud-all-in-one/ 에 이동한 후
      docker-compose up -d : 시작
      docker-comppse down : 정지  할 수 있다.

    - 만약 docker 이미지만 받아 실행을 시켰다면 이미 docker에 능숙한자... 알 것이다..

2. sucloud logger 위치 및 확인

    ![Alt text](/assets/img/posts/sucloud-log.png)
    ![Alt text](/assets/img/posts/sucloud-log-all.png)
    - 기본적으로 /var/log/sucloud2 또는 /var/log/sucloud에서 확인 할 수 있다. 
    DownloadFileManager.log, down.log, k.log, manager.log, d.log, h.log, kvm.log, s.log, docker.log,
    hyperv.log, m.log, scheduler.log 등이 있다. 현재 Debug 단계에서부터 log를 출력하고 있기때문에 Error를 확인 할 떄 힘이 들 수 있다.

3. 포트 포워딩을 하였는데 접속을 할 수 없을 때 

    ![Alt text](/assets/img/posts/sucloud-port.png)
    - sucloud는 기본적으로 접속을 포트포워딩 후 인스턴스에 접속이 가능하다. 그래서 내부 원본 포트와 외부 bind포트가 존재한다.
    원본포트 또한 한 인스턴스에 여러개를 열어둘수 있지만 똑같은 포트를 다른 외부포트에는 연결 할 수 없다. 
    - 빨간 박스의 포트는 원본 포트, 초록 박스의 포트는 Bind 포트로 만약 bind포트가 3306, 22, 443이면 포트포워딩이 동작하지 않아 모든 포트 포워딩이 연결 되지 않을 수 있다.

    ![Alt text](/assets/img/posts/sucloud-port-info.png)
    - 포트포워딩이 동작을 안할 시 [접속주소]:9999/v1/config 로 접속하면 모든 포트포워딩의 정보가 한눈에 들어온다. 인스턴스 ID를 기반한 정보이기 때문에 만약 금지 포트가 bind 포트에 입력 되어있다면 그 인스턴스 상세페이지로 이동하여 포트포워딩되어있는 것을 삭제 해주면 포트포워딩의 기능은 정상적으로 돌아온다.

    ![Alt text](/assets/img/posts/sucloud-port-docker.png)
    - docker logs -f [docker ID or docker NAME] 을 하면 포트포워딩하는 모든 레벨의 로그들을 볼 수있다. 혹 에러가 있다면 빨간줄과 같이 쉽게 확인이 가능 할 것이다.

