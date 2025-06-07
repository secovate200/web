## Flexbox:부모 요소와 자식요소의 관계

- Flexbox는 부모컨테이너( `flex-container` )와 자식요소( `flex-items` )로 구성된 레이아웃 방식입니다.
- 부모요소에 `Flexbox`를 설정하면,자식요소들은 자동으로 배치되며 다양한 정렬 및 배치방식이 가능합니다.

1. 부모요소에 display: flex 설정

- Flexbox의 기본설정은 부모요소에 `display: flex` 를 적용하는것입니다.

- Flexbox 속성을 정의하면, 자식 요소들은 자동으로 Flexbox의 규칙을 따르게 됩니다.

| 속성                | 값                    | 설명                                         | 예시 CSS 코드                     |
| ------------------- | --------------------- | -------------------------------------------- | --------------------------------- |
| **flex-direction**  | `row` (기본값)        | 자식 요소를 가로 방향으로 배치               | `flex-direction: row;`            |
|                     | `column`              | 자식 요소를 세로 방향으로 배치               | `flex-direction: column;`         |
|                     | `row-reverse`         | 가로 방향, 반대 순서로 배치                  | `flex-direction: row-reverse;`    |
|                     | `column-reverse`      | 세로 방향, 반대 순서로 배치                  | `flex-direction: column-reverse;` |
| **justify-content** | `flex-start` (기본값) | 가로축에서 왼쪽 정렬                         | `justify-content: flex-start;`    |
|                     | `center`              | 가로축에서 가운데 정렬                       | `justify-content: center;`        |
|                     | `flex-end`            | 가로축에서 오른쪽 정렬                       | `justify-content: flex-end;`      |
|                     | `space-between`       | 양 끝에 요소 배치, 나머지 공간 균등 분배     | `justify-content: space-between;` |
|                     | `space-around`        | 요소 주변에 균등한 간격 부여                 | `justify-content: space-around;`  |
| **align-items**     | `flex-start`          | 세로축에서 위쪽 정렬                         | `align-items: flex-start;`        |
|                     | `center`              | 세로축에서 가운데 정렬                       | `align-items: center;`            |
|                     | `flex-end`            | 세로축에서 아래쪽 정렬                       | `align-items: flex-end;`          |
|                     | `stretch` (기본값)    | 자식 요소가 부모 컨테이너 높이에 맞춰 늘어남 | `align-items: stretch;`           |
