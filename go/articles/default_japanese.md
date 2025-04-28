<!--
Meta Description: # Go言語における「default」：使用方法と注意点 ## 概要 Go言語における「default」は、`switch`文や`select`文において、他のケースにマッチしない場合に実行されるデフォルトの処理を指定するために使用されるキーワードです。この機能を利用することで、プログラムの流れをよ...
Meta Keywords: default, select, switch, case, fmt
-->

# Go言語における「default」：使用方法と注意点

## 概要
Go言語における「default」は、`switch`文や`select`文において、他のケースにマッチしない場合に実行されるデフォルトの処理を指定するために使用されるキーワードです。この機能を利用することで、プログラムの流れをより柔軟に制御することができます。

## ドキュメンテーション
### 目的
Go言語の`switch`文や`select`文における`default`は、特定の条件にマッチしない場合に実行されるコードブロックを定義します。これにより、プログラムの流れが明確になり、予期しない条件に対する処理を簡潔に記述できます。

### 使用方法
`default`は`switch`文または`select`文の最後に配置します。以下は、`switch`文における基本的な構文です。

```go
switch 式 {
case 値1:
    // 値1の場合の処理
case 値2:
    // 値2の場合の処理
default:
    // どのcaseにもマッチしなかった場合の処理
}
```

`select`文における`default`の使用方法は次の通りです：

```go
select {
case チャネル1:
    // チャネル1からの受信処理
case チャネル2:
    // チャネル2からの受信処理
default:
    // どのチャネルにもマッチしなかった場合の処理
}
```

## 例
### `switch`文の例
```go
package main

import "fmt"

func main() {
    day := 3
    switch day {
    case 1:
        fmt.Println("月曜日")
    case 2:
        fmt.Println("火曜日")
    case 3:
        fmt.Println("水曜日")
    default:
        fmt.Println("週末")
    }
}
```

この例では、`day`の値に応じて、対応する曜日が出力され、3の場合は「水曜日」が表示されます。

### `select`文の例
```go
package main

import (
    "fmt"
    "time"
)

func main() {
    ch1 := make(chan string)
    ch2 := make(chan string)

    go func() {
        time.Sleep(1 * time.Second)
        ch1 <- "チャネル1からのメッセージ"
    }()

    go func() {
        time.Sleep(2 * time.Second)
        ch2 <- "チャネル2からのメッセージ"
    }()

    select {
    case msg1 := <-ch1:
        fmt.Println(msg1)
    case msg2 := <-ch2:
        fmt.Println(msg2)
    default:
        fmt.Println("どちらのチャネルも準備ができていません")
    }
}
```

この例では、どちらのチャネルも準備ができていない場合、`default`ブロックが実行されます。

## 説明
`default`を使用する際の注意点は、必ずしもすべての`switch`または`select`文に必要なわけではないことです。場合によっては、`default`を省略することで、特定の条件が満たされない場合にエラーを発生させることができます。また、`default`は1つの`switch`または`select`文に対して1回だけ使用できます。

### 一般的な落とし穴
- `default`ブロックは、他のcaseがすべてマッチしなかった場合のみ実行されるため、意図しない動作を引き起こすことがあります。
- `select`文の`default`が存在する場合、他のcaseが非同期で準備できている場合でも、`default`が優先されるため、注意が必要です。

## 一文の要約
Go言語における「default」は、`switch`や`select`文で、条件にマッチしない場合の処理を定義するための重要なキーワードです。