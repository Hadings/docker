# elasticsearch_install

```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.4.0.tar.gz
tar -xvf elasticsearch-5.4.0.tar.gz cd elasticsearch-5.4.0/bin 
./elasticsearch
#elasticsearch 5.x 버전 부터는 root 권한으로 실행할 수 없음
#user 생성
useradd elastic
passwd elastic
chown -R elastic:elastic <elasticsearch 폴더>

#이제 실행 가능
./elasticsearch 
```
