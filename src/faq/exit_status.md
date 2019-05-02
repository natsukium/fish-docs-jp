## コマンドの終了ステータスを得るには？

`$status`変数を使ってください.
これは他のシェルで使われている`$?`変数を置き換えるものです.

```fish
somecommand
if test $status -eq 7
    echo "That's my lucky number!"
end
```

もし単に成功か失敗かを知りたいだけなら, `if`のような条件構文に直接渡してください.

```fish
if somecommand
    echo "Command succeeded"
else
    echo "Command failed"
end
```

より詳しくは[test]コマンドや[if]コマンドを参照してください.
