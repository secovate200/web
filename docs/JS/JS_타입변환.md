# 타입변환( 암시적변환, 명시적변환)

## 형변환 정리

- 데이터타입을 변경하는 과정을 `형변환` 이라고 합니다.
- 크게 `암시적 형변환`, `명시적 형변환`이 있습니다.

### 1. 암시적형변환

- 자바스크립트가 자동으로 데이터타입을 변환하는 방식을 말합니다.
- 코드를 작성하지 않아도 js가 알아서 데이터를 다른 타입으로 변환합니다.

```js
let num = 1;
let str = "2";
console.log(num + str); // "12" (숫자 1이 문자열로 변환됨
```

#### Boolean 과 숫자의 암시적 형변환

```js
let isTrue = true;
let number = 3;
console.log(isTrue + number); // 4 (true는 1로 변환됨)
```

- boolean값 `true`는 숫자 1로 변환되고, 숫자와 더해져 결과는 4가 됩니다.

### 2. 명시적 형변환

- 명시적 형변환은 개발자가 직접 코드를 작성여 타입을 변환하는 방식입니다.
- 강제적으로 데이터타입을 변경 할 수 있습니다.

1. 숫자를 문자열로 변환

```js
let num = 123;
let str = String(num); // 숫자를 문자열로 변환
console.log(str); // "123"
console.log(typeof str); // string
```

- `String` 함수는 숫자값을 문자열로 변환해줍니다.

2. 문자열을 숫자로 변환

```js
let str = "123";
let num = Number(str); //문자열을 숫자로 변환
console.log(num); // 123
console.log(typeof num); // number
```

- `number()`함수는 문자열을 숫자로 변환해줍니다.

3. Boolean을 숫자로 변환

```js
console.log(Number(true)); // 1
console.log(Number(false)); // 0
```

- boolean값 `true`는 숫자1로 `false`는 숫자0으로 변환됩니다.

4. 주요함수

| 함수        | 설명                            | 예시 코드       | 결과     |
| ----------- | ------------------------------- | --------------- | -------- |
| `String()`  | 숫자나 불리언을 문자열로 변환   | `String(123)`   | `"123"`  |
|             |                                 | `String(true)`  | `"true"` |
| `Number()`  | 문자열이나 불리언을 숫자로 변환 | `Number("123")` | `123`    |
|             |                                 | `Number(true)`  | `1`      |
|             |                                 | `Number(false)` | `0`      |
| `Boolean()` | 숫자나 문자열을 불리언으로 변환 | `Boolean(0)`    | `false`  |
|             |                                 | `Boolean(1)`    | `true`   |
|             |                                 | `Boolean("")`   | `false`  |

|
