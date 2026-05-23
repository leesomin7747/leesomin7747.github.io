---
layout: post
title: Bandit Level 0-1 풀이
date: 2026-05-07 17:46:59 +0900
categories: Blog Docs
description: bandit0 입력
---

## Level 0

**목표:** SSH로 접속하기

**풀이:** 비밀번호 bandit0 입력

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 0-1

**목표:** readme 파일 열기

**풀이:** ls로 파일 구조 확인 후 cat readme

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 1-2

**목표:** - 파일 열기

**풀이:** - 는 제대로 인식이 안 되기 때문에, 파일명이라는 것을 명시해주기 위해 cat ./- 사용

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 2-3

**목표:** --spaces in this filename-- 파일 열기

**풀이:** - 와 공백을 입력하기 위해 "./--spaces in this filename--" 사용

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 3-4

**목표:** hidden 파일 열기

**풀이:** cat hidden 2-3

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 4-5

**목표:** human-readable 파일 찾기

**풀이:** ./-file01 부터 ./-file09까지의 파일이 존재하는데 다 열어볼 수는 없으니
file ./-\*를 사용해 속성을 확인함.

-file07만 아스키코드로 작성된 것을 확인한 후 파일 오픈

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

---

## Level 5-6

**목표:** 조건에 맞는 파일 찾기

**풀이:** 파일이 특정되는 조건을 이용해 찾기

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
find . -type f -size 1033c

```

---

## Level 6-7

**목표:** 조건에 맞는 파일 찾기(2)

**풀이:** 파일이 특정되는 조건을 이용해 찾기

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
find / -type f -size 1033c -user bandit7
```

---

## Level 7-8

**목표:** 파일 속 특정 단어 찾기

**풀이:**

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
grep millionth data.txt
```

![](/assets/images/2026-05-13-05-19-36.png)

---

## Level 8-9

**목표:**

**풀이:**
sort data.txt 같은 문자열끼리 인접하도록 정렬
uniq -u 딱 한 번만 등장한 줄을 출력

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
sort data.txt | uniq -u
```

![](/assets/images/2026-05-13-05-18-37.png)

---

## Level 9-10

**목표:** 특정 문자열로 이루어진 부분 찾기

**풀이:** strigs 파일 -> 바이너리 파일 안에서 읽을 수 있는 문자열만 추출

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
strings data.txt | grep "==="
```

![](/assets/images/2026-05-13-09-46-34.png)

---

## Level 10-11

**목표:** base64로 인코딩 된 문자열 찾기

**풀이:**

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
cat data.txt | base64 -d
```

![](/assets/images/2026-05-13-09-59-34.png)

---

## Level 11-12

**목표:**

**풀이:**

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

---

## Level 12-13

**목표:** 다중 압축 해제

**풀이:**

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

![](/assets/images/2026-05-13-10-56-53.png)

---

## Level 13-14

**목표:** SSH 키를 이용해 다음 단계로 넘어가기

**풀이:**

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
![](/assets/images/2026-05-13-19-45-32.png)
---

## Level 14-15

**목표:** 포트 번호 30000에 접속

**풀이:**

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
nc 0 30000
# 0: 로컬
```
![](/assets/images/2026-05-13-19-55-42.png)

---

## Level 15-16

**목표:** 

**풀이:**

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
openssl s_client -connect localhost:30001
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```
![](/assets/images/2026-05-13-20-01-19.png)

---

## Level 16-17

**목표:**

**풀이:**

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220

kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

---


## Level 17-18

**목표:** 두 파일의 차이 찾기

**풀이:**

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
diff passwords.new passwords.old

```
![](/assets/images/2026-05-13-20-37-30.png)

---
## Level 18-19

**목표:** SSH로 로그인 하자마자 명령 실행하기

**풀이:** 

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
![](/assets/images/2026-05-13-20-45-11.png)

---
## Level 19-20

**목표:** 

**풀이:**

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
ls /etc/bandit_pass/
./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```
![](/assets/images/2026-05-13-21-00-49.png)

---
## Level 20-21

**목표:**

**풀이:**

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220

EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```
![](/assets/images/2026-05-13-21-14-08.png)

---
## Level 21-22

**목표:** cronjob

**풀이:**

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220

tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```
![](/assets/images/2026-05-13-21-24-04.png)

---
## Level 22-23

**목표:** cronjob

**풀이:**

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220

0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```
![](/assets/images/2026-05-13-21-47-45.png)

---
## Level 23-24

**목표:** cronjob

**풀이:**

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220

gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

**STEP1**
![](/assets/images/2026-05-23-15-06-41.png)
```
- \* * * * * 매 1분마다
- bandit24 권한으로
- /usr/bin/cronjob_bandit24.sh 를 자동 실행
```

**STEP2**
![](/assets/images/2026-05-23-15-10-50.png)
```
/var/spool/bandit24/foo 폴더 안에 있는 파일 중 소유자가 bandit23인 파일을 찾아서 bandit24 권한으로 실행한 뒤 삭제함
```

**STEP3**
![](/assets/images/2026-05-23-15-23-18.png)

---
## Level 24-25

**목표:**
```
포트 30002에 접속
bandit24 비밀번호 + 핀코드 형식으로 입력
핀코드는 0000~9999 전부 시도
연결은 한 번만 하고 계속 입력 가능 → 스크립트로 자동화해야 함
```

**풀이:**

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220

iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```
**STEP1**
nano 편집기로 브루트포스 스크립트 작성
```
$ nano /tmp/mydir24/brute.sh

#!/bin/bash
for i in $(seq -w 0000 9999)
do
    echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"
done | nc localhost 30002
```

**STEP2**
![](/assets/images/2026-05-23-16-00-39.png)
```
저장 후 실행
bash /tmp/mydir24/brute.sh
```

---
