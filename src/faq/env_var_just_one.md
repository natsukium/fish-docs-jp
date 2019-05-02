## 一回限りの環境変数を設定するには？

`SOME_VAR=1 command`というコマンドは次のエラーを引き起こします.
`Unknown command "SOME_VAR=1"`

このようなときには`env`コマンドを使ってください.

`env SOME_VAR=1 command`

ブロック中で次のようにローカル変数を宣言することもできます.

```fish
begin
    set -lx SOME_VAR 1
    command
end
```
