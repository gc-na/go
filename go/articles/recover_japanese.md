<!--
Meta Description: # Go言語の「recover」: パニックからの回復方法 ## 概要 Go言語の「recover」は、パニック状態から回復するための関数です。この機能を使用することで、プログラムが予期しないエラーによって終了するのを防ぎ、エラー処理を行うことができます。 ## ドキュメンテーション ### 目的 ...
Meta Keywords: recover, defer, func, fmt, panic
-->

# Go言語の「recover」: パニックからの回復方法

## 概要
Go言語の「recover」は、パニック状態から回復するための関数です。この機能を使用することで、プログラムが予期しないエラーによって終了するのを防ぎ、エラー処理を行うことができます。

## ドキュメンテーション
### 目的
「recover」は、パニック（panic）によって引き起こされるプログラムのクラッシュを防ぎ、エラーハンドリングを可能にします。主に、`defer`文と組み合わせて使用され、パニックが発生した際にその状態を捕捉するために利用されます。

### 使用方法
「recover」を使用するには、まず`defer`ステートメントを使用して関数を遅延実行し、その中で「recover」を呼び出します。以下のコードは基本的な使用方法を示しています。

```go
package main

import (
    "fmt"
)

func safeFunction() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered from:", r)
        }
    }()
    
    // パニックを引き起こす
    panic("Something went wrong!")
}

func main() {
    safeFunction()
    fmt.Println("Program continues...")
}
```

## 例
### 基本的な使用例
上記の例では、`safeFunction`内で`panic`が発生した場合でも、`recover`によってプログラムがクラッシュすることなくエラーメッセージを表示し、正常に続行されます。

### 複数のリカバリー
複数の`defer`文を持つ関数でも、最初に呼び出された`defer`内の`recover`が優先されます。

```go
package main

import (
    "fmt"
)

func first() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered in first:", r)
        }
    }()
    panic("Panic in first")
}

func second() {
    defer func() {
        if r := recover(); r != nil {
            fmt.Println("Recovered in second:", r)
        }
    }()
    first() // この呼び出しでパニックが発生する
}

func main() {
    second()
    fmt.Println("Program continues...")
}
```

## 説明
### 一般的な落とし穴
- `recover`は、`defer`内でのみ機能します。直接呼び出すと効果がありません。
- パニックが発生した後に`recover`を呼び出さないと、プログラムは終了します。
- `recover`を使用しても、すべてのエラーを捕捉できるわけではありません。パニックの原因を理解し、適切に処理することが重要です。

### 注意点
- `recover`は、通常のエラーハンドリングの代わりにはなりません。エラーを管理するためには、適切なエラーチェックを行うことが推奨されます。
- `recover`は、パフォーマンスに影響を与える可能性があるため、必要に応じて使用することが望ましいです。

## 一行要約
Go言語の「recover」は、パニックから回復し、プログラムのクラッシュを防ぐための機能です。