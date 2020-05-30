# MySQL 기본 문법

> <a href="[https://www.inflearn.com/course/SQL-%EC%9D%B8%EC%A0%9D%EC%85%98-%EA%B3%B5%EA%B2%A9-%EA%B8%B0%EB%B3%B8-%EB%AC%B8%EB%B2%95](https://www.inflearn.com/course/SQL-인젝션-공격-기본-문법)">성공적인 SQL 인젝션 공격을 위한, SQL 기본 문법</a>



## SQL이란?

- Structured Query Language
- RDBMS의 데이터를 관리하기 위해 설계된 특수 목적의 프로그래밍 언어





## SQL 문법 종류

#### DDL

- 데이터 정의 언어
- CREATE, DROP, ALTER, ...



#### DML

- 데이터 조작 언어(CRUD)
- SELECT, INSERT, UPDATE, DELETE, ...



#### DCL

- 데이터 제어 언어
- GRANT, REVOKE





## 기본 문법

#### CREATE

```mysql
CREATE DATABASE [DB_NAME];
CREATE TABLE [NAME] ([COLUMN_NAME] [DATE_TYPE]);
```



#### DROP

```mysql
DROP DATABASE [NAME];
DROP TABLE [NAME];
```



#### INSERT

```mysql
INSERT INTO [TABLE_NAME] ([COLUMN1], ...) VALUES ([DATE1], ...);
```



#### SELECT

```mysql
SELECT [COLUMN1] FROM [TABLE_NAME] WHERE [CONDITION];
```



#### UPDATE

```mysql
UPDATE [TABLE_NAME] SET [COLUMN1] = [DATA1] WHERE [CONDITION];
```



#### DELETE

```mysql
DELETE FROM [TABLE_NAME] WHERE [CONDITION];
```





## 연산자

#### 논리 연산자

| 연산자 |  의미  | 우선 순위 |         표현식          |
| :----: | :----: | :-------: | :---------------------: |
|  NOT   |  부정  |     1     |      NOT 피연산자       |
|  AND   | 논리곱 |     2     | 피연산자1 AND 피연산자2 |
|   OR   | 논리합 |     3     | 피연산자1 OR 피연산자 2 |



#### IN 연산자

```mysql
### IN 연산자가 OR 연산자보다 속도나 가독성 측면에서 유리하다.

# IN 연산자 사용
SELECT * FROM member WHERE id IN('admin', 'guest');

# OR 연산자 사용
SELECT * FROM member WHERE id = 'admin' OR id = 'guest';

# NOT IN 연산자
SELECT * FROM member WHERE id NOT IN('admin', 'guest');

# 서브쿼리에도 사용 가능
SELECT * FROM member WHERE id IN ([SUBQUERY]);
```



#### LIKE 연산자

```mysql
# % : 모든 문자
SELECT * FROM member WHERE id LIKE 'ad%';

# _ : 하나의 문자
SELECT * FROM member WHERE id LIKE 'admi_';
```





## 함수

#### 문자열 함수

```mysql
# SUBSTRING([문자열], [시작위치], [길이]);
SELECT SUBSTRING('test', 2, 2); # es 출력

# CONCAT([문자열1], ...)
SELECT CONCAT('te', 'st'); # test 출력 

# LENGTH([문자열])
SELECT LENGTH('test'); # 4 출력
```



#### COUNT 함수

```mysql
# 레코드 수 조회
SELECT COUNT(*) FROM [TABLE_NAME];
```





## 조건문

#### CASE WHEN

```mysql
# 문법
CASE WHEN [CONDITION] 
    THEN [TRUE_CASE] 
    ELSE [FALSE_CASE] 
END

# SELECT example
SELECT CASE WHEN 1=1 THEN 1 ELSE 2 END; # 1 출력

# WHERE example
SELECT * FROM member
WHERE seq = (CASE WHEN 1=1 THEN 1 ELSE 2 END); # seq=1 레코드 출력
```





## 서브쿼리

#### 서브쿼리 명칭

```mysql
# SELECT : 스칼라 서브쿼리
# 하나의 레코드에 하나의 컬럼만 출력
SELECT (SubQuery) FROM [TABLE_NAME] WHERE [CONDITION];

# FROM : 인라인 뷰(가상의 테이블)
# 여러 레코드 출력 가능
SELECT * FROM (SubQuery) a WHERE[CONDITION];

# WHERE : 일반 서브쿼리
# 여러 레코드 출력 가능
SELECT * FROM [TABLE_NAME] WHERE [COLUMN] = (SubQuery);
```



#### 서브쿼리 종류

```mysql
# 단일 행 서브쿼리
SELECT * FROM member WHERE id = (SELECT id FROM bbs WHERE idx = 192);

# 다중 행 서브쿼리
SELECT * FROM member WHERE id IN(SELECT id FROM bbs);
```





## 레코드 정렬

#### ORDER BY

```mysql
# 오름차순 (default)
SELECT [COLUMN] FROM [TABLE_NAME] ORDER BY [COLUMN] ASC;

# 내림차순
SELECT [COLUMN] FROM [TABLE_NAME] ORDER BY [COLUMN] DESC;

# 다수의 조건 COLUMN 사용 가능
# COLUMN1으로 정렬 후 COLUMN2로 정렬 (오름차순)
SELECT [COLUMN] FROM [TABLE_NAME] ORDER BY [COLUMN1], [COLUMN2];
```





## 레코드 출력 개수 제한

#### LIMIT

```mysql
SELECT [COLUMN] FROM [TABLE_NAME] LIMIT [OFFSET], [ROW_COUNT];
SELECT [COLUMN] FROM [TABLE_NAME] LIMIT [ROW_COUNT];
```





## 기타

```mysql
# 작업중인 데이터베이스
SELECT DATABASE();

# 데이터베이스 변경
USE [DB_NAME];

# 테이블 목록 조회
SHOW TABLES;

# 테이블 구조 조회
DESC [TABLE_NAME];
```



