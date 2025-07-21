# SOLID 원칙(객체지향설계)

## 객체지향 설계 원칙 - SOLID

### SOLID란?

객체지향 설계의 5가지 핵심 원칙으로, **유지보수성**, **확장성**, **유연성**을 확보하기 위해 반드시 알아야 할 규칙.

***

#### 1. SRP - 단일 책임 원칙 (Single Responsibility Principle)

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

* **클래스는 하나의 책임만 가져야 한다**
* 책임이 많아질수록 클래스는 변경될 이유가 많아지고, 결합도도 상승함
* → 객체의 "상태"와 "책임"을 명확히 구분해야 함
* 커피머신 떠올리기 (분쇄기, 추출기 각각의 클래스로 만들기)
* 유지보수시 유리 단위테스트와 통합테스트 둘 다 가능하여 여러가지로 유리

```
❌ Bad: User 클래스가 DB처리, 이메일 발송, UI까지 전부 처리
✅ Good: User, UserRepository, EmailService 등으로 역할 분리
```

#### 2. OCP - 개방/폐쇄 원칙 (Open/Closed Principle)

* **확장에는 열려(Open)** 있고, **수정에는 닫혀(Closed)** 있어야 한다
* 기존 코드를 변경하지 않고, 기능을 추가할 수 있어야 한다

```
❌ if-else 문으로 기능 분기
✅ 전략 패턴, 추상 클래스/인터페이스로 대체
```

***

#### 3. LSP - 리스코프 치환 원칙 (Liskov Substitution Principle)

* **자식 클래스는 언제나 부모 클래스를 대체할 수 있어야 한다**
* 상속을 썼다면, 부모 타입으로 자식 객체를 써도 문제가 없어야 한다

```java
✅ Animal a = new Dog(); // OK
❌ Rectangle을 상속한 Square가 setWidth()를 깨뜨리는 경우 → 위반
```

***

#### 4. ISP - 인터페이스 분리 원칙 (Interface Segregation Principle)

* **특정 클라이언트를 위한 인터페이스로 분리하라**
* 너무 많은 기능을 한 인터페이스에 몰아넣지 말고, 역할 단위로 쪼개야 한다

```java
❌ interface Printer { print(); scan(); fax(); }  
✅ interface Printable { print(); }, interface Scannable { scan(); }
```

***

#### 5. DIP - 의존 역전 원칙 (Dependency Inversion Principle)

* **구체적인 클래스가 아닌, 추상(인터페이스)에 의존하라**
* 의존 대상이 바뀌어도 시스템은 유연하게 동작해야 한다

```java
// ❌ Bad
class Door {
    Key key = new DigitalKey(); // 구체 클래스에 의존

// ✅ Good
interface Key { void unlock(); }
class Door {
    private final Key key;
    Door(Key key) { this.key = key; }
}
```
