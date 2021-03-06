# Linux install and types

## Linux install

### 리눅스 설치를 위한 하드웨어 정보 파악
   
__하드웨어 정보__

- 최근 리눅스 배포판들은 하드웨어 호환성이 우수함
- 설치 마법사의 Plug and Play(PNP) 기능으로 자동으로 하드웨어를 찾아냄
- 설치 전에 하드웨어에 대한 정보를 알아두는 것이 설치 작업을 용이하게 한다.(이건 ㅇㅈ)
- 하드웨어 정보 파악은 하드웨어 문제가 발생했을 때 장애처리의 실마리가 될 수 있음
  - CPU
    - 제조사와 모델명 확인
      - 32비트 CPU 또는 64비트 CPU 파악
      - 가상화 환경에서는 CPU의 물리적 개수와 코어(Core) 개수 확인
    - 메모리(RAM)
      - 메모리 용량 확인
      - SWAP 파티션 설정 시 사용
    - 하드디스크 드라이브
      - 하드디스크의 파일명 확인
        - IDE 또는 ATA 하드디스크 타입 파일명: /dev/hdX
        - S-ATA, USB, SSD, SCSI 하드디스크 타입 파일명: /dev/sdX
    - 네트워크 인터페이스
      - 제조사, 모델명, 유무선 여부, 어댑터 종류
      - TCP/IP 속성 정보 확인
- 필요한 시스템 정보를 얻을 수 있는 방법은 다음과 같음
  - 시스템 구매 시 받은 제품 설명서~~(MCU는 칩 사면 딸려오는 도함 2000장 레퍼런스 읽으면 됨 ㅋ)~~
  - BIOS 설정 화면
  - 장치 관리자(Windows)
  - 시스템 정보 수집 프로그램 사용
- 시스템이 네트워크에 연결되어 있는 상태라면 네트워크 정보를 정확히 기록해 둔다.
- 시스템의 이름 정보(호스트 이름, 도메인 이름)와 TCP/IP 주소 정보(IP 주소, 넷마스크, 게이트웨이 주소, DNS 주소)가 필요하다

__하드웨어 호환성__
  
- 리눅스는 많은 하드웨어 제품들에서 문제없이 작동하지만 다른 OS들만큼 다양한 종류의 하드웨어에서 동작하지 못한다...?(리눅스가 더 호환성 좋은거 아님? 아닌가 드라이버 패키지는 윈도우가 더 좋나)
- 하드웨어 호환성은 다음의 방법으로 확인 가능
  - 제조사의 웹사이트에서 새 드라이버 확인
  - 웹사이트와 매뉴얼에서 에뮬레이션에 대한 정보 탐색
    - 덜 알려진 상표의 제품이 더 많이 알려진 제품의 드라이버와 설정들을 그대로 사용
  - 해당 아키텍처에 관한 웹사이트에서 리눅스 하드웨어 호환성 목록 확인

### 리눅스 설치 관련 정보들

__CentOS 7__

- CentOS 7부터 커널 3.X 이상을 사용하며, 프로세서 아키텍처는 x86_64 만 지원한다.(나머지는 구버전)

__커널(Kernel)__

- 운영체제의 핵심 부분으로 CPU나 메모리, 기타 디바이스 등의 시스템 자원을 관리하고 사용자 프로그램이 사용할 수 있도록 한다.
- 커널 버전은 검증이 완료된 안전 버전과 개발 중인 개발 버전으로 나뉜다.
- 커널명은 '주버전.부버전.패치버전'으로 구성된다.
  - ex) 3.10.17.1 (맨 끝 번호는 안전 버전 일련번호로, 안전 버너에서만 사용된다.)
  - 부버전이 짝수이면 안정 커널이고, 홀수이면 개발 커널이다.

__날짜와 시간__

- 시스템의 시간대를 수동으로 설정
- NTP(Network Time Protocol) 기반으로 네트워크를 통해 컴퓨터 시스템 간 시간 동기화를 자동 설정 가능
  - NTP는 네트워크에 분산된 다수의 시스템들의 시간을 동기화하는 프로토콜
  - 네트워크상에서 서로 연동하는 시스템들 간에 시간이 일치하지 않을 시 시스템들의 장애 처리나 성능 카운터, 분석 또는 로깅 등에서 문제가 발생

