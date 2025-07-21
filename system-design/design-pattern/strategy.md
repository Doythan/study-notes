# Strategy(전략) 패턴

## 디자인 패턴 - 전략 패턴 (Strategy Pattern)

### 전략 패턴이란?

* **알고리즘(전략)을 캡슐화**해서 런타임에 자유롭게 바꿀 수 있도록 하는 패턴
* 실행 방법을 고정하지 않고, **행동을 객체화해서 주입**하는 방식
* 주요 목적: **코드 수정 없이 동작을 교체할 수 있도록 하기**

## 전략 패턴 예제 - 동물 쫓아내기

### 기존 구조

다형성과 추상화만 사용된 구조. `Doorman` 클래스가 `Animal`의 자식 객체들을 쫓아냄.

#### 구조 요약

* `Animal`: 추상 클래스 (`getName()` 메서드를 추상화)
* `Mouse`, `Tiger`, `Cat`: `Animal`을 상속받아 각 동물의 이름 정의
* `Doorman`: `Animal`을 받아서 `getName()`으로 동물의 이름을 가져와 쫓아냄

```java
public class Doorman {
    public void 쫓아내(Animal a){
        System.out.println(a.getName() + " 나가 !!");
    }
}
```

### 📌 구조 변화 (전략 패턴 적용)

#### 1. 전략 인터페이스 정의

```java
public interface Strategy {
    void runAway();
}
```

***

#### 2. 동물마다 전략 구현

```java
jpublic class MouseStrategy implements Strategy {
    public void runAway() {
        System.out.println("쥐가 찍~ 도망갑니다.");
    }
}

public class TigerStrategy implements Strategy {
    public void runAway() {
        System.out.println("호랑이가 으르렁거리며 사라집니다.");
    }
}

public class CatStrategy implements Strategy {
    public void runAway() {
        System.out.println("고양이가 야옹~ 하며 도망갑니다.");
    }
}
```

***

#### 3. Doorman 클래스 리팩토링

```java
public class Doorman {
    private Strategy strategy;

    public Doorman(Strategy strategy) {
        this.strategy = strategy;
    }

    public void 쫓아내() {
        strategy.runAway();
    }
}
```

***

#### 4. 실행 코드

```java
public class App {
    public static void main(String[] args) {
        Doorman d1 = new Doorman(new MouseStrategy());
        d1.쫓아내();

        Doorman d2 = new Doorman(new TigerStrategy());
        d2.쫓아내();

        Doorman d3 = new Doorman(new CatStrategy());
        d3.쫓아내();
    }
}
```

***

### ✅ 전략 패턴을 적용한 장점

| 항목     | 설명                                       |
| ------ | ---------------------------------------- |
| OCP 만족 | 새로운 전략을 추가해도 기존 `Doorman` 수정 없음          |
| DIP 만족 | `Doorman`은 전략 인터페이스에만 의존                 |
| 유연성    | 실행 중 전략 교체도 가능                           |
| SRP 만족 | 동작과 실행 책임이 분리됨 (`Doorman` vs `Strategy`) |

***

### 📎 정리 한 줄 요약

> 쫓아내는 **행동을 전략(객체)** 으로 분리하여, **Doorman은 추상에만 의존**하게 만드는 것이 전략 패턴의 핵심이다.
