## 変数が定義されるているか確認するには？

`set -q var`コマンドを使ってください.

例えば`if set -q --$var; echo variable defined; end`のように使います;

複数の変数を確認するには'`and`や`or`の演算子を使ってください.

```fish
if set -q var1; or set -q var2
    echo either variable defined
end
```

定義済みの変数は空である可能性もあることに注意してください.
次の2つのコマンドで空の変数を定義できます.
`set var` `set var ""`
