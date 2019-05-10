## fishのUnicode private-use charactersについて

fishはU+F600からU+F73Fの
[Unicode private-use character](http://www.unicode.org/faq/private_use.html)
を内部的に使用しています.
この範囲の文字を使用した場合, Unicodeの'replacement character', U+FFFDに変換されます.
これにはインタラクティブな入力とファイルによる入力が含まれます.
(ただし実行されるプログラムには関係しません.)
