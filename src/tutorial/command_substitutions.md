## コマンド置換

コマンド置換は1つのコマンドの実行結果を他のコマンドの引数として渡す際に使われます.
他のシェルと違って, `fish`は` `` `ではなく`()`を用います.

```fish
>_ echo In (pwd), running (uname)
In /home/tutorial, running FreeBSD
```

コマンドの結果を変数に代入するときによく使われます.

```fish
>_ set os (uname)
>_ echo $os
Linux
```

コマンド置換はクオートによって展開されません.
その代わり一度クオートを閉じ, コマンド置換を行いそれから再びクオートを開くことによって実現できます.

```fish
>_ touch "testing_"(date +%s)".txt"
>_ ls *.txt
testing_1360099791.txt
```

他のシェルと違って, `fish`は(スペースやタブのような)いかなる空白文字であっても
分割されることはなく, 改行によってのみ分割されます.
これは`pkg-config`のような複数の引数を1行に出力するコマンドを使う際に問題となります.
スペースでも分割できるようにするためには`string split`を用いてください.

```fish
>_ printf '%s\n' (pkg-config --libs gio-2.0)
-lgio-2.0 -lgobject-2.0 -lglib-2.0
>_ printf '%s\n' (pkg-config --libs gio-2.0 | string split " ")
-lgio-2.0
-lgobject-2.0
-lglib-2.0
```
