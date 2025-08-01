## 변수선언(var ,let ,const )

1. 변수선언

- 자바스크립트에서 변수선언할 때에 var,let,const를 사용할수 있습니다.

  ```javascript
  let age; // age라는 이름의 변수를 선언
  ```

2. 값 대입

- 변수에 값을 대입할때 `=`대입연산자를 사용합니다.
  ```javascript
  let age = 34; // age라는 이름의 변수를 선언후 34라는 값을 넣는다.
  let a; //a라는 이름의 변수선언
  a = 10; // a 라는변수에 10을 대입
  ```

| 키워드    | 특징                                  | 값 변경 가능 여부 | 스코프                       | 사용 권장 여부         | 예시                      |
| --------- | ------------------------------------- | ----------------- | ---------------------------- | ---------------------- | ------------------------- |
| **let**   | 변수를 선언, 값 변경 가능             | 가능              | 블록 스코프 (block scope)    | 권장 (최신 문법)       | `let age = 34; age = 35;` |
| **const** | 상수 선언, 선언과 동시에 값 할당 필수 | 불가              | 블록 스코프                  | 권장 (불변값에 사용)   | `const birthYear = 1990;` |
| **var**   | 기존 변수 선언 방식, 함수 스코프      | 가능              | 함수 스코프 (function scope) | 비권장 (ES6 이전 방식) | `var name = 'John';`      |

3. 동적 타이핑 (Dynamic Typing)

자바스크립트는 **동적 타입 언어**입니다.  
이는 변수를 선언할 때 별도로 타입을 지정하지 않아도, 할당된 값에 따라 자동으로 타입이 결정된다는 의미입니다.

```javascript
let age = 34; // 숫자 타입
let name = "John"; // 문자열 타입
let isAdult = true; // 불리언 타입 (true/false)
```
