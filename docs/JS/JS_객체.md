# 자바스크립트 객체 정리

## 1. 객체란?

- 객체는 중괄호 `{}` 안에 **키(key)** 와 **값(value)** 쌍으로 이루어진 데이터 구조입니다.
- 값에는 문자열, 숫자뿐 아니라 함수(메소드)도 포함될 수 있습니다.

### 객체 생성 예시

```javascript
const person = {
  name: "Black",
  age: 32,
  greet: function () {
    console.log("Hello");
  },
};
person.name; // 'Black'
person.age; // 32
person.greet(); // "Hello"
```

## 2. this 키워드

| 상황               | 설명                                             | 예시                |
| ------------------ | ------------------------------------------------ | ------------------- |
| 일반 함수 호출     | `this`는 전역 객체를 가리킵니다.                 | `window`            |
| 객체 메소드 호출   | `this`는 해당 메소드를 호출한 객체를 가리킵니다. | `person`            |
| 생성자 함수 내에서 | `this`는 생성된 인스턴스 객체를 가리킵니다.      | `new`로 생성된 객체 |

```js
// 일반함수 호출
function showThis() {
  console.log(this); // 브라우저 환경에서는 window
}
showThis();

// 객체메소드 호출
const person = {
  name: "Alice",
  greet: function () {
    console.log(this.name); // 'Alice'
  },
};
person.greet();
// 생성자 함수
function Person(name) {
  this.name = name;
}
const p = new Person("Bob");
console.log(p.name); // 'Bob'
```

## 3. 프로토타입 (Prototype)

- 자바스크립트의 객체 상속을 담당하는 개념입니다.

- 모든 객체는 부모 객체로서 프로토타입을 가지며, 공통된 메소드를 공유합니다.

```js
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function () {
  console.log(`${this.name} makes a noise.`);
};

const dog = new Animal("Dog");
dog.speak(); // 'Dog makes a noise.'
```

- `dog` 객체는 `speak` 메소드를 직접 가지고 있지 않지만, 프로토타입을 통해 접근 가능합니다

## 4. 프로토타입 체인 (Prototype Chain)

- 객체에 없는 메소드를 호출하면, 자바스크립트는 그 객체의 프로토타입을 통해 메소드를 찾습니다.

- 이것이 프로토타입 체인입니다.

```js
console.log(dog.hasOwnProperty("name")); // true
console.log(dog.hasOwnProperty("speak")); // false
// dog 객체에는 speak가 없지만, 프로토타입 체인을 통해 Animal.prototype.speak 접근 가능
```
