# PriorityQueue(우선순위 큐)

#### 참고

* 자료구조 개념으로 보면 → 우선순위 큐는 **힙**
* 자바 라이브러리 계층도로 보면 → Queue 밑에 놓임.

***

#### 우선순위 큐

* **우선순위 큐 (PriorityQueue)**
  * 가장 작은 값이나 큰 값을 빠르게 꺼내는 자료구조
  * Java에선 `PriorityQueue` 클래스 사용
  * 기본은 Min-Heap (작은 값이 우선순위 높음)
* 관련 메서드 및 시간복잡도:
  * `poll()`, `offer()` 모두 O(log N)
  * `poll() : 꺼내고 지우기`  `offer() : 넣기`
