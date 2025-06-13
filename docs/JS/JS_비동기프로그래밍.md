## 비동기 프로그래밍 개념

- 여러 작업을 병행하여 처리합니다.
- 하나의 작업이 완료 되지 않아도 다른 작업을 동시에 시작할수 있습니다.
- 자바스크립트에서 비동기 작업은 이벤트 루프를 통해 처리되며 이 작업은 병행성을 가지고 있습니다.
- 여러 작업을 동시에 시작하진 않지만 한 작업이 완료될떄까지 다른작업을 처리하는 것을 의미합니다.

## 장점

- 성능: 작업이 병렬실행되므로 전체적인 작업처리 시간이 단축됩니다.
- 효울성: 시간이 오래걸리는 작업이 진행되는 동안에도 다른작업이 진행될수 있어 시스템 자원을 효율적으로 사용할수 있습니다.

## 단점

- 가독성: 비동기 작업이 많은 경우 가독성이 떨어질수 있습니다..
  - 무분별 callback
- 디버깅의 어려움: 비동기 작업은 언제 완료될지 미리 알수 없기 떄문에 에러가 발생하였을 경우 원인 추적이 어렵습니다.

### 1. 병행성과 동시성

| 개념                     | 설명                                                                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **병행성 (Concurrency)** | 여러 작업을 **번갈아 가며 실행**하는 방식. 자바스크립트는 **단일 스레드** 환경에서 병행성을 통해 여러 작업을 중단하지 않고 동시에 처리되는 것처럼 보이게 함. |
| **동시성 (Parallelism)** | 여러 작업을 **실제 동시에 실행**하는 방식. **멀티스레드 환경**에서 가능. 자바스크립트는 기본적으로 단일 스레드이기 때문에 비동기 작업은 병행성 기반.         |

### 2. 콜백 함수 (Callback Function)

- 파라미터로 전달받은 함수를 말합니다.

```js
function orderFood(food, callback) {
  console.log(`${food} 주문을 시작해요.`);
  setTimeout(function () {
    console.log(`${food}가 배달되었어요!`);
    callback(); // 음식이 도착하면 콜백 함수 실행
  }, 3000); // 3초 후 실행
}

orderFood("피자", function () {
  console.log("맛있게 먹어요!");
});
```

### 3. Promise(프로미스)

- 자바스크립트는 비동기 처리를 위해 콜백함수를 사용하지만 이를 너무 남용할 경우 콜백 지옥에 빠질 수 있습니다.
- 이것을 보완하며 비동기 처리에 사용되는 객체를 프로미스 라고 합니다.
- JavaScript의 Promise는 비동기 작업의 성공 또는 실패를 나타내는 객체입니다.

```javascript
const orderFood = new Promise((resolve, reject) => {
  const isDelivered = true;

  if (isDelivered) {
    resolve("음식이 배달되었어요!");
  } else {
    reject("배달에 실패했어요...");
  }
});

orderFood
  .then((message) => {
    console.log(message);
    console.log("맛있게 먹어요!");
  })
  .catch((error) => {
    console.log(error);
  });
```

### 4.async/await

- Promise 기반 코드를 더 직관적으로 작성할 수 있게 해주는 기능입니다.
- async 키워드는 함수 앞에 붙여서 그 함수를 비동기 함수로 만들며 await 키워드는 Promise가 해결될 때까지 기다린 후 그 값을 반환합니다.
  - async 함수 내부에서 await를 사용하여 동기처럼 비동기 처리 가능

```javascript
function deliverFood() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("음식이 배달되었어요!");
    }, 3000);
  });
}

async function orderAndEat() {
  console.log("음식을 주문했어요...");
  const message = await deliverFood(); // 배달이 올 때까지 기다림
  console.log(message);
  console.log("이제 음식을 먹어요!");
}

orderAndEat();
```
