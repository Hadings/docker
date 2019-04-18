#java 8 install 

```
java -version
javac
java가 설치 되어있지 않을 경우 
#yum으로 설치 가능한 jdk 목록 확인
yum list java*jdk-devel

#OPEN JDK 1.8.0 설치
yum install java-1.8.0-openjdk-devel.x86_64

#java version 확인
java -version

#java 위치 확인
which javac

#readlink -f는 심볼릭 링크로 이루어진 javac명령어의 물리위치를 찾아내는 방법
readlink -f /usr/bin/javac

-/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.181-3.b13.el7_5.x86_64/bin/javac

#환경변수 등록을 위하여 /etc/profile 파일을 편집
vi /etc/profile

#맨 아래에 추가
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.181-3.b13.el7_5.x86_64/bin/javac

#환경변수 확인
source /etc/profile
echo $JAVA_HOME
```
