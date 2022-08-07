# Rails7
初めてRails７を使用するため今までのバージョンとの違いや自分の考えをまとめておこうと思う。

## 変更点
* Webpacker,Node.jsを使用しなくてもJavaScriptをRailsアプリで使える
* cssbuilding-railsというGemを利用することで、CSSファイルをアセットパイプラインに乗せることができるようになった
* Active Recordの属性を暗号化した状態でDBに保存することができるようになった
* SQLクエリに自動的にコメントを付与することができるようになり、スロークエリが発生した場合、ログを見れば特定できる
* 非同期でSQLを実行して結果を取得できるようになった
* バルクインサート・バルクアップサートでタイムスタンプを自動でセットできる
* in_order_of（レコードを指定した順番で取得する）、structurally_compatible?（リレーションのデータ構造が同じかチェックする）というメッソド追加
* ActiveModel：：APIの追加
* weekday_options_for_select(曜日選択のオプションタグを生成する）というヘルパーメソッド追加
* データベースの設定オプションでタスクをオフにできる
* button_toのメソッドがPOSTではなくPATCHを使用
* sass-rails、springが非標準化された
* classicが廃止され、zeitwerkで起動することが必須になった
* byebugの代わりにdebugが標準で含まれるようになった
* ActiveSupport::DigestがSHA-256に変更になった
* Active Storageの画像処理でlibvipsが標準になった
