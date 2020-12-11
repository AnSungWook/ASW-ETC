# HTML이란?

- HTML은 하이퍼 텍스트 마크업 언어를 의미
- HTML은 웹 페이지의 표준 마크업 언어
- HTML 요소(Element)는 HTML 페이지의 구성 요소
- HTML 요소는 `<>` 태그로 표현 됨

#### HTML 요소

- HTML 요소는 start 태그와 end 태그 사이에 내용이 포함된 태그

#### HTML 속성

- HTML 요소에는 attributes(특성)이 있을 수 있음
- attributes는 태그에 대한 추가 정보를 제공
- attributes는 charterset="utf-8"과 같은 이름/값을 쌍으로 제공
- EX

```HTML
<!DOCTYPE html>
<html lang="en">

<meta charset="utf-8">
<title>Page Title</title>

<body>
<h1>This is a Heading</h1>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
</body>

</html>
```

- HTML 태그 분석
  - `<!DOCTYPE html>` 선언은 이 문서를 HTML5로 정의
  - `<html>` 요소는 HTML 페이지의 루트 요소
  - `lang` 속성은 문서의 언어를 정의
  - `<meta>` 요소에 문서에 대한 메타 정보가 포함
  - `charset` 속성은 문서에 사용된 문자 집합을 정의
  - `<title>` 요소는 문서의 제목을 지정
  - `<body>` 요소에 표시되는 페이지 내용이 포함
  - `<h1>` 요소가 큰 제목을 정의
  - `<p>` 요소는 단락을 정의

---

> 출처

[[What is HTML? - W3Schools]](https://www.w3schools.com/whatis/whatis_html.asp)