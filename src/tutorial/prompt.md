## プロンプト

他のシェルと違って, PS1のようなプロンプト変数はありません.
プロンプトを表示するために, `fish`は`fish_prompt`という名前の関数を実行し,
その出力がプロンプトとして用いられます.

次のように独自のプロンプトを定義することができます.

```fish
>_ function fish_prompt
     echo "New Prompt % "
   end
New Prompt %
```

複数行のプロンプトも可能です.
色は`set_color`コマンドにANSI colorsか16進数のRGB値を渡すことによって設定できます.

```fish
>_ function fish_prompt
     set_color purple
     date "+%m/%d/%y"
     set_color FF0
     echo (pwd) '>'
     set_color normal
   end
<span style="color: purple">02/06/13</span>
<span style="color: #FF0">/home/tutorial ></span>___
```

`fish_config_prompt`関数を実行することでサンプルの中からプロンプトを選ぶことができます.
また, `fish`は`fish_right_prompt`関数によって右プロンプトもサポートしています.
