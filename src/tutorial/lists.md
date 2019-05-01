## リスト

先に見た`set`コマンドはクオートで囲むことによって`Mister Noodle`を1つの引数として扱いました.
もし2つの引数だったなら, 変数`name`は長さ2のリストになります.
実際, `fish`の全ての変数はリストであり, いくつでも値を保持できるし全く持たないことも可能です.

`$PWD`のようないくつかの変数は1つしか値を持ちません.
慣習に従って変数の値というとき, 最初(かつただ1つ)の値を指すことにします.

`$PATH`のようなその他の変数は複数の値を保持しています.
これらの変数は複数の引数として展開されます.

```fish
>_ echo $PATH
/usr/bin /bin /usr/sbin /sbin /usr/local/bin
```

"PATH"で終わる変数は自動的にコロンで分割されてリストになります.
これらはサブコマンドに渡されるときにコロンによって結合されます.
この仕様は`$PATH`はコロンで区切られていると想定している他のツールとの互換性のためにあります.
明示的にパスを変数に加えるには`set --path`, 削除するには`set --unpath`を用いることができます.

リストは要素として他のリストを保持することはできず, 再帰的ではありません.
変数は文字列のリストであり, 他にはありえません

リストの要素数を得るには`count`コマンドを使います.

```fish
>_ count $PATH
5
```

リスト自身に追加の引数をセットすることで, 要素を追加することができます.
`$PATH`に`/usr/local/bin`を追加する例を示します.

```fish
>_ set PATH $PATH /usr/local/bin
```

`[]`を用いることで個別の要素にアクセスすることができます.
インデックスは1から始まり, 最後は-1です.

```fish
>_ echo $PATH
/usr/bin /bin /usr/sbin /sbin /usr/local/bin
>_ echo $PATH[1]
/usr/bin
>_ echo $PATH[-1]
/usr/local/bin
```

"スライス"を用いてある範囲の要素にアクセスすることもできます.

```fish
>_ echo $PATH[1..2]
/usr/bin /bin
>_ echo $PATH[-1..2]
/usr/local/bin /sbin /usr/sbin /bin
```

forループを用いてリスト全体(或いはスライス)に繰り返しアクセスすることもできます.

```fish
>_ for val in $PATH
     echo "entry: $val"
   end
entry: /usr/bin/
entry: /bin
entry: /usr/sbin
entry: /sbin
entry: /usr/local/bin
```

他のリストや文字列と隣り合ったリストは, クオートで囲まなければ直積となります.
([直積], [変数展開] 参照)

```fish
>_ set a 1 2 3
>_ set 1 a b c
>_ echo $a$1
1a 2a 3a 1b 2b 3b 1c 2c 3c
>_ echo $a" banana"
1 banana 2 banana 3 banana
>_ echo "$a banana"
1 2 3 banana
```

これは[ブレース展開]と似た作用です.
