## コンバイナ(and, or, not)

`fish`は馴染みのある`&&`と`||`, それから否定の`!`をサポートしています.

```fish
>_ ./configure && make && sudo make install
```

さらに`fish`は`and`, `or`と`not`も同様にサポートしています.
最初の2つはコマンドの修飾子で, 優先順位は低くなっています.
以下に例を挙げます.

```fish
>_ cp file1.txt file1_bak.txt && cp file2.txt file2_bak.txt ; and echo "Backup successful"; or echo "Backup failed"
Backup failed
```
[セパレートコマンド(;)](./separating_commands.md)の項で触れたように複数行にわたって
書くこともできます.

```fish
cp file1.txt file1_bak.txt && cp file2.txt file2_bak.txt
and echo "Backup successful"
or echo "Backup failed"
```
