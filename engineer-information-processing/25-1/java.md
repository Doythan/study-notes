# JAVA 문제들

#### 5. 다음은 Java 코드에 대한 문제이다. 아래 코드를 확인하여 알맞는 출력값을 작성하시오.

```java
public class Main {
 
  public static void main(String[] args) {
 
    int a=5,b=0;
 
    try{
      System.out.print(a/b);
    }catch(ArithmeticException e){
      System.out.print("출력1");
    }catch(ArrayIndexOutOfBoundsException e) {
      System.out.print("출력2");
    }catch(NumberFormatException e) {
      System.out.print("출력3");
    }catch(Exception e){
      System.out.print("출력4");
    }finally{
      System.out.print("출력5");
    }
  }
}

답 : 출력1출력5
```



#### 13. 다음은 Java 코드에 대한 문제이다. 아래 코드를 확인하여 알맞는 출력값을 작성하시오.

<pre class="language-java"><code class="lang-java"><strong>public class Main {
</strong>    public static void main(String[] args) {
        new Child();
        System.out.println(Parent.total);
    }
}

class Parent {
    static int total = 0;
    int v = 1;
 
    public Parent() {
        total += (++v);
        show();    
    }
 
    public void show() {
        total += total;
    }
}

class Child extends Parent {
    int v = 10;
 
    public Child() {
        v += 2;
        total += v++;
        show();
    }
 
    @Override
    public void show() {
        total += total * 2;
    }
}
</code></pre>

#### 핵심 개념&#x20;

**오버라이딩**

* Parent 생성자에서 show() 호출 → Child.show() 실행

**필드 숨김 (field hiding)**

* Parent.v 와 Child.v → **서로 다른 변수**
* Parent 생성자 → Parent.v 사용
* Child 생성자 → Child.v 사용

**static 변수**

* total은 하나만 존재
* Parent.total = Child.total 동일



답 : 54
