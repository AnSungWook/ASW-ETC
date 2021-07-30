# Simple Json 사용 중 겪었던 이슈

## 현상

- 데이터를 JSONObject 로 변경 후 데이터를 읽어오는 과정에서 이슈가 발생
- Map 데이터를 JSONObject 로 변환
- 변환된 JSONObject 에서 .get 메소드를 활용해 value를 추출
- 읽던 도중 NullPointException 발생

## 원인

- 발생하는 원인이 뭘까... 찾아 봅시다
- 참고로 맵은 없을 경우 .get 했을때 값이 null이거나 키가 없더라도 null 값 줌

## 해결

- JSONObject 내부에서 제공하는 메소드를 이용하자
- 만약 key가 없는 경우는 .has 메소드를 이용해서 해당 키가 존재하는지 여부를 체크할 수 있다
- 하지만 key가 존재하지만 value가 null 인 경우는 위의 메소드를 이용하여 처리가 되지 않는다
- 그래서 .isNull 메소드를 이용하여 처리를 하자

### 예시

```kotlin
// 키가 있는지 여부를 체크하는 로직
// 하지만 키가 존재하고 value null 인 경우는 에러가 발생한다 NullPointException
if(JSONObject.has("_testKey")) println("키 존재함") else println("키 없음")

// 그런 경우 .isNull을 활용하자
if(JSONObject.isNull("_testKey")) println("값이 NULL") else println("값 있음")
```
