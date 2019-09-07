---
title: "[프로그래머스] 7daySQL 챌린지 Day 5"
layout: post
date: '2019-09-06 00:00:00'
image: "/assets/images/profile-round.png"
headerImage: true
tag:
- MySQL
- Programmers.kr
- 7daySQL
category: blog
author: ry4nkim
description: 7daySQL 챌린지 Day 5 - 없어진 기록 찾기, 있었는데요 없었습니다
---

## Summary:

[프로그래머스] 7daySQL 챌린지 Day 5

### Index
- [없어진 기록 찾기](#없어진-기록-찾기)
- [있었는데요 없었습니다](#있었는데요-없었습니다)

---
## 없어진 기록 찾기

출처 : [프로그래머스 # 코딩테스트 연습 - 없어진 기록 찾기](https://programmers.co.kr/learn/courses/30/lessons/59042){:target="_blank"}

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

`ANIMAL_OUTS` 테이블은 동물 보호소에서 입양 보낸 동물의 정보를 담은 테이블입니다. 
`ANIMAL_OUTS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `NAME`, `SEX_UPON_OUTCOME`는 각각 동물의 아이디, 생물 종, 입양일, 이름, 성별 및 중성화 여부를 나타냅니다. 
`ANIMAL_OUTS` 테이블의 `ANIMAL_ID`는 `ANIMAL_INS`의 `ANIMAL_ID`의 외래 키입니다.

<div class="table-wrapper" markdown="block">

| NAME             | TYPE       | NULLABLE |
|------------------|------------|----------|
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_OUTCOME | VARCHAR(N) | FALSE    |

</div>

천재지변으로 인해 일부 데이터가 유실되었습니다. 입양을 간 기록은 있는데, 보호소에 들어온 기록이 없는 동물의 ID와 이름을 ID 순으로 조회하는 SQL문을 작성해주세요.

### 예시

예를 들어, `ANIMAL_INS` 테이블과 `ANIMAL_OUTS` 테이블이 다음과 같다면

`ANIMAL_INS`

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|------|-----------------|
| A352713   | Cat         | 2017-04-13 16:29:00 | Normal           | Gia  | Spayed Female   |
| A350375   | Cat         | 2017-03-06 15:01:00 | Normal           | Meo  | Neutered Male   |

</div>

`ANIMAL_OUTS`

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | NAME  | SEX_UPON_OUTCOME |
|-----------|-------------|---------------------|-------|------------------|
| A349733   | Dog         | 2017-09-27 19:09:00 | Allie | Spayed Female    |
| A352713   | Cat         | 2017-04-25 12:25:00 | Gia   | Spayed Female    |
| A349990   | Cat         | 2018-02-02 14:18:00 | Spice | Spayed Female    |

</div>

`ANIMAL_OUTS` 테이블에서
- Allie의 ID는 `ANIMAL_INS`에 없으므로, Allie의 데이터는 유실되었습니다.
- Gia의 ID는 `ANIMAL_INS`에 있으므로, Gia의 데이터는 유실되지 않았습니다.
- Spice의 ID는 `ANIMAL_INS`에 없으므로, Spice의 데이터는 유실되었습니다.

따라서 SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME  |
|-----------|-------|
| A349733   | Allie |
| A349990   | Spice |

</div>

### 풀이

{% gist ry4nkim/e1c4fc9e67e6fe1f46f223366c010fe1 solution_5_1.sql %}

---
## 있었는데요 없었습니다

출처 : [프로그래머스 # 코딩테스트 연습 - 있었는데요 없었습니다](https://programmers.co.kr/learn/courses/30/lessons/59043){:target="_blank"}

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

`ANIMAL_OUTS` 테이블은 동물 보호소에서 입양 보낸 동물의 정보를 담은 테이블입니다. 
`ANIMAL_OUTS` 테이블 구조는 다음과 같으며, `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `NAME`, `SEX_UPON_OUTCOME`는 각각 동물의 아이디, 생물 종, 입양일, 이름, 성별 및 중성화 여부를 나타냅니다. 
`ANIMAL_OUTS` 테이블의 `ANIMAL_ID`는 `ANIMAL_INS`의 `ANIMAL_ID`의 외래 키입니다.

<div class="table-wrapper" markdown="block">

| NAME             | TYPE       | NULLABLE |
|------------------|------------|----------|
| ANIMAL_ID        | VARCHAR(N) | FALSE    |
| ANIMAL_TYPE      | VARCHAR(N) | FALSE    |
| DATETIME         | DATETIME   | FALSE    |
| NAME             | VARCHAR(N) | TRUE     |
| SEX_UPON_OUTCOME | VARCHAR(N) | FALSE    |

</div>

관리자의 실수로 일부 동물의 입양일이 잘못 입력되었습니다. 보호 시작일보다 입양일이 더 빠른 동물의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 시작일이 빠른 순으로 조회해야합니다.

### 예시

예를 들어, `ANIMAL_INS` 테이블과 `ANIMAL_OUTS` 테이블이 다음과 같다면

`ANIMAL_INS`

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | INTAKE_CONDITION | NAME     | SEX_UPON_INTAKE |
|-----------|-------------|---------------------|------------------|----------|-----------------|
| A350276   | Cat         | 2017-08-13 13:50:00 | Normal           | Jewel    | Spayed Female   |
| A381217   | Dog         | 2017-07-08 09:41:00 | Sick             | Cherokee | Neutered Male   |

</div>

`ANIMAL_OUTS`

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | ANIMAL_TYPE | DATETIME            | NAME     | SEX_UPON_OUTCOME |
|-----------|-------------|---------------------|----------|------------------|
| A350276   | Cat         | 2018-01-28 17:51:00 | Jewel    | Spayed Female    |
| A381217   | Dog         | 2017-06-09 18:51:00 | Cherokee | Neutered Male    |

</div>

SQL문을 실행하면 다음과 같이 나와야 합니다.

<div class="table-wrapper" markdown="block">

| ANIMAL_ID | NAME     |
|-----------|----------|
| A381217   | Cherokee |

</div>

### 풀이

{% gist ry4nkim/e1c4fc9e67e6fe1f46f223366c010fe1 solution_5_2.sql %}

---