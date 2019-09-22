---
layout: post
title: 리눅스 shell 스크립트 실행 python 실행시 인자값 포함 실행하기 
description: > 
---

리눅스 쉘 스크립트 실행으로 파이선을 실행하는경우 파이선 실행시 필요한 인자값이 존재한다.
리눅스 파일실행 -> 조건에 맞는 파이선 실행 + 인자값 전달
아래의 예제를 보고 쉽게 작성할 수 있다.

### Test.sh 
~~~
#!/bin/bash

echo "param count : $#"
echo "Test01.py call"
python Test01.py $1 $2 $3 #받은 인자값을 3개 파이선으로 넘겨 실행하기
~~~

### Test01.py 
~~~
import sys

print("sys.argv[2] :", sys.argv[2]) #두번째 변수 값 출력하기
~~~

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