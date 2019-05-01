## パイプとリダイレクト

`|`を用いることでコマンドをパイプすることができます.

```fish
>_ echo hello world | wc
       1       2      12
```

stdinとstdoutは馴染み深い`<`と`>`によってリダイレクトすることができます.
stderrは`2>`によってリダイレクトされます.

```fish
>_ grep fish < /etc/shells > ~/output.txt 2> ~/errors.txt
```
