# 리눅스의 이해

## 리눅스의 개요

### 리눅스의 특징 및 장단점
__특징__

- **오픈 소스 운영체제!**(소스코드 및 모든 관련 자료가 공개되어 있는 운영체제)
- **MultiUser(다중 사용자),** **MultiTasking(다중 작업)** 운영체제!
  - MultiUser Function: 여러 사용자가 동시에 동일한 시스템에 접근이 가능함
  - MultiTasking: 여러 개의 Task를 동시에 실행하고, 교대로 컴퓨터의 자원을 사용할 수 있는 기능이다.
  - 가상 터미널 환경으로 하나의 모니터에 여러 개의 가상 화면(가상 콘솔)을 두어 화면마다 다른 작업이 가능하다(ex: Terminator)
- **다중 스레드를 지원하는 네트워크 운영체제!**
  - 하나의 프로세스 내에서 여러 개의 네트워크 작업을 동시에 처리할 수 있기 때문에 강력한 네트워크 지원 가능!
  - 인터넷과 이더넷에 안정적인 연결이 가능하다.
  - 이 때문에 네트워크 서버로 사용이 완전 가능하며 웹 브라우저, 메일, 뉴스, 웹 서버 등의 모든 인터넷 서비스 기능을 갖추고 있다.
- **여러 종류의 파일 시스템을 지원**하는 운영체제!
  - 리눅스의 기본 파일 시스템
    - ext2, ext3, ext4
  - DOS
    - FAT
  - Windows
    - FAT3, NTFS
  - 네트워크 파일 시스템
    - SMB, CIFS, NFS
  - 이외 등등 여러 파일시스템 지원!(추가로 설치 가능!)

__장단점__

- **리눅스는 유닉스와 완벽하게 호환이 가능함!**
  - 리눅스는 POSIX(Portable Operating System Interface UNIX) 규격을 따르고 있다.(근데 POSIX 재단은 특이하게 Linux를 인정 안해줌... 인정한 OS는 대표적으로 Mac등이 있음)
  - 리눅스는 POSIX 표준화를 기반하기 때문에 유닉스 소스코드를 전혀 사용하지 않고 개발되었다.
  - 유닉스용 프로그램은 별도의 수정 없이 리눅스에서 동작할 수 있다.
- **리눅스는 다른 PC용 OS보다 안정적!**
  - 일반 PC는 업무가 끝나면 전원을 끄지만, 리눅스는 네트워크 사용을 전제로 설계되었기에 특별한 사항을 제외하고 항상 켜 놓아도 안정적으로 운영된다!
  - 리눅스 시스템은 **네트워크 기반**하의 멀티유저, 멀티태스킹이 가능하여 많은 작업자가 동시에 사용해도 안정적인 시스템 운영이 가능함!
- **하드웨어 기능을 효과적으로 사용한다!** (개인적으로 선호하는 부분)
  - 다른 OS보다 적은 양의 메모리를 필요로 한다.
  - *SWAP 방식*을 통해 램(RAM)이 부족한 경우 Swap 영역을 늘려 메모리의 효율성을 높일 수 있다!
- **오픈소스 운영체제!**
  - 많은 인재가 확보되어 있기에 우수한 소프트웨어 개발이 가능하고, 여러 배포판 개발 업체들이 있어 사용자에게 **넓은 선택권**이 주어짐!
  - 다양한 배포판들이 존재하여 OS뿐만 아니라 여러 가지 유틸리티 프로그램과 응용 프로그램들을 사용자 편의에 맞춰 **무료**로 사용할 수 있다!
- **공개 OS이기 때문에 문제점 발생 시 기술 지원을 받는 데 한계가 있음!**
  - RHEL, SUSE과 같은 몇몇 엔터프라이즈용 리눅스들은 기술지원이 유로로 제공되고 있으나 대부분은 예상치 못한 오류 발생 시 개발자들의 기술 지원을 직접적으로 받는 것은 불가능하다!
- **한글 지원이 미흡**
  - 배포판마다 별도의 한글 지원 패키지를 설치해야 하지만 개인적으로 크게 중요하다고 생각치 않은 부분
- **보안상의 취약점이 쉽게 노출될 가능성이 있음!**
  - 공개 OS이기 때문에 보안에 취약할 것이라는 선입관이 있으나 꾸준한 기술 개발로 비교적 높은 보안성을 지원하고 있음!
  - 많은 프로그래머들이 리눅스를 연구하고 있기에, 보안 문제가 발생하였을 경우에는 신속하게 해결할 수 있음!

### 리눅스 디렉터리 종류와 특징

- 디렉터리란 파일 저장소를 의미함
- 리눅스 디렉터리는 최상위 디렉터리(/)를 기준으로 하위 디렉터리들이 존재하는 계층적 트리 구조로 구성되어 있음!
<img src="https://t1.daumcdn.net/cfile/tistory/262827345775C7AF22">
- 디렉터리 간에는 부모와 자식의 관계를 가지므로 상위 디렉터리와 하위 디렉터리는 부모 디렉터리와 자식 디렉터리로 나뉨
- 디렉터리별 저장 내용
  - /
    - 파일 시스템이 있는 최상위 디렉터리
    - 모든 디렉터리의 출발점인 동시에 다른 시스템과의 연결점이 되는 디렉터리
  - /boot
    - 부팅 시 커널 이미지와 부팅 정보 파일 저장
  - /proc
    - 시스템 정보 디렉터리이며 커널 기능을 제어하는 역할
    - 현재 실행되는 프로세스와 실제로 사용되는 장치, 하드웨어 정보 저장
  - /lib
    - 공유 라이브러리 디렉터리
    - 커널 모듈 파일들과 프로그램 실행을 지원해 주는 라이브러리 저장
  - /bin
    - 기본적인 명령어가 저장된 디렉터리
    - root 사용자가 일반 사용자가 함께 사용할 수 있는 명령어 디렉터리
  - /dev
    - 시스템 디바이스 파일들을 저장하는 디렉터리
    - 하드디스크 장치 파일, CD-ROM 장치파일 같은 파일 저장
  - /etc
    - 시스템 환경 설정 파일 저장 디렉터리
  - /root
    - 시스템 관리자용 홈 디렉터리
  - /sbin
    - 관리자용 시스템 표준 명령 및 시스템 관리와 관련된 실행 명령어 저장
  - /usr
    - 사용자 디렉터리로 사용자 데이터나 애플리케이션 저장
  - /home
    - 사용자 계정 디렉터리로 계정들의 홈 디렉터리가 위치함
    - 일반 사용자들이 로그인 시 처음으로 위치하게 되는 디렉터리
  - /var
    - 가변 자료 저장 디렉터리로 로그 파일이나 메일 데이터 저장
  - /tmp
    - 각종 프로그램이나 프로세스 작업을 할 때 임시로 생성되는 파일 저장
    - 모든 사용자에 대해서 읽기와 쓰기가 허용
    - 스티키 피트(sticky bit)설정으로 파일의 소유자만이 자신의 소유 파일 삭제 가능
  - /mnt
    - 파일 시스템을 일시적으로 마운트할 때 사용
  - /lost+found
    - 결함이 있는 파일에 대한 정보가 저장되는 디렉터리
- 좀 더 세부적인 디렉터리 설명
  - DIR /proc
    - 가상 파일 시스템
    - 시스템에서 운영되고 있는 다양한 프로세스들에 관한 내용과 프로그램에 대한 정보를 포함
    - 디렉터리에서 볼 수 있는 것은 실제 드라이브가 아니라 메모리 상에 저장되어 있음!
    - 사용자가 /proc나 하위 파일에 접근할 때마다 커널에서 파일 내용을 동적으로 만듦
    - 각 프로세스는 고유의 식별자를 가지고 있으며, 이 식별자를 가진 디렉터리 밑에 정보를 저장함
  - DIR /lib
    - 동적 공유 라이브러리를 저장하고 있음
    - 공유 라이브러리에는 많은 프로그램에서 공통으로 사용하는 함수들이 들어있어 디스크의 공간을 절약할 수 있으며, 프로그램마다 동일한 코딩을 할 필요 X
    - 라이브러리 공유 방법에는 정적 라이브러리와 동적 라이브러리 두 가지 방법이 있다.
    - 정적 라이브러리는 컴파일 과정에서 공유 라이브러리와 동적 라이브러리의 루틴을 사용하지 않고 프로그램 내에 라이브러리 루틴의 복사본을 갖도록 컴파일 한다.
    - 동적 라이브러리는 실행 파일 내부에 라이브러리를 넣어두지 않고 프로그램을 실행할 때 가져와 사용하므로 메모리 효율성이 높다!
  - DIR /dev
    - 하드디스크, 프린터, 입출력장치 등과 같은 장치들을 파일화하여 관리한다.
    - 특정장치를 실행하기 위해서는 해당 장치 파일을 실행해야 한다.
    - 장치 파일(device file) 또는 특수 파일(special file)은 장치 드라이버다.
    - 블록 장치 파일(block device)은 하드디스크, CD/DVD, 플로피 디스크와 같은 저장 장치들을 의미
    - 문자 장치 파일(character device)은 키보드, 마우스, 테이프, 모니터, 프린터 등의 같은 입출력장치들이다.
    - 리눅스의 표준 입력장치는 키보드이며, 표준 출력장치는 모니터이다.
  - DIR /etc
    - 시스템 환경설정 파일과 부팅 관련 스크립트 파일들이 저장되어 있는 디렉터리
    - 사용자 정보 및 암호 정보 파일, 보안 파일등을 저장
      - /etc/group : 그룹의 정보가 담겨 있는 파일
      - /etc/passwd : 자원을 사용할 수 있는 사용자 목록 저장
      - /etc/shadow : /etc/passwd의 두 번째 필드인 패스워드 부분을 암호화 관리 ; 패스워드 만기일, 계정 만기일 등을 설정
  - DIR /usr
    - 시스템이 아닌 일반 사용자들이 사용하는 디렉터리
    - 공유 가능한 프로그램들이 설치되며, 네트워크를 이용해서 여러 개의 시스템을 연결할 경우 이 디렉터리를 공유하여 설치된 프로그램을 활용할 수 있음!
    - /usr 디렉터리는 읽기 전용으로 마운트 되어야 하며, 가변 자료들은 /var 디렉터리로 심볼릭 링크로 사용하게 된다.
  - DIR /var
    - 시스템에서 사용되는 가변적인 파일들을 저장하는 디렉터리
    - 가변적인 파일들로는 로그파일, 스풀링(spooling), 캐싱(caching)등이 있음
  - DIR /lost+found
    - 파일 시스템의 이상 유무를 진단하고 복구하는 fsck에 의해서 사용되는 디렉터리
    - 손상된 파일이나 디렉터리를 /lost+found 디렉터리에 연결한 뒤에 오류를 수정하게 되며 평상시에는 null 파일 링크에 의해서 빈 상태로 존재한다.
    - 리눅스 파일 시스템 ext2에 의한 fsck, ext2 프로그램도 이 디렉터리를 사용한다.

### 리눅스 배포판
   
__특징__
- 리눅스 배포판은 리눅스 전체 시스템을 구성하는 소프트웨어 패키지 형태
- 리눅스 커널, GNU 소프트웨어 및 여러가지 자유 소프트웨어로 구성된 OS
  - 운영체제는 리눅스 커널과 GNU 프로젝트에서 가져온 라이브러리와 유틸리티, X 윈도우 시스템의 그래픽으로 구성되며, 워드프로세서, 스프레드시트, 미디어 플레이어, DB(최상위 응용단) 등 여러가지 소프트웨어 애플리케이션들도 포함하고 있다.
- 전 세계에 300여 가지의 배포판이 있으며, 배포판을 구성하는 SW도 자유롭게 구상되어 있다.
  - 용량을 맞춰서 X 윈도우를 빼거나 용량이 작은 GNU 유틸리티를 선택하기도 한다.(종류에 따라 다름!)

__종류__
- **슬랙웨어 리눅스(Slackware Linux)**
  - 배포판 가운데 가장 먼저 대중화된 배포판, 1992년 패트릭 볼커딩에 의해 출시
  - 최근 패키지 관리의 문제점으로 인기가 다소 떨어짐
  - 구조가 간결하고 파악하기 쉬워 유닉스 학습에 리눅스를 사용하고 싶은 사용자들에겐 적합
- **데비안(Debian)(중요)**
  - 1994년 이안머독(Ian Murdock)에 의해 비영리 조직으로 데비안 프로젝트를 설립함
  - 데비안 프로젝트에서 만들어 배포하는 공개 OS로 GNU의 공식적인 후원을 받고 있는 유일한 배포판
  - 종류
    - **리눅스(Linux) 커널을 탑재한 데비안 GNU/리눅스(현재 유일하게 정식판 존재)**
    -  GNU 허드(GNU Hurd) 커널을 탑재한 데비안 GNU/허드
    -  FreeBSD 커널을 탑재한 데비안 GNU/KFreeBSD
    -  NetBSD 커널을 탑재한 GNU/NetBSD 등
 -  데비안은 패키지 설치 및 업그레이드의 과정이 단순함!
    -  Install 후 패키지 매니저인 **apt**등을 이용하면 소프트웨어의 설치나 업데이트에서 다른 패키지와의 의존성 확인, 보안관련 업데이트 등을 자동으로 해줌!
-  **우분투(Ubnutu)**
   -  Debian GNU/Linux에 기초한 OS
   -  고유한 데스크탑 환경인 유니티를 사용하는 리눅스 배포판
   -  영국에 기반을 둔 회사인 캐노니컬의 지원을 받음
   -  여섯 달마다 새 버전이 하나씩 배포(LTS 버전은 2년), GNOME의 새 버전이 나오는 시기와 비슷
   -  사용자 편의성에 초점을 맞추고 있음! -> 현존하는 모든 리눅스 배포판 중에 가장 편의성이 뛰어나다고 생각함
-  **레드햇(Red hat)**
   -  미국의 레드햇사가 개발하던 리눅스 배포판
   -  현재는 유로로 기술지원을 하는 기업용 Rad hat Enterprises Linux(RHEL)와 페도라 프로젝트에서 개발하고 있는 페도라로 나누어져 있음!
   -  레드햇은 기업용 유료 리눅스 배포판인 RHEL의 개발을 지원함(몇년전 레드햇은 IBM에게 흡수당함)
-  **RHEL**
   -  레드햇이 개발하여 판매하고 있는 상용 리눅스 배포판
   -  18~24개월에 한 번씩 새로운 버전이 공개되며 라이선스는 별도 판매 X
   -  서브 스크립션의 형태로 요금을 지불하는 방식으로 계약
   -  기술 지원은 버전마다 출시 시점으로부터 7년 동안 제공
   -  계약기간 중에는 추가 비용 없이 업그레이드 및 다운그레이드를 자유롭게 실시 가능
   -  상업용 패키지는 구입해야 하지만 소스코드는 레드햇의 FTP 사이트를 통해 공개함
-  **패도라(Fedora)**
   -  리눅스 커널에 기반한 OS와 레드햇의 후원과 개발 공동체의 지원 아래 개발된 배포판
   -  일반적인 목적을 가진 RPM 기반의 SW가 결합된 OS
   -  6개월 간격으로 새로운 버전이 배포되며 지원기간은 각 버전마다 13개월
   -  SW 개발이 안정적으로 이루어지기 위해서는 새 버전으로 계속 교체되어야 한다는 단점 존재
-  **CentOS(리눅스마스터 실기는 이걸로 함)**
   -  업스트림 소스인 Rad hat Enterprises Linux와 완벽하게 호환되는 무료 기업용 Computing OS
   -  플랫폼을 제공할 목적으로 만들어짐
   -  자체 커뮤니티에 의해 관리
   -  기본적으로 포함하는 SW와 업데이트 되는 SW를 아울러 이전 파일에 대해 상위판과 100%에 최대한 가까운 호환성을 유지하는 것을 원칙
   -  레드햇의 기술 지원은 X
-  **수세(SUSE)**
   - 독일에서 출시된 배포판, 유럽에서 인기
   - 풍부한 기능과 안정성, 보안 기능 포함
   - 정기적인 배포판보다는, 언제든지 새로운 버전 출시시 업데이트가 가능한 롤링 릴리즈(Rolling Release)방식 사용
   - 오픈 수세, 수세 엔터프라이즈 리눅스로 나뉨