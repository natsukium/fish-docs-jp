## コマンドの実行

`fish`は他のシェルと同じように, コマンドに続けて引数を与えることで実行します.
スペースはセパレータとなっています.

```fish
>_ echo hello world
hello world
```

空白文字として引数を与えたい場合, バックスラッシュを前置するか或いはシングルクオート,
ダブルクオートで囲むことによって実現します.

```fish
>_ mkdir My\ Files
>_ cp ~/Some\ File 'My Files'
>_ ls "My Files"
Some File
```

コマンドはセミコロンを用いることによって繋げることができます.
