---
title: "[프로그래머스] 7daySQL 챌린지 Day 3"
layout: post
date: '2019-09-04 00:00:00'
image: "/assets/images/profile-round.png"
headerImage: true
tag:
- MySQL
- Programmers.kr
- 7daySQL
category: blog
author: ry4nkim
description: 7daySQL 챌린지 Day 3 - 최솟값 구하기, 이름이 없는 동물의 아이디
---

## Summary:

[프로그래머스] 7daySQL 챌린지 Day 3

### Index
- [최솟값 구하기](#최솟값-구하기)
- [이름이 없는 동물의 아이디](#이름이-없는-동물의-아이디)

---
## 최솟값 구하기

출처 : [프로그래머스 # 코딩테스트 연습 - 최솟값 구하기](https://programmers.co.kr/learn/courses/30/lessons/59038){:target="_blank"}

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

동물 보호소에 가장 먼저 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.

### 예시

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|----------|-----------------|
| A399552   | Dog         | 2013-10-14 15:38:00 | Normal           | Jack     | Neutered Male   |
| A379998   | Dog         | 2013-10-23 11:42:00 | Normal           | Disciple | Intact Male     |
| A370852   | Dog         | 2013-11-03 15:04:00 | Normal           | Katie    | Spayed Female   |
| A403564   | Dog         | 2013-11-18 17:03:00 | Normal           | Anna     | Spayed Female   |

</div>

가장 먼저 들어온 동물은 Jack이고, Jack은 2013-10-14 15:38:00에 들어왔습니다. 따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| 시간          | 
|---------------|
| 2013-10-14 15:38:00 |

</div>

### 풀이

{% gist ry4nkim/21a6338aa6ebb538933bc57a02c705fb solution_3_1.sql %}

---
## 이름이 없는 동물의 아이디

출처 : [프로그래머스 # 코딩테스트 연습 - 이름이 없는 동물의 아이디](https://programmers.co.kr/learn/courses/30/lessons/59039){:target="_blank"}

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

동물 보호소에 들어온 동물 중, 이름이 없는 채로 들어온 동물의 ID를 조회하는 SQL 문을 작성해주세요. 단, ID는 오름차순 정렬되어야 합니다.

### 예시

예를 들어 `ANIMAL_INS` 테이블이 다음과 같다면

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME       | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|------------|-----------------|
| A368930   | Dog         | 2014-06-08 13:20:00 | Normal           | NULL       | Spayed Female   |
| A524634   | Dog         | 2015-01-02 18:54:00 | Normal           | *Belle     | Intact Female   |
| A465637   | Dog         | 2017-06-04 08:17:00 | Injured          | *Commander | Neutered Male   |

</div>

이름이 없는 채로 들어온 동물의 ID는 A368930입니다. 따라서 SQL을 실행하면 다음과 같이 출력되어야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID |
|-----------|
| A368930   |

</div>

### 풀이

{% gist ry4nkim/21a6338aa6ebb538933bc57a02c705fb solution_3_2.sql %}

---