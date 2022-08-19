# Token
GitHubではパスワードの代わりにPersonal Access Tokenを発行して、セキュリティを保っている。

## エラー
remote: Invalid username or password.
fatal: Authentication failed for 'https://github.com/suzuki-yuka-27/net_shopping_size.git/'

これは、Tokenの有効期限が切れたことによるエラーである。
無期限で設定することも可能だが、セキュリティの脆弱性に繋がる恐れがあるため、私は有効期限を設定している。

## 解決方法
Tokenの有効期限が切れた場合、更新をすれば再度使用できるようになる。

1. ブラウザでGitHubにログイン
2. 右上のプロフィール画像をクリックし、Settingsをクリック
3. 左メニューのDeveloper settingsをクリックし、Pesonal access tokensを選択
4. 有効期限切れになったTokenの「Expires on 日時」をクリックする
5. パスワード（アカウント作成時のもの）を入力
6. Regenerate tokenをクリックし、新しいトークンを作成する(※この段階でしかTokenを確認できないため、必ずメモする）
7. ターミナルに戻り、エラーが発生した操作を行うと、ユーザー名とパスワードの入力を求められるので入力する
