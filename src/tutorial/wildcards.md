## ワイルドカード

`fish`はワイルドカードの`*`をサポートしています.
全てのJPEGファイルをリストアップするには次のようにします.

```fish
>_ ls *.jpg
lena.jpg
meena.jpg
santa maria.jpg
```

複数のワイルドカードを用いることもできます.

```fish
>_ ls l*.p*
lena.png
lesson.pdf
```

特に強力なのはディレクトリを再帰的に探索する`**`です.

```fish
>_ ls /var/**.log
/var/log/system.log
/var/run/sntp.log
```

ディレクトリの探査に時間がかかるときは`Ctrl-c`で中止することができます.
