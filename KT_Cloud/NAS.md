## NAS Volum mount

### NAS = 네트워크 결합 스토리지
```
CentOS 환경 = NFS
Windows 환경 = CIFS
```
```
CentOS 7 'NFS' 사용
```

#### NFS 기본 모듈 설치
```
yum install -y showmount
```

#### Mount 디렉토리 생성
```
mkdir [디렉토리 명]
```

#### Mount 할 수 있는 볼륨이 있는 지 확인 (NFS주소)
```
showmount -e 172.27.128.1
```

#### Mount : mount –t nfs [대상주소:/경로] [mount 할 디렉토리]
```
mount -t nfs 172.27.128.1:/testnass /root/mfss
```

#### Mount 상태 확인
```
df -h
```

#### Reboot 을 할 경우 NFS 볼륨이 해제 됨으로 /etc/fstab 에 아래와 같이 등록 해야 한다.
```
vim /etc/fstab

-- 맨밑에 아래내용 추가 --

172.27.128.1:testnass                     /root/mfss              nfs     auto            0 0
```