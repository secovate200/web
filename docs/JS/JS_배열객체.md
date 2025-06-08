# 배열과 객체

## 1.배열과 객체의 공통점: CRUD기능

- 배열과 객체는 모두 데이터를 조작할수 있는 자료구조 입니다.
- 이둘의 공통점중 하나는 `CRUD`기능을 지원한다는 점입니다.

| 항목     | 설명              | 의미 |
| -------- | ----------------- | ---- |
| `C`reate | 데이터를 추가한다 | 생성 |
| `R`ead   | 데이터를 읽는다   | 조회 |
| `U`pdate | 데이터를 수정한다 | 수정 |
| `D`elete | 데이터를 삭제한다 | 삭제 |

## 2. 배열: 인덱스를 통한 데이터 접근

- 배열은 인덱스번호를 통해 데이터를 관리하고 접근합니다.
- 배열은 순서가 있는 데이터의 모음이며 0부터 시작하는 인덱스로 접근가능합니다.

```js
//배열 생성(Create)
const fruits = ["사과", "바나나", "오렌지"];
//배열 요소 읽기(Read);
console.log(fruits[0]); // '사과'
// 배열 요소 수정(Update)
fruits[1] = "딸기";
console.log(fruits); // ['사과', '딸기', '오렌지']
//배열 요소 삭제(Delete)
fruits.splice(2, 1); // 세번째 요소인 '오렌지' 삭제
console.log(fruits); // ['사과', '딸기]
```

## 3. 객체:키와 값으로 데이터 접근

```js
// 객체생성 (Create)
const person = {
  name: "홍길동",
  age: 25,
  city: "서울",
};
//객체 속성 읽기(Read)
console.log(person.name); // '홍길동'

//객체 속성 수정(Update);
person.age = 26;
console.log(person); // { name: '홍길동', age: 26, city: '서울' }

//객체 속성 삭제(Delete)
delete person.city;
console.log(person); // { name: '홍길동', age: 26 }
```
