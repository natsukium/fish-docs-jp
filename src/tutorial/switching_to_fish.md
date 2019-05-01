## fishをデフォルトシェルにする

`fish`(或いはその他のシェル)をデフォルトシェルとして使いたい場合,
fishの実行ファイル`/usr/local/bin/fish`を`/etc/shells`にも置く必要があります.
それから`chsh -s /usr/local/bin/fish`でデフォルトシェルに変更することができます.

具体的には次のコマンドに従ってください.

fishを`/etc/shells`に追加する.
```sh
> echo /usr/local/bin/fish | sudo tee -a /etc/shells
```

デフォルトシェルをfishに変える.
```sh
> chsh -s /usr/local/bin/fish
```

(他のシェルに戻すには上記コマンドの引数`/usr/local/bin/fish`を`/bin/bash`, `/bin/tcsh`や`/bin/zsh`に置き換えてください.)

