## PATH変数

`$PATH`は環境変数で, `fish`がコマンドを探索するディレクトリを保持しています.
他のシェルと違って, `$PATH`は[リスト](./lists.md)であり, コロンで区切られた文字列ではありません.

`/usr/local/bin`と`/usr/sbin`を`$PATH`に追加するためには次のように書きます.

```fish
>_ set PATH /usr/local/bin /usr/sbin $PATH
```

`$PATH`から`/usr/local/bin`を削除するには次のようにします.

```fish
>_ set PATH (string match -v /usr/local/bin $PATH)
```

また, 他のシェルの`.profile`のように`config.fish`を直接編集しても構いません.

より早い方法として`$fish_user_paths`という[ユニバーサル変数]を設定すると良いでしょう.
これは自動的に`$PATH`に追加されます.
例えば,　`$PATH`に永続的に`/usr/local/bin`を追加したい場合, 次のようにしてください.

```fish
>_ set -U fish_user_paths /usr/local/bin $fish_user_paths
```

この方法の利点は設定ファイルを汚さなくてよいところです.
一度コマンドラインで実行さえすれば現在のセッションから永久的にパスが有効になります.
(注意: これを`config.fish`に書き加えないでください.
もしそうした場合, fishを起動するたびに変数に追加されて長くなっていってしまいます！)
