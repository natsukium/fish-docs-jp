## ループ

Whileループは次のように使えます.

```fish
>_ while true
     echo "Loop forever"
end
Loop forever
Loop forever
Loop forever
...
```

Forループはリスト全体を処理することができます.

```fish
>_ for file in *.txt
     cp $file $file.bak
   end
```

`seq`コマンドを用いることで数列でループすることができます.

```fish
>_ for x in (seq 5)
     touch file_$x.txt
   end
```
