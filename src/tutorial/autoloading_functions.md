## オートロード関数

`fish`がコマンドを認識したとき, `~/.config/fish/functions/`からそのコマンドを探し,
オートロード関数として呼び出そうとします.

例えば`ll`という関数が欲しければ, `ll.fish`というテキストファイルを`~/.config/fish/functions/`に追加します.

```fish
>_ cat ~/.config/fish/functions/ll.fish
function ll
    ls -lh $argv
end
```

同様に独自プロンプトを次のように定義するのがより良い方法です.

```fish
>_ cat ~/.config/fish/functions/fish_prompt.fish
function fish_prompt
    echo (pwd) "> "
end
```

こうしたファイルを自動的に作る方法として[funced], [funcsave]を参考にしてください.
