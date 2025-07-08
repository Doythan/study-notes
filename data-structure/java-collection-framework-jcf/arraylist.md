# ArrayList (배열)

JCF에서 배열을 활용한 대표 클래스가 **ArrayList**

***

#### ArrayList 특징

* 내부에 Object\[] 배열을 사용
* 초기 용량보다 커지면 새 배열을 만들어 **복사** (resize)
* 크기 변경이 자유롭지만, 결국 배열 기반이기에 삽입/삭제 비용은 높음

***

#### 내부 동작 흐름

```java
List<String> list = new ArrayList<>();
list.add("A");
list.add("B");
list.add("C");
```

→ 내부적으로는 이렇게 저장:

| Index | Value |
| ----- | ----- |
| 0     | "A"   |
| 1     | "B"   |
| 2     | "C"   |

→ 추가로 요소가 들어오면:

1. 배열 크기 초과 검사
2. 더 큰 배열 생성 (보통 1.5배 혹은 2배 크기)
3. **복사** 후 새 배열로 교체

***

#### ArrayList 시간복잡도

* get(index): O(1)
* add(E e) (끝에 추가): 평균 O(1), 가끔 O(n) (resize)
* add(index, e): O(n)
* remove(index): O(n)

> 💡 **강한 의견**\
> “ArrayList는 get() 속도는 미쳤지만, 삽입·삭제가 많으면 LinkedList로 가야 한다.”
