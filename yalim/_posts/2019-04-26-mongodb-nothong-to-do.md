---
layout: post
title: 리눅스 mongodb 설치중 Nothing to do 을 만났을때
description: > 
---
ㅤㅤ

### 1.yum 으로 mongodb install
~~~yml
$ sudo yum install mongodb-org
Loaded plugins: priorities, update-motd, upgrade-helper
No package mongodb-org available.
Error: Nothing to do
~~~

### 2.Nothing to do 발생하는 경우 

이때는 repo 파일을 만들어줍니다.
파일명은 /etc/yum.repos.d/mongodb-org-3.4.repo 이고 내용은 다음과 같습니다.

~~~yml
[mongodb-org-3.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2013.03/mongodb-org/3.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.4.asc
~~~

### 3.yum 실행
~~~yml
파일 작성 후에 
sudo yum install mongodb-org
~~~



