## 起動に際して(.bashrc)

`fish`は`~/.config/fish/config.fish`に書かれたコマンドを起動時に実行します.
もしこのファイルがなかったら新たに作ることができます.

次のようなコマンドを用いる事で`config.fish`に直接関数や変数を定義することができます.

```fish
>_ cat ~/.config/fish/config.fish

set -x PATH $PATH /sbin/

function ll
    ls -lh $argv
end
```

しかし, オートロード関数やユニバーサル変数を使うのが一般的で効果的です.
