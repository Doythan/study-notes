# 25년 정처기 실기 13회

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

✅ **오버라이딩**

* Parent 생성자에서 show() 호출 → Child.show() 실행

✅ **필드 숨김 (field hiding)**

* Parent.v 와 Child.v → **서로 다른 변수**
* Parent 생성자 → Parent.v 사용
* Child 생성자 → Child.v 사용

✅ **static 변수**

* total은 하나만 존재
* Parent.total = Child.total 동일



답 : 54
