<!--
Meta Description: # Go 언어의 break 명령어: 루프 제어의 완벽한 가이드 ## 개요 Go 언어에서 `break` 명령어는 반복문(루프)이나 switch 문을 종료하는 데 사용됩니다. 이 명령어는 프로그램의 흐름을 제어하여 특정 조건이 충족될 때 루프를 조기에 종료할 수 있도록 합...
Meta Keywords: break, switch, 명령어는, main, fmt
-->

# Go 언어의 break 명령어: 루프 제어의 완벽한 가이드

## 개요
Go 언어에서 `break` 명령어는 반복문(루프)이나 switch 문을 종료하는 데 사용됩니다. 이 명령어는 프로그램의 흐름을 제어하여 특정 조건이 충족될 때 루프를 조기에 종료할 수 있도록 합니다.

## 문서화
`break`는 Go 언어에서 반복문이나 switch 문을 즉시 종료하는 기능을 제공합니다. 이 명령어는 주로 다음과 같은 상황에서 사용됩니다:

- **목적**: 루프나 switch 문을 조기에 종료하여 더 이상의 반복이나 평가를 방지합니다. 
- **사용법**: `break` 명령어는 단순히 `break` 키워드 뒤에 아무런 조건이나 인자를 필요로 하지 않으며, 해당 명령어가 포함된 블록이 종료됩니다.

### 사용 예시
다음은 Go에서 `break`를 사용하는 기본적인 예제입니다:

```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i == 5 {
            break // i가 5일 때 루프 종료
        }
        fmt.Println(i)
    }
}
```

이 예제에서 `i`가 5일 때 `break` 명령어가 실행되어 루프가 종료되고, 출력은 0부터 4까지의 숫자만 표시됩니다.

## 설명
`break`를 사용할 때 주의해야 할 몇 가지 점이 있습니다:

- **중첩 루프에서의 사용**: `break`는 가장 가까운 루프만 종료합니다. 만약 중첩된 루프에서 바깥쪽 루프를 종료하고 싶다면 `break`에 레이블을 사용할 수 있습니다.
  
```go
package main

import "fmt"

func main() {
    outerLoop:
    for i := 0; i < 3; i++ {
        for j := 0; j < 3; j++ {
            if i == 1 && j == 1 {
                break outerLoop // 바깥쪽 루프 종료
            }
            fmt.Println(i, j)
        }
    }
}
```

- **switch 문에서의 사용**: `break`는 switch 문에서도 사용되며, 해당 switch의 실행을 종료합니다. 하지만 Go의 switch 문은 기본적으로 각 case 문 뒤에 `break`가 내장되어 있어 명시적으로 `break`를 사용할 필요는 없습니다.

## 한 줄 요약
Go 언어의 `break` 명령어는 루프나 switch 문의 실행을 종료하는 데 사용되는 간단하고 유용한 제어 구조입니다.