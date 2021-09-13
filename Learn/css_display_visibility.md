# CSS display 와 visibility

## 현상

- 화면에 특정 element를 안보이게 했다가 다시 보이게하는 과정 중 발생
- width을 auto로 해두고 작업 하니 element가 표시 될때 width이 자동으로 늘,줄 됨

## 원인

- display는 해당 element가 html 문서에 존재 하지 않음
- 그렇기에 display:none 상태를 해제 했을때 element가 문서에 추가됨에 따라 width이 변경 됨

## 해결

- 하지만 visibility는 html 문서내에 element가 존재하지만 가려 놓기만 함
- 그래서 visibility:hidden 상태를 해제 했을때 이미 존재하는 element를 보여주기만 하므로 width이 변경하거나 하지 않음

> 특정 element를 아예 새로 추가하는 경우에는 display를 이용하고 가리기만을 위한 기능으로는 visibility를 사용하자
