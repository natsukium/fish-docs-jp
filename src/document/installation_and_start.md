## インストールと始め方

このセクションではインストール, アンインストール, 起動, 終了のしかたと`fish`をデフォルトシェルにする方法を説明します.

- [インストール](#Installation):
`fish`のインストール方法

- [デフォルトシェル](#Default_Shell):
`fish`をデフォルトシェルにする方法

- [起動と終了](#Starting_and_Exiting):
`fish`の起動方法と終了方法

- [アンインストール](#Uninstalling):
`fish`のアンインストール方法

- [Bashの実行](#Executing_Bash):
`fish`上で`bash`コマンドを実行する方法

<a id="Installation"></a>
### インストール

`fish`のインストール方法は[fishホームページ](https://fishshell.com/)をみてください.
このページで"Go fish"を検索すると良いでしょう.

`fish`の開発バージョンをインストールするには, [プロジェクトのGitHubページ](https://github.com/fish-shell/fish-shell)
をみてください.

<a id="Default_Shell"></a>
### デフォルトシェル

`fish`をデフォルトシェルにするには`fish`の実行ファイルを次の2箇所に配置する必要があります.
`/usr/local/bin/fish`及び`/etc/shells`です.
デフォルトシェルにするには`chsh -s`コマンドに`/usr/local/bin/fish`を引数として渡してください.

詳しくは[fishをデフォルトシェルにする](../tutorial/switching_to_fish.md)を参照ください.

<a id="Uninstalling"></a>
### アンインストール

`fish`をアンインストールするには[FAQ: fishをアンインストールする]を参照してください.

<a id="Starting_and_Exiting"></a>
### 起動と終了

一度`fish`をインストールしてしまえば, ターミナルを開くだけで起動します.
もし`fish`がデフォルトシェルでないなら, 次のようになります.

- `fish`を起動するために`fish`コマンドを実行する.

```fish
> fish
```

- `fish`から抜けるために`exit`コマンドを実行する.

```fish
> exit
```

<a id="Executing_Bash"></a>
### Bashの実行

`fish`がデフォルトシェルで, インターネットで拾った`bash`のような異なるシェルで書かれたコマンドを実行したいとき,
次のようにして実行することができます.

`bash`もまたコマンドです. `man bash`でmanページを開くと2つの方法で実行できることがわかるでしょう.

- `bash`は文字列からコマンドを読み込む`-c`オプションを持っている.

```fish
> bash -c SomeBashCommand
```

或いは`bash`を引数なしで起動して, コマンドを実行したのちに`exit`で抜けるということもできます.
