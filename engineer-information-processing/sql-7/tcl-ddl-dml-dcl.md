# TCL, DDL, DML, DCL

### TCL

* COMMIT
* ROLLBACK
* CHECKPOINT

### DDL

* CREATE
  * **CREATE TABLE** 테이블명(사번 VARCHAR(10) NOT NULL, ... );
  * **CREATE VIEW** 뷰이름 **AS** 조회쿼리;
  * **CREATE OR REPLACE VIEW** 뷰이름 **AS** 조회쿼리;    ->  뷰를 교체하는 명령
  * **CREATE \[UNIQUE] INDEX** 인덱스명 **ON** 테이블명(컬럼명1, 컬럼명2,...);&#x20;
* ALTER
  * **ALTER TABLE** 테이블명 **ADD** 컬럼명 데이터타입 \[제약조건];
  * **ALTER \[UNIQUE] INDEX** 인덱스명 **ON** 테이블명(컬럼명1, 컬럼명2, ...);
* DROP
  * **DROP TABLE** 테이블명 \[**CASCADE | RESTRICT**];
  * **DROP VIEW** 뷰이름;
  * **DROP INDEX** 인덱스명;
* TRUNCATE
  * **TRUNCATE TABLE** 테이블명;

### DML

* SELETE
* INSERT
  * **INSERT** **INTO** 테이블명(속성명1, ...) **VALUES** (데이터1, ...);
  * **INSERT** **INTO** 테이블1(속성명1, ...) **SELETE** 컬럼명1; FROM 테이블2;
* UPDATE
  * **UPDATE** 테이블명 **SET** 속성명=데이터, ... **WHERE** 조건;   -> 조건 만족하는애 set에 속성에 새로운 데이터로 수정
* DELETE
  * **DELETE** **FROM** 테이블명 **WHERE** 조건;
* 조인&#x20;
  * **SELECT** 테이블1.컬럼1, 테이블1.컬럼2, ..., 테이블2.컬럼1, 테이블2.컬럼2, ... **FROM** 테이블 1 **JOIN** 테이블2 **ON** 조인조건 \[**WHERE** 검색조건];

### DCL

* GRANT
  * **GRANT** 권한 **ON** 테이블 **TO** 사용자;
* REVOKE
  * **REVOKE** 권한 **ON** 테이블 **FROM** 사용자;
