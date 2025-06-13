## 예외 처리 (Exception Handling)란?

예외 처리는 프로그램 실행 중 에러가 발생할 수 있는 상황을 안전하게 처리하여, 프로그램이 멈추지 않고 안정적으로 작동하도록 돕는 방법입니다.

**예외 처리가 없으면, 오류 발생 시 프로그램이 강제 종료될 수 있습니다.**

### 예외 처리의 주요 키워드

| 키워드    | 설명                                                                                                        |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| `try`     | 오류가 발생할 수 있는 코드를 감쌉니다.                                                                      |
| `catch`   | 오류가 발생했을 때 실행되는 코드 블록입니다.                                                                |
| `finally` | 오류 발생 여부와 관계없이 **항상 실행**되는 코드입니다. 주로 **자원 정리**나 **로그 기록** 등에 사용됩니다. |

- 예제코드

```js
function divideNumbers() {
  try {
    let number = 10;
    let zero = 0;

    if (zero === 0) {
      throw new Error("0으로는 나눌 수 없습니다!");
    }

    let result = number / zero;
    console.log("결과:", result);
  } catch (e) {
    console.log("문제가 생겼어요:", e.message);
  } finally {
    console.log("프로그램이 끝났어요.");
  }
}

divideNumbers();
```

- `try`: 0으로 나누기 전에 조건을 확인하고 직접 오류를 발생시킴
- `catch`: 발생한 오류를 잡고 메시지를 출력
- `finally`: 오류 발생과 관계없이 항상 실행

### REST API를 사용한 데이터 전송 예외 처리

#### 프론트엔드

```js
async function sendData() {
  const data = {
    name: "Alice",
    age: 25,
  };

  try {
    const response = await fetch("http://localhost:8080/api/users", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(data),
    });

    if (!response.ok) {
      throw new Error(`서버 오류: ${response.status}`);
    }

    const result = await response.json();
    console.log("서버 응답:", result);
  } catch (error) {
    console.error("데이터 전송 중 문제가 발생했습니다:", error.message);
  } finally {
    console.log("데이터 전송 작업이 완료되었습니다.");
  }
}

sendData();
```

- `try`: 서버에 데이터를 보내고 응답을 기다립니다.

- `catch`: 네트워크 오류나 서버 오류 발생 시 예외 처리합니다.

- `finally`: 작업 완료 여부와 상관없이 완료 메시지 출력 합니다.

#### 백엔드

```java
@RestController
@RequestMapping("/api")
public class UserController {

  @PostMapping("/users")
  public ResponseEntity<String> createUser(@RequestBody User user) {
    System.out.println("받은 데이터: " + user.getName() + ", 나이: " + user.getAge());
    return ResponseEntity.ok("데이터가 성공적으로 전송되었습니다.");
  }
}

class User {
  private String name;
  private int age;

  public String getName() { return name; }
  public void setName(String name) { this.name = name; }

  public int getAge() { return age; }
  public void setAge(int age) { this.age = age; }
}

```

| 구분           | 설명                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------- |
| **프론트엔드** | `fetch`와 `try-catch-finally`를 사용하여 서버에 안전하게 데이터 전송 및 예외 처리           |
| **백엔드**     | Spring Boot를 예시로 설명을 하면 `@PostMapping`으로 데이터를 받고, 처리 후 성공 메시지 반환 |
