## エクスポート(シェル変数)

他のシェルと違って, `fish`は`export`コマンドをサポートしていません.
代わりに`set`コマンドの`--export`或いは`-x`オプションによって変数をエクスポートします.

```fish
>_ set -x MyVariable SomeValue
>_ env | grep MyVariable
MyVariable=SomeValue
```

変数は`-e`若しくは`--erase`オプションによって削除することができます.

```fish
>_ set -e MyVariable
>_ env | grep MyVariable
(no output)
```
