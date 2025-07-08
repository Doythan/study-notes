# HashSet

#### HashSet

**Set** 개념을 구현한 자료구조

내부적으로 **Hash Table**을 사용해서

* 값을 해시값으로 변환 (hashCode())
* 같은 해시값이면 equals()로 추가 여부 판단

HashSet은 Set(집합)을 해시 테이블(Hash Table)로 구현한 것

***

#### 특징

* 중복 허용 X
* 순서 없음
* null 허용
* 빠른 속도
* 동일성 판단 (hashCode()와 equals()를 기준으로 중복 여부 판단)

***

#### 주요 매서드

* add(E e)
* remove(Object o)
* contains(Object o) : 해당 요소가 존재하는지 확인
* size() : 요소 개수 반환
* clear() : 모든 요소 삭제
* isEmpty() : 비어있는지 확인&#x20;

***

