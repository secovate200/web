# CSS 선택자

1. 아이디 선택자

- 특정 HTML요소 하나에만 적용됩니다.
- 이를 통해 특정 요소에만 css스타일 적용이 가능합니다.
- 아이디 선택자는 `#`기호로 사용됩니다.

  ```html
  <!DOCTYPE html>
  <html lang="ko">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>아이디 선택자 예시</title>
      <style>
        #header {
          background-color: lightblue;
          padding: 10px;
          text-align: center;
        }
      </style>
    </head>
    <body>
      <div id="header">이것은 헤더입니다</div>
    </body>
  </html>
  ```

2. 클래스 선택자

- 여러 요소에 공통적으로 적용될수 있습니다.
- `.` 기호로 사용되며 여러 요소에 동일한 스타일을 적용할때 유용합니다.

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>클래스 선택자 예시</title>
    <style>
      .highlight {
        color: red;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <p class="highlight">이 문장은 강조되었습니다 .</p>
    <p class="highlight">이 문장도 강조되었습니다 .</p>
  </body>
</html>
```

3. class vs id
   |클래스 | 차이점|
   |--|---|
   |id 선택자| 문서내에 유일, 단일 요소에 적용|
   |class 선택자| 여러 요소에 적용가능, 동일한 스타일을 사용할떄 유용|
