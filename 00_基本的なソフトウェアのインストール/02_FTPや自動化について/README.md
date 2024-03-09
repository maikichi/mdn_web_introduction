## FTP プログラム
→ウェブページを公開する時にファイルをサーバーにアップロードするために必要！

<details><summary>FTPとは</summary>
  
- File Transfer Protocol
- ネットワーク上でファイルを送受信する際に使用する通信プロトコル（Protocol：通信規約・決まりごと）の一種
- クライアントサーバーモデルを使用して、FTPクライアントとウェブサーバーの間で、ファイルの転送をサポート
- コマンドチャネルとデータチャネルという2つの独立したチャネルを使用して情報を転送。デフォルトでは、どちらのチャネルも暗号化されておらず、悪意のある第三者によって転送しているデータが盗用される恐れがある
- 最近ではFTP の代わりに Gitが用いられつつある
  
</details>

<details><summary>(S)FTP とは</summary>
  
- SSH File Transfer Protocol（SSHファイル転送プロトコル）の略だが、Secure File Transfer Protocol（安全なファイル転送プロトコル）とも呼ばれている
- FTPよりも安全なので常に(S)FTPを利用することが望ましい  

:point_right:[Cyberduck](https://cyberduck.io/)、[Fetch](https://fetchsoftworks.com/)、[FileZilla](https://filezilla-project.org/)などがある

[Cyberduck](https://cyberduck.io/)
- 無料
- Windows用とMac対応
- アイコンなども分かりやすく非常に直感的に操作を行うことが可能
- 動作が遅い

[Fetch](https://fetchsoftworks.com/)
- 有料
- Mac OSのみ
- あまり使用しない...

[FileZilla](https://filezilla-project.org/)
- 無料
- 最も人気のあるFTPクライアントの一つ
- Mac、Windows、Linux対応
  
</details>


## 自動化システム
コードの最小化やテストの実行などのような反復作業を自動的に実行することができる
👉Webpack、Grunt、Gulp などがある

[Webpack](https://webpack.js.org/)
- モジュールバンドラー
- モジュールバンドラーとは、複数のファイルを１つにまとめて出力してくれるツールのこと。（複数ファイルをまとめることを「バンドル」と呼ぶ）
- 主にJavaScriptをバンドルする役割が多いみたいだが、CSSや画像などもバンドルできるらしい

[Grunt](https://gruntjs.com/)
- 対応している処理はファイルの結合やSassやTypeScriptなどの変換（コンパイル）、JavaScriptやCSSの最小化（minify）など
- JavaScriptで記述され、*npmで公開されている。通常はNode.js上で実行され、Nodeが対応している環境であればどこでも動作させることができる
*node.jsのライブラリやパッケージを管理するためのツール。package.jsonが設定ファイル

[Gulp](https://gulpjs.com/)
- ファイルを圧縮してファイルサイズを軽くしたり、サーバーにアップロードをする作業を自動化したりすることで開発を効率的に行うことができる
- 一度定義したタスクやインストールしたプラグインを開発者間で共有でき、チーム内で一定の品質を保った開発ができるようになる
- Gruntより処理が高速、コード量が少なくてすむ
