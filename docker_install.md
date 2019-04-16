Centos7-Docker 설치 및 실행
=============

#### 1.Docker 기본 설치

```
# 1.yum 패키지 업데이트

yum -y update

# 2. Docker & Docker Registry 설치

yum -y install docker docker-registry

```
#### 2.Docker 실행 및 자동(On Boot) 실행 서비스 등록

```
# 3. 부팅시에 실행 되도록 등록

systemctl enable docker.service

# 4. Docker 실행

systemctl start docker.service

# 5. systemctl 사용 Docker 스테이터스 확인

systemctl status docker.service
```

#### 3. Docker 컨테이너 다운로드

```
# 6. Docker 사용 준비 완료 후 hello-world

docker run hello-world

