## 条件式(if, else, switch)

`if`, `else if`それから`else`を使うことでコマンドの終了ステータスによって
実行するコードを条件分岐することができます.

```fish
if grep fish /etc/shells
    echo Found fish
else if grep bash /etc/shells
    echo Found bash
else
    echo Got nothing
end
```

文字列や数字の比較, ファイルのプロパティ(ファイルが存在するか, 書き込み可能かなど)を確認する場合には次のように[`test`コマンド]を利用してください.

```fish
if test "$fish" = "flounder"
    echo FLOUNDER
end

# or

if test "$number" -gt 5
    echo $number is greater than five
else
    echo $number is five or less
end
```

[コンバイナ](./combiners.md)を使うことでさらに複雑な条件式がかけるようになります.

```fish
if grep fish /etc/shells; and command -sq fish
    echo fish is installed and configured
end
```

もっと複雑になったときには`begin`と`end`を使ってグループ化してください.

また, `switch`コマンドもあります.

```fish
switch (uname)
case Linux
    echo Hi Tux!
case Darwin
    echo Hi Hexley!
case FreeBSD NetBSD DragonFly
    echo Hi Beastie!
case '*'
    echo Hi, stranger!
end
```

`case`はフォールスルーせず, さらに複数の引数やクオートで囲まれたワイルドカードを受け付けることに注意してください.
