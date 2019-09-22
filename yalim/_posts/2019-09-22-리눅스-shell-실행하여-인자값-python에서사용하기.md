---
layout: post
title: 리눅스 shell 스크립트 활용 하여 받은 인자값 python에 넘겨 실행하기 
description: > 
---

Test.sh 작성하기

### Test.sh 
~~~
#!/bin/bash

echo "param count : $#"
echo "Test01.py call"
python Test01.py $1 $2 $3 #받은 인자값을 3개 파이선으로 넘겨 실행하기
~~~

Test01.py 작성하기
### Test01.py 
~~~
import sys

print("sys.argv[2] :", sys.argv[2]) #두번째 변수 값 출력하기
~~~

Test.sh 실행하기
### Test.sh 실행하기 
~~~
./Test.sh start stop ing
~~~
### 결과값 확인 하기
~~~
param count : 3
Test01.py call
('sys.argv[2] :', 'stop')
~~~