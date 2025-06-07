## 1. 기본적인 데이터 타입

### 1-1. 숫자 (Number)

자바스크립트에서 숫자는 정수와 소수 모두 포함됩니다.  
심지어 **무한대 (Infinity)** 도 숫자 타입에 속합니다.

```js
let age = 37; // 정수
let height = 1.75; // 소수
let infinityNum = Infinity; // 무한대
```

### 1-2. 문자열 (String)

- 문자열은 문자들의 집합이며, 큰 따옴표(" ")나 작은 따옴표(' ')로 감싸서 표현합니다.
- 백틱(`)을 사용하면 문자열 내에서 변수를 표현할 수 있습니다. 이를 템플릿 리터럴이라고 합니다.

```js
let name = "John"; // 큰 따옴표 사용
let greeting = "Hello!"; // 작은 따옴표 사용

let age = 37;
let message = `Hello, I am ${age} years old.`; // 템플릿 리터럴
```

### 1-3. 불리언 (Boolean)

불리언은 참(True) 또는 거짓(False)만을 값으로 가질 수 있습니다.
조건문에서 주로 사용됩니다.

```js
let isAdult = true;
let hasLicense = false;

if (isAdult) {
  console.log("You are an adult.");
} else {
  console.log("You are not an adult.");
}
```

### 1-4. 객체 (Object)

객체는 키-값 쌍으로 구성된 복합 데이터 타입입니다.
점 표기법(dot notation)이나 대괄호 표기법(bracket notation)으로 접근합니다.

```js
let person = {
  name: "John",
  age: 34,
  isMarried: false,
};

console.log(person.name); // John
console.log(person["age"]); // 34
```

### 1-5. 배열 (Array)

- 배열은 여러 개의 값을 순서대로 나열할 수 있는 데이터 타입입니다.
- 대괄호([])로 선언하며, 인덱스(0부터 시작)를 통해 요소에 접근합니다.

```js
let members = ["Minji", "Hanni", "Danielle"];

console.log(members[0]); // Minji
console.log(members[1]); // Hanni
```

## 2. 추가적인 데이터 타입

### 2-1. null

null은 값이 없음을 나타내는 특수 값으로, 변수가 명시적으로 비어있음을 표현할 때 사용됩니다.

```js
let car = null; // 값이 없음
```

### 2-2. undefined

undefined는 변수가 선언되었지만 값이 할당되지 않은 상태를 나타냅니다.

```js
let car;
console.log(car); // undefined
```

## 3. 동적 타이핑 (Dynamic Typing)

자바스크립트는 동적 타이핑 언어입니다. 변수를 선언할 때 타입을 지정하지 않으며, 할당된 값에 따라 타입이 자동으로 결정됩니다.

```js
let value = 10; // 숫자
value = "Hello"; // 문자열
value = true; // 불리언
```

## 4. 배열과 객체

### 4-1. 배열 안에 배열 (다차원 배열)

```js
let nestedArray = [
  [1, 2],
  [3, 4],
  [5, 6],
];

console.log(nestedArray[0]); // [1, 2]
console.log(nestedArray[0][1]); // 2
```

### 4-2. 배열과 객체 혼합

```js
let team = [
  { name: "Minji", age: 19 },
  { name: "Hanni", age: 18 },
  { name: "Danielle", age: 19 },
];

console.log(team[0].name); // Minji
```

## 5. 값과 객체의 차이점

### 5-1. 값 (Value)

값은 독립적인 의미를 가지는 데이터입니다.
숫자, 문자열, 불리언 등이 값으로 취급됩니다.

```js
let number = 17; // 숫자 값
let greeting = "Hello"; // 문자열 값
let isTrue = true; // 불리언 값
```

### 5-2. 객체 (Object)

객체는 여러 값이나 프로퍼티를 하나의 단위로 묶어 관리할 수 있는 복합 데이터 타입입니다.

```js
let person = {
  name: "John",
  age: 34,
  isMarried: false,
};
```

## 6. null과 undefined

### 6-1. null

- 명시적으로 "값이 없음"을 의미하는 데이터 타입

- 개발자가 의도적으로 설정함

```js
let emptyValue = null;
console.log(emptyValue); // null
```

### 6-2. undefined

- 변수가 선언되었으나 값이 할당되지 않은 상태

- 자바스크립트가 자동으로 할당함

```js
let a;
console.log(a); // undefined

a = 10;
console.log(a); // 10
```

### 6-3. 차이점

| 구분        | 의미                          | 할당 주체                |
| ----------- | ----------------------------- | ------------------------ |
| `null`      | 명시적으로 값이 없음을 나타냄 | 개발자가 직접 설정       |
| `undefined` | 값이 할당되지 않은 상태       | 자바스크립트가 자동 할당 |

```js
let a = null;
let b;
console.log(a); // null (값이 없음을 명시)
console.log(b); // undefined (선언만 되고 값 없음)
```
