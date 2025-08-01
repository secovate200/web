## CSS 레이아웃 구성: Display와 Position

- CSS 레이어 구성은 주로 **디스플레이(Display)**와 **포지션(Position)**으로 이루어집니다.

- 두 속성은 HTML태그를 화면에 배치하는 데 중요한 역할을합니다.

### 1. Display(디스플레이)

- 요소가 2차원 또는 3차원 공간을 차지하는지 결정합니다.
- 요소가 영역을 차지하는 방식과 다른 요소들과의 관계를 정의할수 있습니다.

| 표시 방식 (Display) | 설명                                                                                |
| ------------------- | ----------------------------------------------------------------------------------- |
| **block**           | 요소가 **전체 가로 폭을 차지**하며, 다음 요소는 **아래로 배치**됩니다.              |
| **inline**          | 요소가 **컨텐츠 크기만큼의 영역**만 차지하며, 다음 요소가 **같은 줄**에 배치됩니다. |
| **none**            | 요소를 **화면에서 숨기고**, **레이아웃에서도 제외**됩니다.                          |

```css
/* 블록 요소: 전체 가로 폭을 차지하며, 다음 요소는 아래로 배치됨 */
.element-block {
  display: block;
}

/* 인라인 요소: 컨텐츠 크기만큼만 차지하며, 다음 요소는 같은 줄에 배치됨 */
.element-inline {
  display: inline;
}

/* 숨김 요소: 화면에 표시되지 않으며, 레이아웃에도 영향을 주지 않음 */
.element-none {
  display: none;
}
```

| 구분                         | `block` 요소                          | `inline` 요소                                     |
| ---------------------------- | ------------------------------------- | ------------------------------------------------- |
| **줄 배치**                  | 새로운 줄에서 시작됨                  | 같은 줄에서 다른 요소와 나란히 배치됨             |
| **가로 폭 차지**             | 부모 요소의 **전체 가로 폭을 차지함** | **컨텐츠 크기만큼만 차지함**                      |
| **크기 조절 (width/height)** | `width`와 `height` 속성 적용 가능     | `width`와 `height` 속성 적용 **불가 또는 제한적** |
| **대표 태그 예시**           | `<div>`, `<p>`, `<h1>` 등             | `<span>`, `<a>`, `<strong>` 등                    |
| **레이아웃 사용 용도**       | 구조적 레이아웃을 구성할 때 사용      | 텍스트 안에서 스타일링이 필요할 때 사용           |

### 2. Position(포지션)

- `position` 속성은 요소가 페이지에서 어디에 배치될지를 결정합니다.

  | `position` 값 | 설명                                                                          |
  | ------------- | ----------------------------------------------------------------------------- |
  | **static**    | **기본값**. 요소는 문서의 **일반적인 흐름**에 따라 배치됨 (좌표 이동 불가)    |
  | **relative**  | 요소는 **자기 자신을 기준**으로 이동 가능. 원래 위치는 유지됨                 |
  | **absolute**  | 요소는 **가장 가까운 `position`이 설정된 조상 요소**를 기준으로 배치됨        |
  | **fixed**     | 요소는 **브라우저 창을 기준**으로 고정되며, **스크롤해도 위치가 변하지 않음** |

```css
/* 기본 흐름에 따라 배치됨 (좌표 이동 불가) */
.element-static {
  position: static;
}

/* 자신을 기준으로 위치 이동 (원래 자리 차지함) */
.element-relative {
  position: relative;
  top: 10px;
  left: 20px;
}

/* 가장 가까운 position 지정된 부모를 기준으로 절대 위치 */
.element-absolute {
  position: absolute;
  top: 50px;
  right: 30px;
}

/* 브라우저 창을 기준으로 고정 (스크롤해도 위치 유지) */
.element-fixed {
  position: fixed;
  bottom: 0;
  right: 0;
}
```

#### position 속성별 차이점

| `position` 값 | 기준 위치                                 | 배치 특징                                                                 |
| ------------- | ----------------------------------------- | ------------------------------------------------------------------------- |
| **static**    | 문서의 기본 흐름                          | 기본 배치 방식. 위치를 이동할 수 없음 (좌표 속성 `top`, `left` 등 무시됨) |
| **relative**  | 자기 자신의 **원래 위치**                 | 원래 위치를 기준으로 **이동 가능**, 이동해도 공간은 그대로 유지됨         |
| **absolute**  | 가장 가까운 `position` 지정 **부모 요소** | 해당 부모 요소를 기준으로 위치 지정. 부모가 없으면 `body` 기준으로 배치됨 |
| **fixed**     | **브라우저 창(뷰포트)**                   | 화면을 기준으로 **고정**, 스크롤해도 같은 위치에 **항상 유지됨**          |

- absolute는 조상 중 relative, absolute, fixed 중 하나가 있어야 해당 요소를 기준으로 합니다. 없으면 body 기준.

- static은 좌표 지정이 불가능하여 레이아웃 제어에는 사용되지 않습니다.
