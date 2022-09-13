# has_one関係でfindを使うのに苦労した話
### 前提
ポートフォリオで洋服のジャンルごとにサイズを記録できるサービスを作成中。
その開発過程で、現在ログインしているユーザーのトップスサイズの詳細と編集画面を作成中の出来事である。

### 出来事
現在ログインしているユーザーのトップスをとってきて欲しかったので、`current_user.find(1).top`で使用しようとしたが、図１のエラーが発生してしまった。
current_userの中身を確認する。（図２）

私「しっかり情報入ってるな〜」

このとき、私の頭の中ではhas_many関係でfindを使用した時と同じ思考回路になっていた。
つまり、`current_user.top.find(1)`で得られる「current_userがもつtopのid＝１のデータ」が結果として返ってくると思っていた。
しかし、`current_user.find(1).top`の場合、「id＝１のcurrent_userがもつtopのデータ」が結果として返ってくる。
findのかかる場所がそもそも違っていたのである。
その証拠に図２のcurrent_userのidは３であり、findが求めているid=1のcurrent_userではない。

私「そりゃ、エラーなるってぇぇぇぇぇ」

`User.find(current_user.id).top`とすることで解決した。
調べた記事で`親モデル.find(1).子モデル`と書いてあったので、1であることは決まり事だと勘違いしてしまったことが原因だった、、、。
見たものに縛られすぎず、柔軟に考ることを心がけよう！

【図１】
[![Image from Gyazo](https://i.gyazo.com/2a0f1db82b6ca04049eae7172229e858.png)](https://gyazo.com/2a0f1db82b6ca04049eae7172229e858)

【図２】
[![Image from Gyazo](https://i.gyazo.com/88098ed5b7c732a7b9c0a5b205b01d0e.png)](https://gyazo.com/88098ed5b7c732a7b9c0a5b205b01d0e)
