# SQL
Description and Summary of the use of the SQL

## 1. What is SQL
- `SQL Structured Query Language` : 구조적 퀴리 언어의 약자
- sql을 사용하여 데이터 베이스에 접근하고 조작할 수 있다.
- sql은 1986년 ANSI(American National Standards Institute)의 표준이 되었고, 1987년 ISO(International Organization for Standardization)의 표준이 되었다.

## 2. Waht cat SQL do?
- 데이터베이스에 대해 쿼리를 실행할 수 있다.
- 데이터베이스에서 데이터를 검색, 삽입, 업데이트, 삭제할 수 있다.
- 새로운 데이터 베이스와 새 테이블을 생성할 수 있다.
- 데이터베이스에 저장 프로시저(procedures, 절차)를 생성할 수 있다.
- 데이터베이스에서 뷰(view)를 생성하여 효율적인 데이터 조작을 할 수 있다.
- 테이블과 프로시저 뷰에 대한 권한 등을 설정 할 수 있다.

## 3. SQL is a Standard, But..
- sql 언어는 ANSI/ISO의 표준 언어이지만 여러가지 버전이 존재한다.
    - ANSI 표준을 따르는 주요 명령어는 공통으로 사용가능 하다.
    - SELECT, UPDATE, DELETE, INSERT, WHERE 등
- 대부분의 sql 프로그램에는 sql 표준 명령어 외에도 고유한 확장기능들이 있다.

## 4. Using SQL in your web site
- 데이터베이스의 데이터를 표시하는 웹사이트 구축하기 위한 방법 : 
    - PHP 또는 ASP와 같은 서버의 스크립팅 언어 사용하기위해
    - sql을 사용하여 원하는 데이터를 얻기위해
    - HTML/CSS를 사용하여 페이지의 스타일을 지정하기 위해서
- RDBMS 데이터베이스 프로그램 (MS Access, SQL Server, MySQL)이 필요하다.    

## 5. RDBMS
- `RDBMS Relational Database Management System` : 관계형 데이터베이스 관리 시스템
- RDMBS sql과 ms sql server, ibm db2, oracle, mysql 및 microsoft access와 같은 모든 최신 데이터베이스 시스템의 기반이다.
- RDBMS의 데이터는 데이터베이스의 개체인 테이블에 저장된다.
    - 테이블은 데이터 항목의 모음과 같다.
    - 열(column)과 행(row)으로 구성되어 있다.
- 모든 테이블은 필드(fields)라고 하는 작은 엔터티(entities)로 구성된다.
- 필드(fields)는 테이블의 모든 레코드에 대한 특정 정보를 유지하도록 설계된 테이블의 열(column)과 같다.
    - 필드=열
- 행(row)이라고 하는 레코드는 테이블에 있는 각각의 개별 항목과 같다.
    - 레코드는 테이블의 수평 엔터티이다.
    - **행=레코드=수평 엔터티**
- 열(column)은 테이블의 특정 필드와 관련된 모든 정보를 포함하는 테이블의 수직 엔터티이다.   
    - **열=필드=수직 엔터티**

## 6. Some of the most important SQL commands
- `SELECT` : 데이터베이스에서 데이터 추출
- `UPDATE` : 데이터베이스에 데이터 업데이트
- `DELETE` : 데이터베이스에 데이터 삭제
- `INSERT INTO` : 새로운 데이터를 데이터베이스에 삽입
- `CREATE DATABASE` : 새로운 데이터 베이스 만들기
- `ALTER DATABASE` : 데이터 베이스 수정하기
- `CREATE TABLE` : 새로운 테이블 만들기
- `ALTER TABLE` : 테이블 수정하기
- `DROP TABLE` : 테이블 삭제
- `CREATE INDEX` : 인덱스 생성하기(검색 키)
- `DROP INDEX` : 인덱스 삭제

## 7. SQL commands
- statements : 문
- clause : 절
- `SELECT DISTINCT` : 고유한 값만 반환, 중복을 제거한 데이터만 반환
- `SELECT COUNT(DISTINCT)` : 데이터의 갯수 계산, MS Access에서는 사용 불가
- `WHERE` : 레코드 필터링 명령어, 조건을 충족하는 레코드만 추출하는데 사용
    - **WHERE절은 SELECT문이나 UPDATE, DELETE문에서도 사용할 수 있다.**
- `WHERE절 Operators`
    - =, >, <, <=, >=
    - **<> 은 != 과 같다. 일부 SQL 버전마다 다름**
    - BETWEEN : 일정 범위 사이의 조건
    - LIKE : 패턴 검색, WHERE col1 LIKE "%A" (%의 위치에 따라 조건 바뀜)
    - IN : 열에서 여러가지 값을 지정, WHERE col1 IN (val1, val2, ...)
    - AND : 조건 모두 True이면 결과 반환
    - OR : 조건 하나라도 True이면 결과 반환
    - NOT : Not True 인 조건에서 결과 반환
    - **AND, OR, NOT을 조합하여 사용가능** 
        - WHERE 조건 AND (조건 OR 조건) 
        - WHERE NOT 조건 AND NOT 조건
- `ORDER BY` : 결과를 정렬한다.
    - ASCENDING, ASC : 오름차순, 디폴트값
    - DECENDING, DESC : 내림차순
    - 여러 컬럼에 적용 가능
- `INSERT INTO` : 테이블에 새로운 레코드 삽입
    - INSERT INTO table_name (col1, col2, ...) VALUES (val1, val2, ...) : 일부 컬럼
    - INSERT INTO table_name VALUES (val1, val2, ...) : 모든 컬럼
- `NULL` : 값이 없는 필드, 0이나 공백과 다름
    - IS NULL : NULL 값을 찾아준다.
    - IS NOT NULL : 비어 있지 않은 값을 찾아준다.
- `UPDATE` : 테이블의 기존 레코드를 수정
    - UPDATE table_name SET col1=val1, col2=val2, ... WHERE 조건 ; 
    - **WHERE 절로 조건을 설정하지 않으면 모든 테이블의 값이 업데이트 된다.**
    - WHERE 절에서 업데이트할 레코드의 수를 결정한다.
    - 조건에서 선택되는 레코드의 갯수과 업데이트할 값의 갯수가 같아야 한다.
- `DELETE` : 테이블의 기존 레코드를 삭제
    - DELETE FROM table_name WHERE 조건
    - **WHERE 절로 조건을 설정하지 않으면 모든 열(레코드)가 삭제된다. 테이블의 구조, 속성, 인덱스는 유지된다.**
- `SELECT TOP or LIMIT` : 반환할 레코드의 수 지정, 수천개의 레코드가 있는 큰 테이블에서 유용
    - 데이터 베이스 시스템에 따라서 레코드 수 지정하는 명령어가 다를 수 있다.
    - SQL Server / MS Access : 
        - SELECT TOP num col1 FROM table_name WHERE 조건, WHERE 절이 뒤에 옴
        - SELECT TOP num PERCENT col1 FROM table_name WHERE 조건
    - MySQL : 
        - WHERE 조건 1 LIMIT num1, num2 : num1 ~ num1+num2-1
        - WHERE 절이 앞에 옴
    - Oracle : FETCH FIRST, ROWS ONLY, WHERE ROWNUM <= num 등
- `MIN(col1)` : 선택한 열의 가장 작은 값 반환, SELECT 문에서 사용, function
- `MAX(col1)` : 선택한 열의 가장 큰 값 반환, SELECT 문에서 사용, function
- `COUNT(col1)` : 조건의 결과의 행의 수를 반환, NULL 제외
- `AVG(col1)` : 숫자형 열의 데이터의 평균을 반환, NULL 제외
- `SUM(col1)` : 숫자형 열의 데이터의 합을 반환, NULL 제외
- `LIKE` : 열에서 특정한 패턴을 검색, WHERE 절에 사용
    - WHERE col1 LIKE %+패턴1 : %는 0, 1, 문자와 함께 사용
    - WHERE col1 LIKE \_+패턴1 : \_는 단일 문자를 한개를 의미한다.
    - %, \_, AND, OR 를 조합해서 사용 가능
    - MS Access : % 대신 * 사용, \_ 대신 ? 사용
    - WHERE col1 NOT LIKE 패턴1 : 패턴1이 아닌 모든 것
- `LIKE % pattern`
    - `a%` : a로 시작하는 데이터
    - `%a` : a로 끝나는 데이터
    - `%a%` : 어떤 위치는 a가 있는 데이터
    - `_r%` : 두번쨰 자리에 r이 있는 데이터
    - `a_%` : a로 시작하고 길이가 2자 이상인 데이터
    - `a__%` : a로 시작하고 길이가 3자 이상인 데이터
    - `a%o` : a로 시작하고 o로 끝나는 데이터

#### SQL Wildcard Character
- `wildcard character` : 문자열에서 하나 이상의 문자를 대체하는 문자
- LIKE operator와 같이 사용한다.
- **MS Access** :
    - `*` : 0개 이상의 문자
        - bl* -> bl, black, blue 등
    - `?` : 단일 문자
        - h?t -> hot, hat, hit 등
    - `[]` : 대괄호안의 단일문자
        - h[oa]t -> hot, hat을 찾고, hit 제외, o or a
    - `!` : 대괄호가 아닌 모든 문자
        - h[!oa]t -> hit을 찾고, hot, hat 제외
    - `-` : 지정된 범위내의 모든 단일문자
        - c[a-b]t -> cat, cbt 찾고 cut 제외
    - `#` : 단일 숫자문자
        - 2#5 -> 205, 215, 225, 235, 245, 265, 275, 285, 295
    - `[!a-f]%` : 첫글자가 a-f 사이의 문자가 아닌 데이터
    - `_[a-c]%` : 두번쨰 글자가 a-c 사이의 문자인 데이터
- **SQL server** : 
    - `%` : 0개 이상의 문자 
    - `_` : 단일 문자
        - h_t : hot, hat, hit
    - `[]` : 대괄호안의 단일문자
    - `^` : 대괄호가 아닌 모든 문자
        - h[^oa]t -> hit 찾고, hot, hat 제외
    - `-` : 지정된 범위내의 모든 단일문자
    
- `IN` : WHERE 절에 여러개의 조건을 지정
    - WHERE col1 IN (val1, val2, ...) : val1 or val2 or ...
    - WHERE col1 NOT IN (val1, val2, ...) : 조건이 아닌 것 반환
    - WHERE col1 IN (SELECT col2 FROM table_name) : 조건으로 SELECT 문을 쓸 수 있다.
        - **col1 과 col2 의 데이터 종류가 같아야 한다.**
        - WHERE 절에 subquery를 사용한 것
- `BETWEEN` : 주어진 범위 이내의 데이터를 찾는다. 숫자, 텍스트, 날짜 데이터 사용
    - WHERE 절에 조건의 범위로 사용
    - WHERE col1 BETWEEN val1 AND val2 
        - OR는 사용이 안된다. OR는 IN ()의 기능
    - WHERE col1 NOT BETWEEN val1 AND val2 : 범위 밖의 데이터선택
    - **WHERE col1 BETWEEN val1 AND val2 AND col2 IN (val3, val4, va5)**
        - AND 로 IN()이나 다른 연산자를 계속 연결하여 필터링 조건을 늘릴 수 있다.
- `Aliases, AS` : 테이블이나 열에 임시이름 설정
    - 열 이름을 읽기 쉽게 만들때 사용
    - 이 이름은 해당 쿼리 안에서만 설정된다.
    - SELECT col1 AS alias_name FROM table_name
    - SELECT col1 FROM table_name AS alias_name : FROM 절에서 테이블에도 사용 가능
    - **[alias name]** : 띄어쓰기나 기호를 사용한 이름을 붙일때는 대괄호 사용
    - **FROM 절에서 서로 다른 table의 이름을 단축하여 쓰고 SELECT에서 적용가능**
        - SELECT c.OrderID, a.OrderID FROM Customer AS c, Address AS a WHERE c.ID=o.ID : WHERE 절에서 같은 열을 표시해주어야 한다. 
- 컬럼끼리 데이터 합할때
    - SQL : col1 + ',' + col2
    - MySQL : CONCAT(col1, ',' ,col2, ',', col3)
    - ORACLE : (col1 || ',' || col2)
- Aliases 장점 
    - 쿼리에 사용되는 함수
    - 쿼리에 테이블이 두개 이상 사용 될 때
    - 열이름이 길거나 보기 어려울 때
    - 두 개 이상의 열을 결합 할 때




