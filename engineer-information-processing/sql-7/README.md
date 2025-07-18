# SQL 응용 (7과목)

#### 트랜잭션

트랜잭션은 데이터베이스 시스템에서 하나의 논리적 기능을 정상적으로 수행하기 위한 작업의 기본 단위.

#### 트랜잭션의 특성

* 원자성 (Atomicity) : 트랜잭션의 연산 전체가 성공 또는 실패되어야 하는 성질 (Commit/Rollback)
* 일관성(Consistency) : 시스템이 가지고 있는 고정요소는 트랜잭션 수행 전과 트랜잭션 수행 완료 후의 상태가 같아야 하는성질(무결성 제약조건)
* 격리성(Isolation) : 동시에 실행되는 트랜잭션들이 서로 영향을 미치지 않아야 한다는 성질(고립화 수준)
* 영속성(Durability) : 성공이 완료된 트랜잭션의 결과는 영속적으로 데이터베에스에 저장되어야 하는 성질&#x20;

#### 트랜잭션 제어언어 : TCL

TCL 명령어&#x20;

* 커밋 (COMMIT) : 트랜잭션 확정, 트랜잭션을 메모리에 영구적으로 저장하는 명령어
* 롤백(ROLLBACK) : 트랜잭션 취소, 트랜잭션 내역을 저장 무효화시키는 명령어
* 체크포인트(CHECKPOINT) : 저장 시기 설정, ROLLBACK을 위한 시점을 지정하는 명령어

#### 회복기법 (영속성 주요 기법)

* REDO : 시작과 완료에 대한 기록이 있는 트랜잭션들의 작업을 재작업
* UNDO : 작업한 변경 내용들을 취소하는 기법



데이터 정의어(DDL; Data Definition Language)

데이터 정의어는 '데이터를 담는 그릇을 정의하는 언어'

#### DDL의 대상

* 스키마(Schema) : 데이터베이스의 구조, 제약조건 등의 정보를 담고 있는 기본적인 구조, 외부/개념/내부 3계층으로 구성
* 테이블(Table) : 데이터를 저장하는 항목인 필드(컬럼)들로 구성된 데이터의 집합체, 릴레이션(Relation) 혹은 엔터티(Entity)라고도 불림
  * 튜플, 행, 레코드
  * 속성, 열(컬럼), 필드
  * 카디널리티 : 튜플의 개수
  * 차수 : 속성의 개수
  * 도메인 : 필드가 가질 수 있는 값의 타입과 범위&#x20;
* 뷰(View) : 논리 테이블&#x20;
* 인덱스(Index) : 검색 연산의 최적화를 위해 데이터베이스 내 값에 대한 주소정보로 구성된 데이터 구조, 테이블에 대한 조회 속도를 높여 줌

#### DDL 명령어

* CREATE, ALTER, DROP, TRUNCATE
* CREATE, ALTER TABLE 제약조건
  * PRIMARY KEY : 테이블마다 1개만, NULL 안됨
  * FOREIGN KEY : 다른 테이블의 PK 참조, 부모가 없으면 자식도 못 넣음, CASCADE 옵션으로 부모 삭제 시 자식 삭제 가능
  * UNIQUE : 테이블마다 1개만, NULL 가능
  * NOT NULL
  * CHECK : 특정 조건을 만족해야함
  * DEFAULT : 컬럼의 기본값 설정



