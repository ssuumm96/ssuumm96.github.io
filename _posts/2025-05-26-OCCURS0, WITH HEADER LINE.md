---
title:  "[SAP-ABAP] OCCURS 0, WITH HEARDER LINE 정리"
excerpt: "OCCURS 0, WITH HEARDER LINE 정리"

categories:
  - SAP
tags:
  - [SAP ABAP]

toc: true
toc_sticky: true

date: 2025-05-26
last_modified_at: 2025-05-26
---

쓰다보면 헷갈리는 문법

## OCCURS 0

```
DATA : GT_DATA TYPE BKPF.
```
-> BKPF 타입의 Structure

```
DATA : GT_DATA TYPE BKPF OCCURS 0.
```
-> BOBY가 있지만, HEADER LINE은 없는 테이블


## WITH HEADER LINE

```
DATA : GT_DATA TYPE BKPF WITH HEADER LINE.
DATA : GT_DATA TYPE TABLE OF BKPF WITH HEADER LINE.
```
-> 첫번째 로직은 잘못된 로직
WITH HEADER LINE 구문은 TABLE TYPE일 때만 사용을 할 수 있음

OCCURS 0은 Structure 형태에서 BOBY를 만드는 것이고 
WITH HEADER LINE은 Table 형태에서 Header line(work area)을 만드는 로직이다.

SAP S/4 HANA 버전 부터는 HEADER LINE을 사용하는 것을 권장하지 않고
WORK AREA를 따로 선언.

```
DATA : BEGIN OF GS_TEST,
       NAME(10) TYPE C,
       PHONE(20) TYPE I,
       CITY(10)  TYPE C,
       END OF GS_TEST.

DATA : GT_TEST LIKE TABLE OF GS_TEST.
```


출처 : <https://velog.io/@ss0mzi/03.-OCCURS-0-WITH-HEADER-LINE>