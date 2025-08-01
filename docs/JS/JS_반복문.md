### for

```js
for (초기화식; 조건식; 증감식) {
  //반복할 코드;
}

//예시
for (let i = 0; i < 5; i++) {
  console.log("안녕", i);
}
```

위 코드는 `i`가 0부터 4까지 1씩 증가하면서 "안녕"을 출력합니다.

- 초기화식: 반복문을 시작할 때 한 번 실행되는 코드 (주로 반복 변수 선언)

- 조건식: 반복을 계속할지 판단하는 조건 (false가 되면 종료)

- 증감식: 반복이 한 번 끝난 후 실행되는 코드 (주로 반복 변수 변경)

### while

```js
while (조건식) {
  // 조건이 true인 동안 반복 실행할 코드
}
// 예시 : i가 0부터 4까지 1씩증가하며 "안녕"을 출력
let i = 0;
while (i < 5) {
  console.log("안녕", i);
  i++;
}
```

- 조건을 먼저 평가한 뒤, true일 경우 블록 안 코드를 실행
- 조건이 처음부터 false면 한 번도 실행되지 않을 수 있음

### do-while

```js
do {
  // 최소 한 번은 실행될 코드
} while (조건식);

// i가 0부터 4까지 1씩 증가하며 "안녕"을 출력합니다.
let i = 0;
do {
  console.log("안녕", i);
  i++;
} while (i < 5);
```

- 먼저 코드를 한 번 실행한 후, 조건을 검사하여 반복 여부 결정

- 조건이 처음부터 false라도 최소 1회는 실행
