# Rails7
* Webpacker,Node.jsを使用しなくてもJavaScriptをRailsアプリで使える
* cssbuilding-railsというGemを利用することで、CSSファイルをアセットパイプラインに乗せることができるようになった
* Active Recordの属性を暗号化した状態でDBに保存することができるようになった
* sprocketsがオプションになった


他にも追加や変更された機能があるが、今回はこの４つについて考えをまとめてみようと思う。

## 私が理解するまでの思考や考え
### Webpacker,Node.jsを使用しなくてもJavaScriptをRailsアプリで使える
個人的にはRails6を使用した際、私がWebpacker初心者だったこともあり、環境構築にとても時間がかかってしまったという嫌な思い出があったので、この変更はとても嬉しかった。   
初心者にとってはJavaScriptを使用するハードルが下がるため良いと思った。   


### cssbuilding-railsというGemを利用することで、CSSファイルをアセットパイプラインに乗せることができるようになった
今回、TailWindを使用した場合に絞ってまとめる。   
私が調べた限りでは、cssbuilding-railsというgemを使用するか、tailwindcss-railsというgemを使用するかの2つがあるようだ。   
他のcssフレームワークを使用する場合は、cssbuilding-rails、TailWindのみならばtailwindcss-railsを使用することがベストのようだ。　　　
他のcssフレームワークもいずれ、gemで提供されるのだろうか？だとしたらとても画期的であるので期待したい。

### Active Recordの属性を暗号化した状態でDBに保存することができるようになった
今までfind_byメソッドなどで簡単に内容が取得できていたが、実は他者に内容を見られてしまうかもしれないというリスクと隣合わせだったことに暗号化になってから気がついた。   
個人的には盲点だった点についての変更だったので、とても印象に残った。

### sprocketsがオプションになった
Rails7の環境構築をしていた際に、undefined method `assets'というエラーが発生した。   
assetsという単語から、「sprocketsが入っていないもしくは異常が発生した」と考えた。      
どうやらRails7からはsprocketsとpropshaftがオプションとして存在し、どちらかを選択して利用するようだ。
