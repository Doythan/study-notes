# Vector(벡터)

#### Vector

* 자바에서 List 인터페이스의 구현체 중 하나
* 동적으로 크기가 변하는 배열과 같은 자료구조

***

#### 핵심 특징

* 동적 배열 : 크기를 자동으로 늘릴 수 있음&#x20;
* 동기화 : 메서드들이 멀티스레드 환경에서도 안전하지만 속도가 느려짐
* LIFO(Stack) 클래스가 `Vector`를 상속함&#x20;
* 현재 실무에서는 잘 안쓰임 대신, `ArrayList` + 필요 시 동기화 컬렉션을 사용(Collections.synchronizedList)

***

#### 요약

Vector는 동적배열 + 멀티스레드 안전하지만, ArrayList가 대세고 Vector는 레거시로 남아 있음&#x20;
