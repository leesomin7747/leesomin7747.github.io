---
layout: post
title: Bandit Level 0-1 풀이
date: 2026-05-12T17:46:59.373Z
categories: Security
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
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 1-2

**목표:** - 파일 열기

**풀이:** - 는 제대로 인식이 안 되기 때문에, 파일명이라는 것을 명시해주기 위해 cat ./- 사용

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

**배운 점:** ...

---

## Level 2-3

**목표:** --spaces in this filename-- 파일 열기

**풀이:** - 와 공백을 입력하기 위해 "./--spaces in this filename--" 사용

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
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
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 5-6

**목표:** 조건에 맞는 파일 찾기

**풀이:** 파일이 특정되는 조건을 이용해 찾기

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
find . -type f -size 1033c

```

---

## Level 6-7

**목표:** 조건에 맞는 파일 찾기(2)

**풀이:** 파일이 특정되는 조건을 이용해 찾기

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
find / -type f -size 1033c -user bandit7
```

---

## Level 7-8

**목표:** 파일 속 특정 단어 찾기

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
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
ssh bandit9@bandit.labs.overthewire.org -p 2220
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
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 12-13

**목표:** 다중 압축 해제

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

![](/assets/images/2026-05-13-10-56-53.png)

---

## Level 12-13

**목표:**

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 12-13

**목표:**

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 12-13

**목표:**

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---

## Level 12-13

**목표:**

**풀이:**

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

---
