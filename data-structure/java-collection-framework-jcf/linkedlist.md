# LinkedList (연결리스트)

### JCF에서 LinkedList

JCF에서 연결 리스트를 구현한 게 바로 **LinkedList** 클래스

***

#### LinkedList 특징

* Doubly Linked List (양방향 연결리스트)
* 각 노드가 prev, next를 가진다
* 삽입/삭제 O(1) (노드를 직접 찾아가기만 하면)
* 인덱스 접근은 O(n)

***

#### 동작 원리

```java
java복사편집List<String> list = new LinkedList<>();
list.add("A");
list.add("B");
list.add("C");
```

→ 내부 구조:

```
null ← [prev | A | next ] ↔ [prev | B | next ] ↔ [prev | C | next ] → null
```

* `addFirst()` → 앞에 노드 추가
* `addLast()` → 뒤에 노드 추가
* `remove()` → 노드 레퍼런스 끊어버림

***

#### LinkedList 시간복잡도

* addFirst(): O(1)
* addLast(): O(1)
* removeFirst(): O(1)
* get(i): O(n)

> 💡 \
> “LinkedList도 사실 끝에서만 쓰면 빠른데, 인덱스 기반으로 막 써대면 ArrayList보다 느려진다.”
