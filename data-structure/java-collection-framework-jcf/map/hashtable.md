# HashTable

#### HashTable

* Hashtable은 Map 인터페이스를 구현한 클래스
* "키 - 값 쌍"을 저장하고, 동기화(synchronized) 되어 멀티스레드 안전한 자료구조

***

#### HashTable의 특징

* 동기화 (Thread-safe)
* Null 허용 X
  * null key, null value 둘 다 허용하지 않음
  * 넣으려고 하면 NullPointerException 터짐
* 해시 기반&#x20;
  * key의 hashCode 값으로 데이터를 저장
  * 검색 속도가 빠르다 (평균 O(1))&#x20;

***

#### 요약

* 실무에서 거의 안씀
* 느려서 HashMap을 쓰는게 일반적임&#x20;
