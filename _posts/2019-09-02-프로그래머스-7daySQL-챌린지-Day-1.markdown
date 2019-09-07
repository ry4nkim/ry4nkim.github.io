---
title: "[프로그래머스] 7daySQL 챌린지 Day 1"
layout: post
date: '2019-09-02 00:00:00'
image: "/assets/images/profile-round.png"
headerImage: true
tag:
- MySQL
- Programmers.kr
- 7daySQL
category: blog
author: ry4nkim
description: 7daySQL 챌린지 Day 1 - 모든 레코드 조회하기, 역순 정렬하기
---

## Summary:

[프로그래머스] 7daySQL 챌린지 Day 1

### Index
- [모든 레코드 조회하기](#모든-레코드-조회하기)
- [역순 정렬하기](#역순-정렬하기)

---
## 모든 레코드 조회하기

출처 : [프로그래머스 # 코딩테스트 연습 - 모든 레코드 조회하기](https://programmers.co.kr/learn/courses/30/lessons/59034){:target="_blank"}

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

동물 보호소에 들어온 모든 동물의 정보를 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요. SQL을 실행하면 다음과 같이 출력되어야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME   | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|--------|-----------------|
| A349996   | Cat         | 2018-01-22 14:32:00 | Normal           | Sugar  | Neutered Male   |
| A350276   | Cat         | 2017-08-13 13:50:00 | Normal           | Jewel  | Spayed Female   |
| A350375   | Cat         | 2017-03-06 15:01:00 | Normal           | Meo    | Neutered Male   |
| A352555   | Dog         | 2014-08-08 04:20:00 | Normal           | Harley | Spayed Female   |

</div>

..이하 생략

### 풀이

{% gist ry4nkim/80ea2e1a175b375f6e4b3a9085385592 solution_1_1.sql %}

---
## 역순 정렬하기

출처 : [프로그래머스 # 코딩테스트 연습 - 역순 정렬하기](https://programmers.co.kr/learn/courses/30/lessons/59035){:target="_blank"}

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

동물 보호소에 들어온 모든 동물의 이름과 보호 시작일을 조회하는 SQL문을 작성해주세요. 이때 결과는 ANIMAL_ID 역순으로 보여주세요. SQL을 실행하면 다음과 같이 출력되어야 합니다.

<div class="table-wrapper" markdown="block">

| NAME   | DATETIME            |
|--------|---------------------|
| Rocky  | 2016-06-07 09:17:00 |
| Shelly | 2015-01-29 15:01:00 |
| Benji  | 2016-04-19 13:28:00 |
| Jackie | 2016-01-03 16:25:00 |
| *Sam   | 2016-03-13 11:17:00 |

</div>

..이하 생략

### 풀이

{% gist ry4nkim/80ea2e1a175b375f6e4b3a9085385592 solution_1_2.sql %}

---