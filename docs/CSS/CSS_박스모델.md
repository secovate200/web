## CSS 박스모델

1. CSS에 모든 요소는 박스모델 기반으로 렌더링 됩니다.
2. 요소의 컨텐츠,패딩,보더,마진으로 구성되어 있습니다.

### 컨텐츠(Content)

- 텍스트 또는 이미지가 들어가는 부분입니다.
- width,height속성으로 크기를 지정할수 있습니다.

```css
.element {
  width: 300px;
  height: 100px;
}
```

### 패팅(Padding)

- 컨텐츠와 보더 사이의 간격을 의미합니다.
- 요소 내부에 여백을 줄 때 사용됩니다.

```css
.element {
  padding-top: 10px; /* 상단패딩 */
  padding-right: 15px; /* 우측 패딩 */
  padding-bottom: 10px; /* 하단 패딩 */
  padding-left: 15px; /* 좌측패딩 */
}
```

- 또는 축양형으로 한번에 설정이 가능합니다.

```css
.element {
  padding: 10px 15px; /*상하10px,좌우15px */
}
```

### 보더(Border)

- 요소의 테두리를 의미합니다.
- 두께 스타일 색상을 지정할수 있습니다.

```css
.element {
  border: 2px solid red; /* 두께 2px, 실선, 빨간색*/
}
```

### 박스모델 시각화

| 항목                      | 설명                                               |
| ------------------------- | -------------------------------------------------- |
| **Content (실제 컨텐츠)** | 요소 내부에 표시되는 실제 내용 (텍스트, 이미지 등) |
| **Padding (내부 여백)**   | 컨텐츠와 테두리(Border) 사이의 여백                |
| **Border (테두리)**       | 요소의 테두리, Padding 바깥쪽에 위치함             |
| **Margin (외부 여백)**    | 요소와 다른 요소 사이의 외부 여백                  |
