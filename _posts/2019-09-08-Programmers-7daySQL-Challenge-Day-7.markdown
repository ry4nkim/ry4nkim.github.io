---
title: "[프로그래머스] 7daySQL 챌린지 Day 7"
layout: post
date: '2019-09-08 00:00:00'
image: "/assets/images/profile-round.png"
headerImage: true
tag:
- MySQL
- Programmers.kr
- 7daySQL
category: blog
author: ry4nkim
description: 7daySQL 챌린지 Day 7 - 루시와 엘라 찾기, 이름이 el로 끝나는 동물 찾기
---

## Summary:

[프로그래머스] 7daySQL 챌린지 Day 7

### Index
- [루시와 엘라 찾기](#루시와-엘라-찾기)
- [이름이 el로 끝나는 동물 찾기](#이름이-el로-끝나는-동물-찾기)

---
## 루시와 엘라 찾기

출처 : [프로그래머스 # 코딩테스트 연습 - 루시와 엘라 찾기](https://programmers.co.kr/learn/courses/30/lessons/59046){:target="_blank"}

### 문제

`ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. 
`ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

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

동물 보호소에 들어온 동물 중 이름이 Lucy, Ella, Pickle, Rogan, Sabrina, Mitty인 동물의 아이디와 이름, 성별을 조회하는 SQL 문을 작성해주세요.

### 예시

이때 결과는 아이디 순으로 조회해주세요. 예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME  | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|-------|-----------------|
| A373219   | Cat         | 2014-07-29 11:43:00 | Normal           | Ella  | Spayed Female   |
| A377750   | Dog         | 2017-10-25 17:17:00 | Normal           | Lucy  | Spayed Female   |
| A353259   | Dog         | 2016-05-08 12:57:00 | Injured          | Bj    | Neutered Male   |
| A354540   | Cat         | 2014-12-11 11:48:00 | Normal           | Tux   | Neutered Male   |
| A354597   | Cat         | 2014-05-02 12:16:00 | Normal           | Ariel | Spayed Female   |

</div>

SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME | SEX_UPON_INTAKE |
|-----------|------|-----------------|
| A373219   | Ella | Spayed Female   |
| A377750   | Lucy | Spayed Female   |

</div>

### 풀이

{% gist ry4nkim/a3478c04e30a7d5f95f5c88bfa4dd18e solution_7_1.sql %}

---
## 이름이 el로 끝나는 동물 찾기

출처 : [프로그래머스 # 코딩테스트 연습 - 이름이 el로 끝나는 동물 찾기](https://programmers.co.kr/learn/courses/30/lessons/59047){:target="_blank"}

### 문제

`ANIMAL_INS` 테이블은 동물 보호소에 들어온 동물의 정보를 담은 테이블입니다. 
`ANIMAL_INS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`는 각각 동물의 아이디, 생물 종, 보호 시작일, 보호 시작 시 상태, 이름, 성별 및 중성화 여부를 나타냅니다.

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

보호소에 돌아가신 할머니가 기르던 개를 찾는 사람이 찾아왔습니다. 이 사람이 말하길 할머니가 기르던 개는 이름에 'el'이 들어간다고 합니다. 동물 보호소에 들어온 동물 이름 중, 이름에 EL이 들어가는 개의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 이름 순으로 조회해주세요.

### 예시

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME         | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|--------------|-----------------|
| A355753   | Dog         | 2015-09-10 13:14:00 | Normal           | Elijah       | Neutered Male   |
| A352872   | Dog         | 2015-07-09 17:51:00 | Aged             | Peanutbutter | Neutered Male   |
| A353259   | Dog         | 2016-05-08 12:57:00 | Injured          | Bj           | Neutered Male   |
| A373219   | Cat         | 2014-07-29 11:43:00 | Normal           | Ella         | Spayed Female   |
| A382192   | Dog         | 2015-03-13 13:14:00 | Normal           | Maxwell 2    | Intact Male     |

</div>

- 이름에 'el'이 들어가는 동물은 Elijah, Ella, Maxwell 2입니다.
- 이 중, 개는 Elijah, Maxwell 2입니다.

따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME      |
|-----------|-----------|
| A355753   | Elijah    |
| A382192   | Maxwell 2 |

</div>

### 풀이

{% gist ry4nkim/a3478c04e30a7d5f95f5c88bfa4dd18e solution_7_2.sql %}

---