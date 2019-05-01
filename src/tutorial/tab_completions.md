## タブ補完

`fish`はすぐに使えるリッチなタブ補完を備えています.
`tab`を押してみると, `fish`はコマンドや引数, パスを補完しようとするでしょう.

```fish
>_ <eror>/pri</eror> :kbd:`Tab` => /private
```

複数の候補が見つかれば, それらをリストとして表示します.

```fish
>_ <eror>~/stuff/s</eror> :kbd:`Tab`
<mtch>~/stuff/script.sh  <i>(Executable, 4.8kB)</i>  \mtch{~/stuff/s</mtch>ources/  <i>(Directory)</i>}
```

`tab`を押すたびにその候補を順にフォーカスします.

`fish`はgitのブランチのようなものまでも補完することができます.

```fish
>_ git merge pr :kbd:`Tab` => git merge prompt_designer
>_ git checkout b :kbd:`Tab`
<mtch>builtin_list_io_merge <i>(Branch)</i> \mtch{b</mtch>uiltin_set_color <i>(Branch)</i> <mtch>b</mtch>usted_events <i>(Tag)</i>}
```

実際に`tab`を押して確認してみましょう！
