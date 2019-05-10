## 変数が空でないか確認するには？

`string length -q -- $var`を使ってください.
例えば`if string length -q -- $var; echo not empty; end`のように使います.

`string length`は複数の引数のリストを個別にチェックし, 1つでも空でなければ0を返します.

```fish
if string length -q -- $var1 $var2 $var3
    echo at least one of these variables is not empty
end
```

代わりに`test -n "$var"`を使ってください.
ただしダブルクオートで変数を括ることを忘れないでください.
例えば`if test -n "$var"; echo not empty; end`のように使います.
`test`コマンドはオプションとして`-a`(and)と`-o`(or)を持ちます.

```fish
if test -n "$var1" -o -n "$var2" -o -n "$var3"
    echo at least one of these variables is not empty
end
```
