---
title: "[프로그래머스] 7daySQL 챌린지 Day 2"
layout: post
date: '2019-09-03 00:00:00'
image: "/assets/images/profile-round.png"
headerImage: true
tag:
- MySQL
- Programmers.kr
- 7daySQL
category: blog
author: ry4nkim
description: 7daySQL 챌린지 Day 2 - 아픈 동물 찾기, 어린 동물 찾기
---

## Summary:

[프로그래머스] 7daySQL 챌린지 Day 2

### Index
- [아픈 동물 찾기](#아픈-동물-찾기)
- [어린 동물 찾기](#어린-동물-찾기)

---
## 아픈 동물 찾기

출처 : [프로그래머스 # 코딩테스트 연습 - 아픈 동물 찾기](https://programmers.co.kr/learn/courses/30/lessons/59036){:target="_blank"}

### 문제

`ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. `ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

<div class="table-wrapper" markdown="block">

| NAME             | TYPE       | NULLABLE |
|------------------|------------|----------|
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| INTAKE_CONDITION | VARCHAR(N) | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_INTAKE  | VARCHAR(N) | FALSE    |

</div>

동물 보호소에 들어온 동물 중 아픈 동물[^1]의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.

[^1]: INTAKE_CONDITION이 Sick 인 경우를 뜻함

### 예시

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|----------|-----------------|
| A365172   | Dog         | 2014-08-26 12:53:00 | Normal           | Diablo   | Neutered Male   |
| A367012   | Dog         | 2015-09-16 09:06:00 | Sick             | Miller   | Neutered Male   |
| A365302   | Dog         | 2017-01-08 16:34:00 | Aged             | Minnie   | Spayed Female   |
| A381217   | Dog         | 2017-07-08 09:41:00 | Sick             | Cherokee | Neutered Male   |

</div>

이 중 아픈 동물은 Miller와 Cherokee입니다. 따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME     |
|-----------|----------|
| A367012   | Miller   |
| A381217   | Cherokee |

</div>

### 풀이

{% gist ry4nkim/0b5262f73a2fd773ab49b519e8171d6b solution_2_1.sql %}

---
## 어린 동물 찾기

출처 : [프로그래머스 # 코딩테스트 연습 - 어린 동물 찾기](https://programmers.co.kr/learn/courses/30/lessons/59037){:target="_blank"}

### 문제

`ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. `ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

<div class="table-wrapper" markdown="block">

| NAME             | TYPE       | NULLABLE |
|------------------|------------|----------|
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| INTAKE_CONDITION | VARCHAR(N) | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_INTAKE  | VARCHAR(N) | FALSE    |

</div>

동물 보호소에 들어온 동물 중 젊은 동물[^2]의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.

[^2]: INTAKE_CONDITION이 Aged가 아닌 경우를 뜻함

### 예시

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|----------|-----------------|
| A365172   | Dog         | 2014-08-26 12:53:00 | Normal           | Diablo   | Neutered Male   |
| A367012   | Dog         | 2015-09-16 09:06:00 | Sick             | Miller   | Neutered Male   |
| A365302   | Dog         | 2017-01-08 16:34:00 | Aged             | Minnie   | Spayed Female   |
| A381217   | Dog         | 2017-07-08 09:41:00 | Sick             | Cherokee | Neutered Male   |

</div>

이 중 젊은 동물은 Diablo, Miller, Cherokee입니다. 따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME     |
|-----------|----------|
| A365172   | Diablo   |
| A367012   | Miller   |
| A381217   | Cherokee |

</div>

### 풀이

{% gist ry4nkim/0b5262f73a2fd773ab49b519e8171d6b solution_2_2.sql %}

---