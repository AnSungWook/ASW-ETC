# Kotlin ForEach continue, break 사용하기

## 현상

- 데이터를 반복 해야 하는 경우 ForEach 메소드를 이용함
- 그런데 kotlin forEach는 일반적으로 사용되는 break, continue가 안먹힘

## 원인

- 실행을 위해 코드를 작성해보면 break, continue는 only loop 에서만 이라고 뜬다
- 그럼 forEach는? **loop**가 아닌 **Stream**
- [Stream은 loop가 아니다](https://www.popit.kr/java8-stream%EC%9D%80-loop%EA%B0%80-%EC%95%84%EB%8B%88%EB%8B%A4/)

## 해결

- 그래서 이걸 어떻게 사용하느냐
- Kotlin 공식 사이트에 사용법이 있음
- [Returns and jumps](https://kotlinlang.org/docs/returns.html)

```kotlin
// continue
fun foo() {
    listOf(1, 2, 3, 4, 5).forEach {
        if (it == 3) return@forEach // local return to the caller of the lambda - the forEach loop
        print(it)
    }
    print(" done with implicit label")
}

// break
fun foo() {
    run loop@{
        listOf(1, 2, 3, 4, 5).forEach {
            if (it == 3) return@loop // non-local return from the lambda passed to run
            print(it)
        }
    }
    print(" done with nested loop")
}
```
