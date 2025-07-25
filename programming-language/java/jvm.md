# JVM 구조와 자바 실행 원리

### 자바(Java)와 JVM의 구조 및 실행 과정

#### 1. 자바 프로그램의 실행 흐름

```
Application (자바 코드) → JVM → OS → 하드웨어
```

* **Application**: 우리가 작성하는 코드 (Java, C 등)
* **JVM (Java Virtual Machine)**: 자바 코드를 OS와 독립적으로 실행하게 해줌
* **OS (운영체제)**: 하드웨어와 소통 (Shell 언어로 간접 제어)
* **하드웨어**: 최종적으로 2진수로 명령을 받아 작동

***

#### 2. 자바와 C 언어의 차이점

| 구분      | Java                                | C                         |
| ------- | ----------------------------------- | ------------------------- |
| 플랫폼 독립성 | JVM 덕분에 OS 상관없이 실행 가능               | OS마다 따로 컴파일 필요            |
| 실행 방식   | `.java` → 컴파일 → `.class` → JVM에서 실행 | `.c` → 컴파일 → OS별 실행 파일 생성 |

***

#### 3. 자바의 실행 단계

```plaintext
.java (소스 코드)
   ↓ 컴파일 (javac)
.class (바이트코드)
   ↓ 실행 (java 명령어 → JVM)
프로그램 실행
```

***

#### 요약

* JVM 덕분에 **Write Once, Run Anywhere** (한 번 작성, 어디서든 실행) 가능
* 자바는 **컴파일된 바이트코드를 JVM이 실행**하므로 운영체제에 독립적
* 반면, C 언어는 운영체제에 맞게 **직접 컴파일**해야 해서 OS 종속적
