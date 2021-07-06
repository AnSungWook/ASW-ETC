# Stream, Stream.Collectors

- JAVA 8.0 제공하는 배열, List등의 요소들의 처리를 담당하는 Class
- 기존의 배열처리를 간단하게 해주며, functional style로 처리할 수 있도록 해줌
- 병렬처리, Optional 등 다양한 처리를 할 수 있도록 지원해줌

**kotlin**

```kotlin
  fun convertStringToList(): List<String>{
    val specificString = "TEST1:TEST2:TEST3"
    return specificString.split(":").map {it}.toList()
  }
```

> java에서도 사용되는 방식은 비슷하다 ( .asList )
그 외에도 chain 형식으로 데이터의 구조를 변경한다던지 데이터를 변경 하거나 추출한다던지 하는데 유용해서 좋음