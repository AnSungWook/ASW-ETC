# Varargs : 가변인자

- JAVA 5.0에서 소개되는 기법 중에서 가변인수(Varargs)
- 가변인수라는 것은 필요에 따라 매개변수(인수)를 가변적으로 조정할 수 있는 기술
- 가변인수가 없던 시절에는 가변인수 대신 컬렉션이나 배열을 이용해서 가변인수를 대체하고 있었다.

**kotlin**

```kotlin
    fun varargsTestFunction(vararg varargs: Any) {
        // TODO 가변인수를 사용한 작업 ( 배열이나 컬렉션 Array로 보면 편하다 )
    }

    fun action() {
        varargsTestFunction("1", "2", "5", 1, 2)
    }
```

**java**

```java
    public Object varargsTestFunction(String... varargs) {
        // TODO 가변인수를 사용한 작업 ( 배열이나 컬렉션 Array로 보면 편하다 )
    }

    public static void main(String[] args) {
        varargsTestFunction("1", "2", "5")
    }
```

> 자바는 근데 Vector로 해서 Object 형태로 뽑아내더라 나중에 java에서 한번 써보자.

---
