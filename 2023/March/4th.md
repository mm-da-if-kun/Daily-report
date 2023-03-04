## 　2023年3月4日(土)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン Node.js II ~ 4 章：作成機能を作ろう(作成画面の作成) ~】まで
# 【わかったこと】
## ☆【学習レッスン JavaScript VII】
・ this.setState({プロパティ名: 変更する値})とすることで、指定されたプロパティに対応するstateの値が変更される。その結果、「this.state.name」で表示できる値も変更される。<br>
例）<br>

        <div>
            <h1>こんにちは、にんじゃわんこさん！</h1>
            <button onClick={()=>{this.setState({name: 'ひつじ仙人'})}}>
                ひつじ仙人
            </button>
            <button onClick={()=>{this.setState({name: 'にんじゃわんこ'})}}>
                にんじゃわんこ
            </button>
        </dive>
・stateの変更には、注意点があり,Reactでは、「stateの値に直接代入することで値を変更してはいけない」という決まりがある。値を変更したい場合は、setStateを使うこと。<br>
・メソッドはクラスの中で定義する。メソッド名() { 処理 }とすることでメソッドは定義できる。メソッドは関数と似たようなもので、中括弧{ }の中に行いたい処理を記述する。(復習)<br>
・下記のようにメソッドはイベント内で呼び出すこともできる。<br>
例）<br>

        render () {
            return (
            :
                <button onClick={()=>{this.setState({name: 'ひつじ仙人'})}}>
                    ひつじ仙人
                </button>
            );
        }
## ☆【学習レッスン React II】
・App.jsに書かれているJSXは最終的にHTMLに変換されて、ブラウザに表示される。Reactのコードを実際にブラウザに表示するには、App.js以外にもindex.jsとindex.htmlというファイルが必要になる。<br>
・表示の流れ<br>
→index.js内で「ReactDOM.render(<App />, ...」と書くことで、App.jsのJSXが、HTMLに変換される。この書き方は定型文のようなものなので、暗記しておく必要はない。さらに「..., document.getElementById('id名'));」と書くことで、変換されたHTMLがindex.htmlの指定したid名の要素の中に挿入される。最終的に、index.htmlの内容がブラウザに表示される。<br>
例）<br>
【App.js】

    class App extends React.Component {
        render () {
            return (
                <div>
                    <h1>Hell World!</h1>
                </div>
            );
        }
    }
    export default App;
    
 【index.js】

    import App from './components/App';
    ReactDOM.render(<App/>, document.getElementByld('root'));
            
 【index.html】

    <body>
        <div id="root"></div>
    </body>
・JSXは最終的にindex.htmlに挿入され、ブラウザに表示される。そのため、index.html内でstylesheet.cssを読み込むことで、CSSを適用することができる。<br>
例）<br>

    <head>
        <link rel="stylesheet" href="stylesheet.css">
    </head>
・JSXにはHTMLと同じように、JSXのタグ名を指定してCSSを適用することができる。また、JSXにクラス名をつける場合、HTMLと書き方が違うため注意すること。クラス名は、下記のように「className='クラス名'」とする。CSSの指定方法は変わらない。<br>
例）<br>
【App.js】

        render () {
            return (
                <div>
                    <h1>Hell World!</h1>
                    <p className='text'>Hell React</p>
                </div>
            );
        }
        
【stylesheet.css】
    h1 {
        color: red;
    }
    .text {
        color: blue;
    }
・コンポーネントは「部品」や「パーツ」という意味。Reactでは、見た目を機能ごとにコンポーネント化して、コンポーネントを組み合わせることでWebサイトの見た目を作る。<br>
・コンポーネントを作成するために、まず、Reactをインポートする。そして、React.Componentを継承するクラスを作成する。このクラスがコンポーネントとなる。作成したクラスの中で、renderメソッドを定義し、return内にJSXを記述する。<br>
例）<br>

        import React from 'react';
        class Language extends React.Component {
            render () {
                return ()
                    //-------JSX-------
                ;
            }
        }
・App.js内でLanguageコンポーネントを呼び出すには、まず下記のように作成したコンポーネントをexportする必要がある。<br>
例）<br>

        import React from 'react';
        class Language extends React.Component {
            render () {
                return ()
                    //-------JSX-------
                ;
            }
        }
        export default Language;
・Languageコンポーネントを表示するには、App.jsで下記の2つの手順を行う必要がある。<br>
①コンポーネントをインポート<br>
②JSX内に<コンポーネント名 />と書く<br>
例）<br>

    import React from 'react';
    import Language from './Language';　　　  ①
    class App extends React.Component {
        render () {
            return (
                <div>
                    <h1>言語一覧</h1>　　　　　 ②
                    <Language />
                </div>
                :
・コンポーネントは一度作れば、左の図のように、何度でも呼び出すことができる。<br>
例）<br>

        render () {
            return (
                <div>
                    <h1>言語一覧</h1>
                    <div className='language'>
                        <Language />
                        <Language />
                        <Language />
                    </div>
                </div>
                :
・App.jsから、各言語の名前と画像のデータをLanguageコンポーネントに渡すことによって、言語ごとに表示を変えることができる。App.jsから渡すこのデータをprops（プロップス）という。<br>
・propsは、「props名=値」という形で、コンポーネントを呼び出す箇所で渡す。タグの中身は、改行することで見やすくなる。<br>
例）<br>

        render () {
            return (
                <div>
                    <Language
                        name ='HTML & CSS'
                        image ='https://...'
                    />
                <div>
                :
                </div>
・渡されたpropsは、this.propsで取得できる。this.propsは{ props名: 値}というオブジェクトになる。<br>
例）<br>

        render () {
            console.log(this.props);
            return (
                :
            );
        }
・this.propsと書くことで{props名: 値}というオブジェクトを取得できるため、「this.props.props名」とすることでpropsの値を取得できる。<br>
例）<br>

        render () {
            return (
                :
                <div className='language-name'>
                    {this.props.name}
                </div>
                :
・コンポーネントを何度も呼び出す場合、mapメソッドを使用すると効率的に呼び出せる。<br>
例）<br>

        const languageList = [
            {name: 'HTML & CSS', image: 'https://...'}
        ];
            :
        return (
            <div>
                {languageList.map((languageItem)=>{
                    return (
                        <Language
                            name={languageItem.name}
                            image={languageItem.image}
                        />
                        :
## ☆【学習レッスン React III】
・ポップアップのことをモーダルと呼ぶ。<br>
・サイトは複数のコンポーネントからできている。Appコンポーネントの中に、Header, Main, Footerという3つのコンポーネントがあり、さらにMainコンポーネントの中にコンポーネントがある。<br>
・JSXは、下記のように、変数に代入し{変数名}で表示することができる。<br>
例）<br>

        render () {
            let text = <p>一緒にReactを学びましょう！</p>;
            return {
                <div>
                    <h1>Hell World</h1>
                    {text}
                </div>
            );
        }
・変数に代入するJSXが複数行の場合、下記のようにJSXを()で囲む。<br>
例）<br>

        render () {
            let modal;
            if (this.state.isModalOpen) {
                modal = (
                  <div className='modal'>
                    :
                  </div>  
                );
            :    
## ☆【学習レッスン React IV】
・フォームのJSXは、HTMLと違った書き方をするので気をつけること。<br>
例）<br>
【HTML】<br>
⑴```<input>```<br>
⑵```<textarea></textarea>```<br>
【JSX】<br>
⑴```<input />```<br>
⑵```<textarea />```<br>
・送信ボタンはinputタグを用い、type='submit'を指定する。また、ボタンの表示名を変更するために、value='表示名'を指定する。こちらも/(自己クローズタグ)を忘れないように気をつけること。また、フォーム全体は、```<form>```タグで囲む必要がある。入力欄と送信ボタンを囲むように、```<form>```タグを書くこと。<br>
例）<br>

    <form>
        :
        <textarea />
        <input
            type='submit'
            value='送信'
        />
        :
    </form>
・フォームが送信されたときに処理を実行するには、formタグに対してonSubmitイベントを指定する。下記のようにstateの値を変更するメソッドを作成し、フォームの送信時に呼び出す。<br>
例）<br>

    handleSubmit () {
        this.setState({isSubmitted: true});
    }
    render () {
        :
        <form onSubmit={()=>{this.handleSubmit()}}>    
・Reactでフォームを作る場合、stateと入力値を紐づける必要がある。また、HTMLと同様にvalue属性に値を指定することで、指定した値を表示することができる。そのため、value属性にstateの値を指定すると、フォームの入力欄にstateの値が表示される。<br>
例）メールアドレスの入力値を管理するstateのemailを用意。また、inputタグのvalue属性にstateの値を指定。<br>

    super(props);
    this.state = {
        :
        email: '';
    };
    :
    return (
    :
        <input value={this.state.email}/>
    );
・フォームの入力や削除が行われたときに処理を実行するには、onChangeイベントを用いる。inputタグに対してonChangeイベントを指定する。入力値の取得は、onChangeイベントの関数にeventという引数を追加し、event.target.valueとすると取得できる。eventとevent.target.valueはセットで覚えておくこと。<br>
例）<br>

        <input 
            value={this.state.email}
            onChange={(event)=>{console.log(event.target.value)}}
        />
・複数のstateを更新する場合、コンマ(,)で区切り一度のsetStateでまとめて変更する。<br>
例）<br>

    handleEmailChange (event) {
        const inputValue = event.target.value;
        const isEmpty = inputValue === '';
        this.setState({
            email: inputValue,
            hasEmailErorr: isEmpty,
        });
    }
## ☆【Webについて知ろう！】
・Web-インターネット上にある情報を見る仕組みのこと。<br>
・インターネット上の情報は世界中のサーバーというコンピュータに保存されている。<br>
・それぞれの情報には、インターネット上の場所を示すURLが与えられている。URLは、インターネットの住所のようなものである。<br>
・サーバーの情報を取得するコンピュータをクライアントという。クライアントとサーバーはインターネットでつながっており、情報をやりとりしている。<br>
・サーバーとクライアントのやり取りは、クライアントの要求を元にサーバーが応答するという流れになっている。クライアントの要求をリクエスト(request)、サーバーの応答をレスポンス(response)という。<br>
・リクエストをする際は、URLを用いて場所を指定する。URLは「サーバーの場所」と「サーバーの中の情報の場所」を示している。これのおかげで、世界中のサーバーの中から、特定のサーバーの特定の情報を取得できるようになっている。<br>
・サーバーにはWebページのHTMLが保存されている。そのHTMLを表示するクライアントを、ブラウザという。<br>
・ブラウザとサーバーがやり取りしてWebページを表示するまでの流れ<br>
①ブラウザがサーバーにリクエストを送る<br>
ページのURLをブラウザのアドレスバーに入力したり、Googleなどの検索サイトからProgateのリンクをクリックすることで、ブラウザからサーバーにリクエストが送られる。<br>
② サーバーがURLに応じてHTMLをブラウザに返す<br>
③ブラウザにHTMLが表示される<br>
サーバーから返ってきたHTMLがブラウザに表示される。ここで初めて、見たいと思ったWebページを見ることができる。<br>
## ☆【Webアプリケーションについて知ろう！】
・HTMLだけで作られたWebサイトでは、作成者が更新しないかぎり毎回同じものが表示される。<br>
・Webアプリ-高度な機能を持ったWebサイトのこと。また、Webの仕組みを使ったアプリのこと。iOSアプリやAndroidアプリといったスマートフォンのアプリはWebアプリとは少し異なるものである。一旦、「Webアプリ = ブラウザから使うアプリ」と覚えておくことにする。<br>
・Webアプリの仕組み<br>
①ブラウザがサーバーにリクエストを送る<br>
②サーバーはリクエストの内容（URLなど）に応じて処理を実行し、HTMLをブラウザに返す<br>
このとき必要に応じて、以下のような処理を行う。<br>
・データベースを操作し、データの取得、追加、更新、削除を行う<br>
・データベースから取得したデータをHTMLに変換し、ページの表示内容を変える<br>
データベースとは、Webアプリで使用するテキストや数値などの情報を保存するツールのこと。<br>
③ブラウザにHTMLが表示される<br>
例として、昨日のメモは https://〇〇.com/yesterdayから取得するものする。Webアプリの仕組みを使うと、あらかじめ yesterday というファイルを用意する必要はない。代わりにサーバーはデータベースに保存された昨日のメモのデータを使用して、その都度HTMLを作成する。そのため、元になるデータが変化するたびに作成されるHTMLの中身も変化する。<br>
・Webアプリの開発に必要なプログラミング言語<br>
①ブラウザ上で活躍する言語<br>
・HTML<br>
・CSS<br>
・JavaScript<br>
ブラウザに表示される見た目を作ったり、動きをつけたりする言語。これらをクライアントサイド言語、フロントエンド言語などと呼んだりする。HTMLとCSSは、ブラウザに表示する内容を決めたり装飾したりできる言語。JavaScriptもこちらの分類で、HTMLで作ったページに動きをつけたりすることができる。<br>
②サーバー上で活躍する言語<br>
・JavaScript（Node.js）<br>
・Ruby<br>
・Python<br>
・PHP<br>
サーバーで行う処理を記述する言語。サーバーサイド言語、バックエンド言語ともいい、上の言語以外にも数多く存在する。<br>
JavaScriptは本来クライアントサイドの言語だったが、サーバー上でも動かすことのできるNode.jsが登場した。<br>
③データベース上で活躍する言語<br>
・SQL<br>
データベースでデータの取得、保存、更新、削除などを行う言語。<br>
(Ruby on Railsでは、SQLを直接書かなくてもデータベースを操作できるような構文が用意されているが、その裏側ではSQLが使われている。)<br>
## ☆【学習レッスン Node.js I】
・Node.js-Node.jsは本来クライアント側の言語であるJavaScriptをサーバーサイドで動かすための仕組みのこと。<br>
・Express-Node.jsのフレームワーク。Webアプリケーションを作る機能を提供する。<br>
・Node.jsには便利な機能を簡単に使えるようにまとめたパッケージというものがある。Expressもパッケージの１つである。<br>
・パッケージを用意するにはnpm (Node Package Manager)というシステムを使う。npmにはパッケージを共有・取得する機能がある。<br>
・npm installコマンドを使って、インターネットから自分のアプリケーションにパッケージをインストールする。<br>
・Expressを使うには、インストールしたパッケージの読み込みと、実際に使用するための準備が必要である。ここは定型文として覚えておくこと。<br>
例）<br>

    const express = require('express');
    const app = express();
・listenメソッドを用意してapp.jsファイルを実行するとサーバーを起動することができる。ファイルを実行するには「node ファイル名」とする。<br>
例）<br>

    const express = require('express');
    const app = express();
        :
    app.listen(3000);
・下記のように書くことで、/topにリクエストが来た時に、トップ画面を表示することができる。URLに対応する処理を実行することをルーティングという。<br>
例）<br>

    const express = require('express');
    const app = express();
        :
    app.get('/top', ()=>{
        // トップ画面を表示
    });
    
    app.listen(3000);
・ルーティングの処理では、req(リクエストの略)・res(レスポンスの略)の２つの引数を受け取る。reqやresには、リクエスト・レスポンスに関する情報が入っている。ルーティングの処理でres.renderと書くことで、指定したビューファイルをブラウザに表示できる。<br>
例）<br>

    const express = require('express');
    const app = express();
        :
    app.get('/top', (req, res)=>{
        res.render('top.ejs');
    });
    
    app.listen(3000);
・ブラウザに表示する見た目部分にはEJSという形式のファイルを使い、viewsフォルダに配置する。<br>
・CSSを適用するには<br>
①CSSや画像などを適用するには、まずこれらのファイルを置くフォルダを作る。フォルダ名は自由である。(一般的にはpublicが使われる。)そして下記のようにフォルダを指定し、ファイルを読み込めるようにする。<br>
例）<br>

    const express = require('express');
    const app = express();
    
    app.use(express.static('public'));
    app.get('/top', (req, res)=>{
        res.render('top.ejs');
    });
    
    app.listen(3000);
②その後、適用するCSSファイルをpublic配下に作成する。そして、 EJSファイルにはpublicフォルダを起点としたパスを/css/style.cssのように指定する。<br>
例）<br>

    <!DOCTYPE>
    <html>
        <head>
            <title>LIST APP</title>
            <link rel = "stylesheet"
                  herf = "/CSS/style.CSS">
                  :
・CSSと同じように画像もpublicフォルダから読み込むことができる。<br>
例）<br>

    :
    <div class = "top-image">
        <img src = "/images/top.png">
        :
・EJS-HTMLのコードの中にJavaScriptを埋め込むことができるできるNode.jsのパッケージのこと。EJSはnpmからインストールすることで使うことができる。<br>
・JavaScriptのコードを記述するには、```<% %>```または```<%= %>```で囲む。```<% %>```で囲んだ場合はブラウザに何も表示されないので、変数の定義などに用います。変数の値などをブラウザに表示したい場合は```<%= %>```を用いる。<br>
例）<br>

    <% const item = {id: 3,name: 'たまねぎ'} %>
    <p>id: <%= item.id %></p>
・EJSでforEachを利用するとHTMLを直接記述するよりもスッキリ書くことができ、さらに管理しやすくなる。<br>
例）<br>

    <% const items = [
        {id: 1,name: 'じゃがいも'},
        {id: 2,name: 'にんじん'},
        :
    ]; %>
        :
    <ul>
        <% items.forEach((item)=>{ %>
            <li>
                <span><%= item.id %></span>
                <span><%= item.name %></span>
            </li>
        <% }); %>
    </ul>
・「/」のURLをルートURLという。一番初めにアクセスするページはルートURLに設定することが一般的である。
## ☆【学習レッスン Node.js II】
・Node.jsをMySQLに接続するには、mysqlパッケージを利用する必要がある。<br>
・connection.query('クエリ', クエリ実行後の処理)と書くことで、Node.jsからデータベースに対してクエリを実行することができる。クエリ実行後の処理は2つの引数を取ることができる。第1引数のerrorにはクエリが失敗したときのエラー情報が、第2引数のresultsにはクエリの実行結果（ここでは取得したメモ情報）が入る。<br>
例）<br>

    const connection = mysql.createConnection(...);
    
    connection.query(
        'SELECT* FROM items',
        (error, results)=>{
            console.log(results);
            res.render('index.ejs');
        }
    );
・EJSはrenderメソッドから値を受け取ることができる。renderメソッドの第2引数に{プロパティ : 値}と書くことで、EJS側に値を渡すことができる。<br>
例）<br>
【app.js】

    const connection = mysql.createConnection(...);
    
    app.get('/index', (req, res)=>{
        connection.query(
            'SELECT* FROM items',
            (error, results)=>{
                res.render('index.ejs', {items: result})
            }
        );
    });
    
【index.ejs】

    <% items.forEach((item)=>{ %>
・app.get、app.postのgetやpostはメソッドである。Webでは、サーバーへリクエストするときに、どんな処理をしたいかをメソッドで伝えるようにルールで決まっている。getメソッドやpostメソッドは、それぞれ下記のような処理をしたい時に使う。<br>
①画面を表示したい時はGETを使う<br>
②データベースを変更したい時はPOSTを使う<br>
・フォームを作るときはHTMLの<form>タグを用いる。 action属性には送信先のURL、method属性には「post」か「get」をルーティングに合わせて指定する。<br>
例）<br>
【new.ejs】
    
    <form action="/create" method="post">
        <input type="text">
    </form>
    
【app.js】
    
    app.post('create', (req, res)=> {
        :
    })          
# 【次やること】
・progateでの学習【学習レッスン Node.js II ~ 4 章：作成機能を作ろう(フォームを使ったリクエスト) ~】
# 【感じたこと】
・コールバック関数の学習で、関数について再度出てきて使い方はなんとなく理解できましたが、完璧には理解できませんでした。<br>
・HTMLと違い、imgタグでタグの終わりにスラッシュの入れ忘れに注意したいです。<br>
# 【学習時間】
・本日:8時間5分<br>
・月合計:14時間13分<br>
・累計:80時間20分
