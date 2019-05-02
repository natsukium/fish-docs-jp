## 独自のプロンプトを設定するには？

プロンプトは`fish_prompt`関数の出力になります.
この関数は`~/.config/fish/functions/fish_prompt.fish`に配置してください.
簡単な例を下に示します.

```fish
function fish_prompt
    set_color $fish_color_cwd
    echo -n (prompt_pwd)
    set_color normal
    echo -n ' > '
end
```

Web上の設定ツール, [fish_config]を使うこともできます.
プロンプトのサンプルから選んで試すことができます.
