## 　2023年3月6日(月)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン Node.js V ~ 2 章：ログイン機能を作ろう(セッションを使ってみよう) ~】まで
# 【わかったこと】
## ☆【学習レッスン Node.js II】
・ セッション管理とはクライアントの状態をサーバーが管理するものである。<br>
・セッションを管理するための準備として、セッションを管理するための機能を提供してくれるexpress-sessionというパッケージをインストールする。そのあと、express-sessionを使用するために必要な情報を書き込む。書き方を細かく覚える必要はない。<br>
例）<br>
【>_ターミナル】

    $ npm install express-session
    
【app.js】

    const mysql = require('mysql');
    const session = require('express-session');
        :
・express-sessionパッケージによって、req.sessionオブジェクトに渡した値を管理できる。保存するにはreq.session.プロパティ名=値と書く。<br>
例）<br>

    app.post('/login', (req, res) => {
        :
        if (req.body.password === results[0].password) {
            req.session.userId = results[0].id;
        } else {
            :
・セッション情報からデータを読み出すときはreq.session.プロパティ名と書く。このとき、express-sessionパッケージが送られてきたセッションIDの確認と、それに関するセッション情報の取得を自動で行う。<br>
例）<br>

    app.get('/list', (req, res) => {
        const userId = req.session.userId; 
# 【次やること】
・progateでの学習【学習レッスン Node.js V ~ 2 章：ログイン機能を作ろう(常にログイン状態を確認しよう) ~】
# 【感じたこと】
・本日は生活リズムが狂ってしまい、学習に時間をあてることができませんでした。1日1日、後悔しないように学習に臨んでいきたいと思います。<br>
# 【学習時間】
・本日:時間31分<br>
・月合計:19時間<br>
・累計:85時間11分
