## 　2023年3月8日(水)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン Node.js VI ~ 4 章：パスワードを安全に取り扱う機能を作ろう(ハッシュ化されたパスワードでログインしよう) ~】まで
## ☆エンジニアとしての基礎を学ぶ
・markdownを使えるようになる  
→基本の文法のインプットまで
# 【わかったこと】
## ☆【学習レッスン Node.js VI】
・リクエストを受け取ってからレスポンスを返す間に、複数のミドルウェア関数をつくることができる。また、ミドルウェア関数は、上から順番に実行される。<br>
例）<br>

    app.post('/signup',
        (req, res, next) => {
            console.log('入力値の空チェック');
                :
            next();
        },
        (req, res) => {
            cosole.log('ユーザー登録');
                :
        }
    );
・バリデーション-データをチェックする仕組みのことをいう。<br>
・bcrypt（ビークリプト）パッケージ-パスワードのハッシュ化を行う際に用いる。bcryptパッケージは、普通の文字列のパスワードをハッシュ化して、安全性の高いパスワードを作るのに広く使われている。<br>
例）<br>
【>_ターミナル】

    $ npm install bcrypt
    
【app.js】

    const bcrypt = require('bcrypt');
・パスワードをハッシュ化するには、bcryptパッケージのhashメソッドを用いる。第1引数に普通の文字列のパスワードを与えると、コールバック関数の引数hashから、ハッシュ化されたパスワードを取得できる。<br>
例）<br>

    app.post('/signup',
        (req, res) => {
            :
            bcrypt.hash(password, 10, (error, hash) => {
                :
            });
・ユーザーの入力した普通の文字列のパスワードと、データベース上のハッシュ化されたパスワードを比較するにはbcryptパッケージのcompareメソッドを使う。普通の文字列のパスワードはメソッド内部でハッシュ化される。<br>
例）<br>

    app.post('/login', (req, res) => {
            :
            const plain = req.body.password;
            const hash = results[0].password;
            bcrypt.compare(plain, hash, (error, isEqual) => {
                // 比較した結果により処理を変える
            });
## ☆【Node.jsの開発環境を用意しよう！（macOS）】
・Node.jsの開発環境構築方法
## ☆【Node.jsの新規アプリケーションを作ろう！】
・ローカル環境での新しいExpressのアプリケーションを作成する方法<br>
・npm install express npm install ejsと1つずつinstallコマンドを実行していくことも可能だが、 npm intall インストールしたいパッケージ① インストールしたいパッケージ②... というようにパッケージ名を列挙することで、一度にまとめてインストールすることができる。<br>
・jsファイルを変更した際にはサーバーを再起動しないと反映されないため注意すること。<br>
・一度サーバーを停止してから再度サーバーを起動することで再起動ができる。ファイルの変更を反映したい場合は、Ctrl + Cでサーバーを停止した後に、 node app.js でサーバーを再起動する。
## ☆【Node.jsアプリケーションとMySQLを接続しよう！】
・Node.jsアプリケーションとMySQLを接続する方法
# 【次やること】
・markdownを使えるようになる【markdown記法を用いて記事を書いてみる】
# 【感じたこと】
・本日でProgateの課題を完了させることができました。まだまだ定着していない部分が多々あるので、時間を見つけ復習を行なっていきたいと思います。<br>
# 【学習時間】
・本日:2時間36分<br>
・月合計:23時間35分<br>
・累計:89時間46分
