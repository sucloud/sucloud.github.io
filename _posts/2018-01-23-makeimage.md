---
layout: post
title: SU클라우드 KVM이미지 제작방법
summary: sucloud kvm images
featured-img: 
---

### 1. SU클라우드 플랫폼 관리자
- SU클라우드 플랫폼 관리자를 이용하여 보다 쉽게 클라우드 이미지를 생성 할 수 있습니다
    - 각 버전별 CentOS, Ubuntu 등  인스턴스 생성
    - ssh로 VM 접속

        ```
        * 필요한 패키지 설치 및 초기 데이터 삭제
        rm -rf .ssh
        rm -rf /var/lib/cloud/instances/gncloud*
        ```
        
    - 관리자에서 VM 정지
    - 이미지 > 스냅샷 > 정지된 VM 선택 > 스냅샷 생성
    - ssh로 kvm 호스트 터미널 오픈 (root 계정)
        ```
        # 이미지 변환 및 압축
        $ cd /data/nas/images/kvm/snapshot
        # 최근에 생성된 스냅샷 이미지 이름 확인
        $ ls
        $ qemu-img convert -f raw -O qcow2 [스냅샷 이름(.img)] [원하는 이미지 이름(.qcow2)]
        $ virt-sparsify --compress [원하는 이미지 이름(.qcow2)] [압축된 이미지 이름.qcow2)]
        ```
    - 생성된 이미지를 /data/nas/images/kvm/base 로 이동
    - SU클라우드 플랫폼 관리자에서 이미지 관리 > 등록 (이미지 이름과 같아야 한다)

### 2. virt-manager
- libvirt를 통하여 kvm을 컨트롤 할 수 있으며, 세세한 부분 까지 세팅이 가능합니다.

    - 설치를 원하는 OS의 ISO파일 다운로드
    - virt-manager 실행
    - 파일 > 새 가상머신 > 로컬설치 매체 > ISO 파일 선택
        ```
        # SU클라우드 플랫폼의 pool은 두곳의 디렉토리
        /data/nas/images/kvm/instance
        /var/lib/libvert/images
        ISO 파일을 위의 디렉토리에 복사 또는 이동
        ```
    - virt-manager 화면에서 연결 하여 설치 마무리
    - ssh로 vm에 접속
        ```
        # 클라우드 이미지 사용을 위한 처리 (CentOS 7 기준)
        # ubuntu 는 http://sweet-rain.tistory.com/m/37 참조

        # 클라우드 생성 패키지 설치
        yum -y install cloud-init

        # root 계정으로 로그인 불가 설정
        vi /etc/ssh/sshd_config
        PasswordAuthentication no
        PermitRootLogin no

        # sudo 일때 비밀번호 입력 없이 사용 가능하도록 설정
        vi /etc/sudoers
        centos ALL=(ALL) NOPASSWD:ALL
        # w! 로 저장 후 :q!, sudo 할 경우 비밀번호 없이 바로 수행 가능

        # root 비밀번호 제거
        passwd -d root

        # cloud image 생성에 필요한 패키지 설치
        yum -y update
        yum -y install epel-release
        yum -y groupinstall "Development tools"
        yum -y install python-devel
        yum -y install python-argparse python-psutil python-pip
        pip install --upgrade pip
        pip install 'boto==2.5.2' heat-cfntools
        cfn-create-aws-symlinks --source /usr/local/bin
        shutdown -h now
        ```
    - ssh로 kvm호스트 터미널 오픈 (root 계정)
        ```
        # 이미지 변환 및 압축
        $ cd /var/lib/libvirt/images
        # 설치 시 지정한 파일 이름 확인
        $ ls
        $ virt-sparsify --compress [지정한 파일 이름(.qcow2)] [압축된 이미지 이름(.qcow2)]
        ```
    - 생성된 이미지를 /data/nas/images/kvm/base 로 이동
    - SU클라우드 플랫폼 관리자에서 이미지 관리 > 등록 (이미지 이름과 같아야 한다)


### 3. SU클라우드 플랫폼이 아닌 리눅스 호스트 경우
- https://github.com/gncloud/gncloud/blob/master/Install/gncloud-kvm-host/README.md 참조
- virt-manager 설치
    * yum -y install virt-manager
- virt-sparsify 설치
    * yum install libguestfs-tools