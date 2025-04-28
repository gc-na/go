<!--
Meta Description: # Go의 switch 문: 조건 분기 처리의 효율적인 방법 ## 개요 Go 언어의 `switch` 문은 여러 조건을 간단하고 명확하게 처리할 수 있는 강력한 제어 구조입니다. 복잡한 조건문을 간결하게 작성할 수 있어 가독성이 높아지는 장점이 있습니다. ## 문서화 `...
Meta Keywords: case, fmt, switch, println, main
-->

# Go의 switch 문: 조건 분기 처리의 효율적인 방법

## 개요
Go 언어의 `switch` 문은 여러 조건을 간단하고 명확하게 처리할 수 있는 강력한 제어 구조입니다. 복잡한 조건문을 간결하게 작성할 수 있어 가독성이 높아지는 장점이 있습니다.

## 문서화
`switch` 문은 특정 변수의 여러 값에 따라 실행할 코드를 선택하는 데 사용됩니다. 기본적인 문법은 다음과 같습니다:

```go
switch 변수 {
case 값1:
    // 값1인 경우 실행
case 값2:
    // 값2인 경우 실행
default:
    // 어떤 경우에도 해당되지 않을 때 실행
}
```

### 목적
`switch` 문은 여러 조건을 평가하고 그에 따라 하나의 코드 블록을 실행하는 데 유용합니다. 이는 `if-else` 구문보다 더 깔끔하고 읽기 쉬운 코드를 작성할 수 있게 해줍니다.

### 사용법
`switch` 문은 다음과 같이 사용됩니다:

1. **기본 `switch`**: 특정 변수의 값을 비교합니다.
2. **빈 `switch`**: 조건을 명시하지 않고, `true`로 평가되는 첫 번째 `case` 문을 실행합니다.
3. **다중 조건**: 하나의 `case` 문에 여러 조건을 사용할 수 있습니다.
4. **fallthrough**: `case` 문이 실행된 후 다음 `case` 문으로 넘어가도록 할 수 있습니다.

## 예시
### 기본 사용 예
```go
package main

import (
    "fmt"
)

func main() {
    day := 3
    switch day {
    case 1:
        fmt.Println("월요일")
    case 2:
        fmt.Println("화요일")
    case 3:
        fmt.Println("수요일")
    default:
        fmt.Println("주말입니다.")
    }
}
```

### 빈 switch 예
```go
package main

import (
    "fmt"
)

func main() {
    number := 2
    switch {
    case number < 0:
        fmt.Println("음수")
    case number == 0:
        fmt.Println("제로")
    case number > 0:
        fmt.Println("양수")
    }
}
```

### 다중 조건 예
```go
package main

import (
    "fmt"
)

func main() {
    grade := 'A'
    switch grade {
    case 'A', 'B':
        fmt.Println("합격")
    case 'C':
        fmt.Println("재시험")
    default:
        fmt.Println("불합격")
    }
}
```

### fallthrough 예
```go
package main

import (
    "fmt"
)

func main() {
    score := 85
    switch {
    case score >= 90:
        fmt.Println("A")
    case score >= 80:
        fmt.Println("B")
        fallthrough
    case score >= 70:
        fmt.Println("C")
    default:
        fmt.Println("F")
    }
}
```

## 설명
`switch` 문을 사용할 때 주의할 점은 다음과 같습니다:

- **fallthrough**: 기본적으로 `case` 문이 실행된 후 다음 `case` 문이 자동으로 실행되지 않습니다. `fallthrough` 키워드를 사용해야 합니다.
- **중복 case**: 동일한 값이 여러 `case`에 있을 경우, 가장 먼저 매칭되는 `case`가 실행됩니다.
- **빈 switch**: 조건을 지정하지 않으면 항상 `true`로 평가되어 첫 번째 `case`가 실행됩니다.

## 요약
Go의 `switch` 문은 조건 분기를 간결하고 효율적으로 처리할 수 있는 유용한 도구입니다.