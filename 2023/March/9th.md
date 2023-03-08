## 　2023年3月9日(木)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン Node.js VI ~ 4 章：パスワードを安全に取り扱う機能を作ろう(ハッシュ化されたパスワードでログインしよう) ~】まで
## ☆エンジニアとしての基礎を学ぶ
・markdownを使えるようになる  
→基本の文法のインプットまで
# 【わかったこと】
## ☆【学習レッスン Node.js VI】
・<br>
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
・<br>
例）<br>
【>_ターミナル】

    $ npm install bcrypt
    
【app.js】

    const bcrypt = require('bcrypt');
・
# 【次やること】
・markdownを使えるようになる【markdown記法を用いて記事を書いてみる】
# 【感じたこと】
・<br>
# 【学習時間】
・本日:時間分<br>
・月合計:23時間35分<br>
・累計:89時間46分
