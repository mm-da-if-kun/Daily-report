## 　2023年3月7日(火)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン Node.js VI ~ 2 章：ユーザー登録機能を作ろう(ユーザー登録と同時にログインしよう) ~】まで
# 【わかったこと】
## ☆【学習レッスン Node.js V】
・app.use関数は全てのリクエストに対応する。そのため、ルーティング処理の一番最初に書くことで、毎回実行することができる。受け取ることのできる引数はreq, res, nextの3つである。<br>
例）<br>

    app.use((req, res, next) => {
        // ログイン状態の確認
        next();
    });
        :
    app.get('/list', (req, res) => {
        :
    });
・app.use関数の引数で受け取ったnextは処理の中で関数として使うことができる。next関数を実行すると、リクエストに一致する次の処理を実行することができる。<br>
・res.localsオブジェクトを使うと、res.renderがなくてもEJSファイルに値を渡すことができる。また、res.localsオブジェクトはres.locals.プロパティ名 = 値の形で値を代入することができる。代入した値はレスポンスを返すまで使用可能である。<br>
例）<br>

    app.use((req, res, next) => {
        if (req.session.userId === undefined) {
            res.locals.username = 'ゲスト';
        } else {
            res.locals.username = req.session.username;
        }
        :
・EJSファイルでは代入した値がlocalsオブジェクトに変換される。そのため、値を用いるときにはlocals.プロパティ名と書く。resがつかないので注意すること。<br>
例）<br>

    <header>
        :
        <p>ようこそ、<%= locals.username %>さん</p>
        :
・include機能-EJSにはファイルの中で、別のEJSファイルを呼び出す機能。また、別のEJSファイルを呼び出すときはinclude('ファイル名');と書く。<br>
例）<br>

    <body>

        <%- include('header'); %>
            :
・req.session.destroy( ()=>{ 実行後の処理 })と書くことで、保存したセッション情報を消すことができる。<br>
例）<br>

    app.get('/logout', (req, res) => {
        req.session.destroy((error) => {
            res.redirect('/list');
        });
    });
## ☆【学習レッスン Node.js VI】
・INSERTクエリが成功すると、特に設定しなくても、追加したレコードのidがresultsオブジェクトのinsertIdというプロパティに入ることになっている。<br>
・ミドルウェア関数-Expressでは、このリクエストとレスポンスの間にサーバーが実行する関数のことをいう。例として、これまでルーティングに対応する処理を書いてきた関数が、ミドルウェア関数である。
# 【次やること】
・progateでの学習【学習レッスン Node.js VI ~ 3 章：ユーザーの入力をチェックする機能を作ろう(入力値の空チェック機能を作成しよう) ~】
# 【感じたこと】
・include機能での「<%-」を「<%=」と書かない等、エラーを出さない為にも細かい部分まで気をつけてコーディングしていかなければと思いました。<br>
# 【学習時間】
・本日:1時間59分<br>
・月合計:20時間59分<br>
・累計:87時間10分
