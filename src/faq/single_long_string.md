## pkg-configのような出力が1行の長い文字列のときどうしたらいい？

他のシェルと違って, `fish`は改行時のみ置換されたコマンドを分割します.
スペースやタブ, $IFSに含まれる文字では分割されません.

これは次のことを意味します.

```fish
echo x(printf '%s ' a b c)x
```

を実行すると`xa b c x`が出力されます.
しかし次の場合,

```fish
echo x(printf '%s\n' a b c)x
```

`xax xbx xcx`が出力されます.

ほぼ全てのケースにおいてスペース区切りは望ましくないので, この仕様は改善点であるといえます.

しかしながら, `pkg-config`やその周辺ツールなどではスペース区切りが必要となっています.
このような場合, `string split " "`を使ってください.

```fish
g++ example_01.cpp (pkg-config --cflags --libs gtk+-2.0 | string split " ")
```
