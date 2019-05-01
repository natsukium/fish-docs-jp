## 変数

他のシェルと同じように, `$`によって変数を扱います.

```fish
>_ echo My home directory is $HOME
My home directory is /home/tutorial
```

変数はダブルクオートのなかでは置換されますが, シングルクオートの中では置換されません.

```fish
>_ echo "My current directory is $PWD"
My current directory is /home/tutorial
>_ echo 'My current directory is $PWD'
My current directory is $PWD
```

他のシェルと違って, `fish`は変数を代入する構文を持ちません.
代わりに変数名とその値を引数にとる, `set`コマンドを持ちます.

```fish
>_ set name 'Mister Noodle'
>_ echo $name
Mister Noodle
```

(クオートに注意してください. もしこれがなければ`Mister`と`Noodle`は別々の引数として認識され, `$name`は2つの要素を持つリストになります.)

他のシェルと違って, 変数は置換後に分割されることはありません.

```fish
>_ mkdir $name
>_ ls
Mister Noodle
```

bashでは上記コマンドで"Mister"と"Noodle"という2つのディレクトリが作られます.
`fish`では"Mister Noodle"という値を持った変数によって1つのディレクトリが作られます.
つまり`mkdir`にはスペースを含んだ文字列の引数として渡されます.
他のシェルではリストという表現ではなく"配列"という用語が用いられます.
