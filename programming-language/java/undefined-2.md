# 추상클래스와 오버라이딩

#### 추상 클래스와 오버라이딩

* `abstract` 클래스를 상속하면, **반드시** 추상 메서드를 구현해야 함 (안 하면 컴파일 에러)
* 추상 클래스를 쓰는 이유:
  * 부모 클래스가 구체적인 동작을 강제하지 않고, **자식에게 구현을 위임**
  * "같은 동작(메서드 이름)은 있지만 내용은 다르게" 구성 가능 → **컨트롤 일관성 유지**

### 예시로 이해하기

```java
abstract class Car {
    abstract void goForward();
}

class Sonata extends Car {
    void goForward() {
        System.out.println("소나타 앞으로 감");
    }
}

class Genesis extends Car {
    void goForward() {
        System.out.println("제네시스 앞으로 감");
    }
}

Car myCar1 = new Sonata();
Car myCar2 = new Genesis();

myCar1.goForward(); // 소나타 앞으로 감
myCar2.goForward(); // 제네시스 앞으로 감
```

#### 결론

* **상속의 목적 = 부모 기능을 재사용**보다도, **다형성을 통한 일관된 제어**가 더 중요
* 추상화는 **여러 클래스들을 동일한 인터페이스(틀)로 묶기 위해** 사용함
