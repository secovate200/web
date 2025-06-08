# 조건문

- 조건식은 어떤 연산을 통해 참(true) 혹은 **거짓(false)**를 도출하는 식입니다.

## if, else,else if

### 1. if 문 기본 형식

```js
if (조건식) {
  // 조건식이 참일 때 실행되는 코드
}
```

- if는 "만약에"라는 의미를 가집니다.

- 괄호 안의 조건식이 참이면 중괄호 안의 코드가 실행됩니다.

```js
let num = 10;
if (num > 5) {
  console.log("num은 5보다 큽니다.");
}
```

- 위 코드에서 num > 5 조건이 참이므로 console.log가 실행됩니다.

### 2. if-else 문

- 조건식이 거짓일 때 실행할 코드가 필요한 경우 else를 사용할 수 있습니다.

```js
if (조건식) {
  // 조건식이 참일 때 실행되는 코드
} else {
  // 조건식이 거짓일 때 실행되는 코드
}
```

```js
// 예시
let num = 3;
if (num > 5) {
  console.log("num은 5보다 큽니다.");
} else {
  console.log("num은 5보다 작거나 같습니다.");
}
```

### 3. else if 문

- 여러 조건을 차례대로 검사할 때 사용합니다

```js
if (조건식1) {
  // 조건식1이 참일 때 실행
} else if (조건식2) {
  // 조건식2가 참일 때 실행
} else {
  // 모든 조건이 거짓일 때 실행
}
```

```js
//예시
let num = 10;
if (num > 10) {
  console.log("num은 10보다 큽니다.");
} else if (num === 10) {
  console.log("num은 10과 같습니다.");
} else {
  console.log("num은 10보다 작습니다.");
}
```

## switch

- `switch` 문은 다수의 경우의 수(보통 3개 이상)를 다룰 때 적합하며, 여러 값 중 하나를 비교할 때 사용합니다.
- `if` 문과 마찬가지로 조건에 따라 코드를 실행하지만, 경우의 수가 많을 때 더 간단하게 작성할 수 있습니다.

```js
switch (변수) {
  case 값1:
    // 변수 값이 값1일 때 실행할 코드
    break;
  case 값2:
    // 변수 값이 값2일 때 실행할 코드
    break;
  // ... 더 많은 case 가능
  default:
  // 모든 case에 해당하지 않을 때 실행할 코드
}
```

- switch 문은 비교할 변수를 넣고, case는 그 변수의 값과 비교할 대상입니다.

- break는 해당 case 코드 실행 후 switch 문을 빠져나가는 역할을 합니다.

- 만약 break를 쓰지 않으면 다음 case의 코드도 계속 실행됩니다.

- adefault는 if 문의 else와 같으며, 모든 case에 해당하지 않을 때 실행됩니다.

```js
let fruit = "apple";

switch (fruit) {
  case "apple":
    console.log("Apple costs 100 KRW");
    break;
  case "banana":
    console.log("Banana costs 200 KRW");
    break;
  case "orange":
    console.log("Orange costs 300 KRW");
    break;
  default:
    console.log("Unknown fruit");
}
```

- 위 예시에서 fruit 값이 "apple"이므로 "Apple costs 100 KRW"가 출력됩니다.

- 만약 "banana"나 "orange"가 주어지면 해당하는 case 코드가 실행됩니다.

- 값이 어느 case에도 해당하지 않으면 default가 실행되어 "Unknown fruit"가 출력됩니다
