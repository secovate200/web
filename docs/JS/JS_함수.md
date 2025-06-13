## 함수의 선언과 호출

### 함수의 정의

- 함수: js상에서 기능을 설정하는 것입니다.
- 함수를 정의하려면 `function`키워드를 사용합니다.

```JS
function hello() {
 console.log("Hello, world!");
 }

```

- 여기서 hello 라는 함수가 정의되고, 이 함수는 호출될 때"Hello, world!" 를 출력하는 기능을 가집니다.

### 함수의 호출

- 호출은 정의된 기능을 실행하는 것입니다.
- 함수를 호출하면 정의된 코드가 실행됩니다.

### 매개변수(Parameter) 와 인자(Argument)

- 함수는 외부에서 값을 전달받을 수 있습니다. 이를 매개변수라고 합니다.

```JS
 function greet(name) {
 console.log("Hello, " + name);
 }
 greet("Alice");  //출력: Hello, Alice
```

- 여기서 name 이 매개변수이고, 함수 호출시 전달된 "Alice"가 인자입니다.

### 리턴값(Return Value)

- 함수는 실행 결과를 return 키워드를 사용해 호출한 곳에 값을 반환할 수 있습니다.

- return문을 만나면 함수는 즉시 종료되며, 뒤에 오는 값을 반환합니다.

```js
function add(a, b) {
  return a + b;
}

let result = add(3, 5); // result에는 8이 저장됨
console.log(result); // 출력: 8
```

- add(3, 5) 호출 시 3 + 5 결과인 8이 반환되고, result에 저장됩니다.

## 함수 선언식

```js
function hello() {
  console.log("Hello, World!");
}
```

- 형태: function 키워드로 직접 정의

- 호이스팅(O): 함수 선언식은 코드 실행 전에 메모리에 등록되므로, 정의되기 전에 호출 가능합니다.

```js
hello(); // 정상 실행: "Hello, World!"

function hello() {
  console.log("Hello, World!");
}
```

## 함수 표현식

```js
const hello = function () {
  console.log("Hello, World!");
};
```

- 형태: 함수를 변수에 할당하여 정의합니다.
- 익명 함수일 수 있습니다.
- 호이스팅(X): 변수 선언은 호이스팅되지만, 함수 정의는 런타임에 평가되므로 정의 전 호출 시 오류가 발생합니다.

```js
hello(); // (X) ReferenceError

const hello = function () {
  console.log("Hello, World!");
};
```

| 항목           | 함수 선언식                       | 함수 표현식                             |
| -------------- | --------------------------------- | --------------------------------------- |
| 정의 방법      | `function 함수명() {}`            | `const 변수명 = function() {}`          |
| 호이스팅       | O (정의 전에도 호출 가능)         | X (정의 후에만 호출 가능)               |
| 익명 함수 사용 | 불가능                            | 가능                                    |
| 일반적인 사용  | 간단한 함수나 유틸 함수에 사용    | 콜백 함수나 동적 함수에 많이 사용       |
| 권장 방식      | ❗ 혼동을 피하기 위해 표현식 권장 | ✅ `const`와 함께 함수 표현식 사용 권장 |

## 호이스팅(Hoisting)이란?

자바스크립트의 실행 전에 변수와 함수 선언이 코드의 최상단으로 끌어올려지는 현상을 말합니다
함수 선언식은 전체가 호이스팅되지만, 함수 표현식은 변수 선언만 호이스팅되고, 함수 정의는 호이스팅되지 않습니다.
