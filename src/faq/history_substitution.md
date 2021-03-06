## 履歴置換(`!$`など)が働かないのはなぜ？

履歴置換は対話形式の編集が可能になる前に開発された行儀の悪いインターフェースであるからです.
fishはこのインターフェースを無くし, 代わりに完全な対話形式の履歴想起インターフェースを持ちます.
これまでの習慣を少し変える必要があります.
古い行や単語を修正したいときにはまずそれを思い出してそれから編集してください.
例えば`sudo !!`とは打たないでください. まず`Up`キーを押してそれから`Home`, 最後に`sudo`と打ってください.

fishの履歴想起は以下のようにとてもシンプルかつ効率的です.

- 他のモダンなシェル同様, `↑`は最後に実行した行から順に行全体を呼び出します.
一回押すと`!!`を置き換え, `!-3`などを置き換えたい場合には次のようにしてください.
  - ずっと前の履歴を呼び出したいとき, そのコマンドの一部を打ってから`↑`を一回或いは複数回押してください.
  こうすることでその文字列を含んだコマンドに絞って呼び出すことができ,
  必要な行をより早く手に入れることができます.
  これは`!vi`や`!?bar.c`などの代わりになります.

- `Alt+↑, Up`は直近に実行した行から順番に引数のみを呼び出します.
一回押すと`!$`を置き換え, `!!:4`などを置き換えたい場合は次のようにしてください.
  - 使いたい引数が履歴のずっと前にある場合, 引数の一部を打ってから`Alt+↑, Up`を押してください.
  こうすることでその文字列を含んだ引数に絞って呼び出すことができ,
  必要な行をより早く手に入れることができます. 試してみるととても便利なことがわかるでしょう.
  - 同一の行から複数の引数を再利用したい場合(`!!:3*`のように),
  全体を呼び出した後必要ない部分を削除するといいでしょう.
  (`Alt+D`や`Alt+Backspace`を用いると手早く済みます.)

fishでの行の編集について, 詳細は[ドキュメント]を参照してください.
