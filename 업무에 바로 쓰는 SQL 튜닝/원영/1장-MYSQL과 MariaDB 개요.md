# 1장 MYSQL과 MariaDB 개요

### MySQL

- 1995년 배포된 무료 DBMS
- 대용량 데이터와 가용성, 안정성이라는 장점

### MariaDB

- 2010년 MySQL이 오라클에 인수됨
- 개발 지침과 라이선스 정책 변화에 따라 MySQL 핵심 개발자 주도로 오픈소스 정책을 지향하는 MariaDB가 탄생
- MySQL의 소스 코드에 기반을 둔 개발인 만큼, 개발자 입장에서 현재까지 별다른 차이가 없음
- 일부 기능과 수행 매커니즘, 시스템 변수나 시스템 상태 등에서 점점 차이가 나는 중

오라클 DB는 `통합된 스토리지 하나를 공유`하여 사용하는 방식

- 사용자가 어느 DB서버(Master 노드)에 접속하여 SQL문을 수행하더라도 같은 스토리지를 사용하여 같은 결과를 출력함

MySQL은 물리적인 DB 서버마다 `독립적으로 스토리지를 할당`하는 방식

- 마스터-슬레이브 구조(주-종 구조)
  - 마스터 노드 : 쓰기, 읽기 처리를 모두 수행 가능
  - 슬레이브 노드 : 읽기 처리만 수행
- DB서버마다 각자의 역할이 부여될 수 있음

### 쿼리 오프로딩

- DB 서버의 트랜잭션에서 쓰기 트렌잭션과 읽기 트랜잭션을 분리하여 DB 처리량을 증가시키는 성능 향상 기법
  - 쓰기 트랜잭션 : UPDATE, INSERT, DELETE
  - 읽기 트랜잭션 : SELECT

### 기능 차이

- MySQL
  - 중첩 루프 조인 방식(nested loop join)으로만 풀림
    - 수행 가능한 알고리즘이 적어서 성능적으로 분리함
  - 스토리지 엔진이라는 개념을 포함하므로 오픈소스 DBMS를 바로 꽂아서 사용할 수 있는 `확장성`이 특징
    - 무료
    - 경량화
  - 메모리 사용률이 상대적으로 낮음(오라클과 100배 이상 차이)
- 오라클 DB
  - 중첩 루프 조인, 정렬 병합 조인, 해시 조인

## MySQL, Oracle 문법 차이

### Null 값을 대체하는 문법

- MySQL / MariaDB

```sql
-- IFNULL(컬럼명, '대쳇값')
SELECT IFNULL(col1, 'N/A') col1
FROM tab;
```

- Oracle

```sql
-- NVL(컬럼명, '대쳇값')
SELECT NVL(col1, 'N/A') col1
FROM tab;
```

### 페이징 처리

- MySQL / MariaDB

```sql
SELECT col1
FROM tab
LIMIT 5;
```

- Oracle :

```sql
SELECT col1
FROM tab
LIMIT ROWNUM <= 5;
```

### 현재 날짜

- MySQL / MariaDB

```sql
NOW()
```

- Oracle

```sql
SYSDATE()
```

### 조건문

- MySQL / MariaDB

```sql
-- IF(조건식, '참값', '거짓값')
SELECT IF(col1='A', 'apple', '-') As col1
From tab;
```

- Oracle

```sql
-- IF(컬럼명, '값', '참값', '거짓값')
SELECT DECODE(col1, 'A', 'apple', '-') As col1
From tab;
```

### 날짜 형식

- MySQL / MariaDB

```sql
-- DATE_FORMAT(날짜열, '형식')
SELECT DATE_FORMAT(NOW(), '%Y%m%d %H%i%s') AS date;
```

- Oracle

```sql
-- TO_CHAR(날짜열, '형식')
SELECT TO_CHAR(SYSDATE, 'YYYYMMDD HH24MISS') AS date
FROM DUAL;
```

### 자동 증갓값

- MySQL

```sql
-- AUTO_INCREMET
CREATE TABLE tab
(
	seq INT NOT NULL AUTO_INCREMENT PRIMARY KEY
);
```

- MariaDB 10.3 이상, Oracle

```sql
-- 시퀀스 오브젝트 생성
CREATE SEQUENCE SEA_SAMPLE
INCREAMENT BY 1
START WITH 1
MINVALUE 1
MAXVALUE 99999999999
CYCLE
CACHE;

-- 다음 값 채번 문법 (MariaDB)
SELECT NEXTVAL(SEQ_SAMPLE);

-- 다음 값 채번 문법 (MariaDB)
SELECT SEQ_SAMPLE.NEXTVAL
FROM DUAL;
```

### 문자 결합

- MySQL / MariaDB

```sql
-- CONCAT(컬럼값 또는 문자열, 컬럼값 또는 문자열)
SELECT CONCAT('A', 'B') TEXT;
```

- Oracle

```sql
-- 컬럼값 또는 문자열 || 컬럼값 또는 문자열
SELECT 'A' || 'B' TEXT
FROM DUAL;

-- CONCAT(컬럼값 또는 문자열, 컬럼값 또는 문자열)
SELECT CONCAT('A','B') TEXT
```

### 문자 추출

- MySQL / MariaDB

```sql
-- SUBSTRING(열값 또는 문자열, 시작 위치, 추출하려는 문자 개수)
SELECT SUBSTRING('ABCDE',2,3) AS sub_string;
```

- Oracle

```sql
-- SUBSTR(열값 또는 문자열, 시작 위치, 추출하려는 문자 개수)
SELECT SUBSTR('ABCDE',2,3) AS sub_string
FROM DUAL;
```
