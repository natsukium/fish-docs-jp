## 関数

`fish`の関数はコマンドのリストであり, オプションとして引数をとることができます.
他のシェルと違って, 引数は`$1`のような"数字変数"ではなく,`$argv`という一つのリストとして渡されます.
関数を作るためにビルトインの`function`コマンドを用います.

```fish
>_ function say_hello
     echo Hello $argv
   end
>_ say_hello
Hello
>_ say_hello everybody!
Hello everybody!
```

他のシェルと違って, `fish`はエイリアスや特殊なプロンプト構文を持ちません.
これらも関数で表現します.

`functions`キーワードによって全ての関数名を列挙することができます.
(複数形であることに注意！)
`fish`にははじめから数多くの関数が定義されています.

```fish
>_ functions
alias, cd, delete-or-exit, dirh, dirs, down-or-search, eval, export, fish_command_not_found_setup, fish_config, fish_default_key_bindings, fish_prompt, fish_right_prompt, fish_sigtrap_handler, fish_update_completions, funced, funcsave, grep, help, history, isatty, ls, man, math, nextd, nextd-or-forward-word, open, popd, prevd, prevd-or-backward-word, prompt_pwd, psub, pushd, seq, setenv, trap, type, umask, up-or-search, vared
```

`functions`に関数名を渡すことでその関数の中身をみることもできます.

```fish
>_ functions ls
function ls --description 'List contents of directory'
    command ls -G $argv
end
```
