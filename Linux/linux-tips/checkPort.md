# checkPort

## 포트를 확인 할 수 있는 다양한 명령어들
   
Nucleo-F103RB 보드를 연결하고 ST-Link로 명령어 업로드 해준 뒤에 디버깅하기 위해 Serial port를 열려고 확인해봤는데, 생각해보니 내가 ubuntu에서 포트를 확인하는 방법을 몰랐다 ~~싸발...~~ 그래서 업로드하는 포트 확인 방법

### 마운트된 장비로 이동하는 방법
   
간단하다. <code>/dev/[사용자이름]/[포트이름]</code>으로 이동하면 끝임. 근데 이건 개인 데스크톱에서만 해당이 되지 서버와 같이 큰 컴퓨터는 이렇게 수동적으로 접근하지 않는다고 한다.

### Linux가 장치를 식별하는 방법
   
<code>/dev</code> 이 디렉터리에 저장된 특수한 파일로 장치를 파악한다고 한다.

### df
시스템에 연결된 각 장치와 마운트 지점을 보려면 df 명령 (Linux 디스크 공간 사용률 확인)을 사용할 수 있다.

```sh
df -h
```

### lsblk
다음과 같이 시스템에 연결된 모든 블록 장치를 나열하는 lsblk 명령 (list block devices)을 사용할 수도 있다.

```sh
lsblk
```

### fdisk
fdisk는 모든 블록 장치 (USB 드라이브 포함)에 파티션 테이블을 인쇄하는 강력한 유틸리티. 다음과 같이 루트 권한을 실행할 수 있다.

```sh
sudo fdisk -l
```
### dmesg
dmesg는 커널 작업에 대한 정보를 저장하는 데이터 구조 인 커널 링 버퍼를 인쇄하거나 제어하는 중요한 명령.

```sh
dmesg
```

보드 포트 확인할 때는 이 명령어로 겨우 /dev/ttyACM0 인걸 알아냄;;

