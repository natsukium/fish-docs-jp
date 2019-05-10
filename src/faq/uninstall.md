## アンインストールするには？

万が一fishをアンインストールしたくなった場合, まずデフォルトシェルに設定されていないことを確認してください.
もしそうであれば`chsh -s /bin/bash`で変更してください.

次に以下の操作をしてください.
(/usr/localにfishがインストールされていると想定しています.)

```sh
rm -Rf /usr/local/etc/fish /usr/local/share/fish ~/.config/fish
rm /usr/local/share/man/man1/fish*.1
cd /usr/local/bin
rm -f fish fish_indent
```
