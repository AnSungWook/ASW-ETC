# Computed Property - 동적으로 변수 데이터 받기

## 요구조건

- 데이터를 내려주고 받고 하다보면 List안에 특정한 Class 형태로 데이터를 내려주는 경우가 많음
- 그런데 종종 key, value 형태로만 존재하는 데이터 리스트가 존재하기도 함
- 근데 이걸 JavaScript 에서 쓰려고 하니 불편함
- 아 물론 일반적으로 list를 map 해서 데이터를 추출 하는데에는 안 불편함
- 단지 이 CustomClass안의 특정 값이 key가 되어야 되는 상황이 발생할 수도 있음
- **예시**

```javascript
val list = [{
    key: "column1",
    value: "test-value1",
},{
    key: "column2",
    value: "test-value2",
}];
```

- 위와 같은 형태의 데이터가 존재 할때 내가 원하는 데이터의 view 형태가 column1, column2 의 형태를 취해야 한다!
- 그 때 이 기능이 굉장히 좋음

## 사용법

- **예시**

```javascript
var object = new Object();
val list = [{
    key: "column1",
    value: "test-value1",
},{
    key: "column2",
    value: "test-value2",
}];

list.forEach(data => {
    object[data.key] = value;
});
```

- 어 근데 내가 필요한건 이게 아니고 List에 담긴 Object가 필요하다

- **예시**

```javascript
val list = [{
    key: "column1",
    value: "test-value1",
},{
    key: "column2",
    value: "test-value2",
}];

list.map(data => ({
    [data.key]: data.value
}));
```

- 핵심은 *[ ]* 안에 키로 쓸 데이터를 넣는것!
- 요것을 일컬어 **계산된 프로퍼티(computed property)** 라고 함 (변수 내에서 프로퍼티 이름을 동적으로 받아옴)
