## 　2023年3月3日(金)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン React I ~ 3 章：stateとイベントを学ぼう(stateの表示) ~】まで
# 【わかったこと】
## ☆【学習レッスン JavaScript VII】
・ JavaScriptでは引数に関数を渡すことができる。引数に渡される関数をコールバック関数と呼ぶ。<br>
・下記のように、関数を呼び出す際に、引数に関数を渡す。関数は、関数名の後ろに()をつけると呼び出され、()をつけなければ関数そのものを指す。よって下記のように、呼び出し方と渡し方で書き方が異なる。<br>
例）<br>

    const printWanko = () => {
        console.log("にんじゃわんこ");
    };
    
    const call = (callback) => {
        console.log("コールバック関数を呼び出します。");
        callback();
    };
    
    call(printWanko);
・コールバック関数は直接引数の中で定義することもできる。動作の流れは、事前に定義した関数を引数に渡す場合と同じである。<br>
例）<br>

    const call = (callback) => {
        console.log("コールバック関数を呼び出します。");
        callback();
    };
    
    call(() => {
        console.log("にんじゃわんこ");
    });
・コールバック関数では、普通の関数と同じように引数を渡すことができる。２つ以上の引数を渡すこともできる。また、コールバック関数の引数と、実行時に渡す引数の数をそろえるように気をつけること。<br>
例）<br>

    const introduce = (callback) => {
        callback("にんじゃわんこ", 14);
    };
    
    introduce((name, age) => {
        console.log(`${name}は${age}歳です。`);
    });
## ☆【学習レッスン React I】
・下記のように、App.jsというファイルのrenderメソッドのreturn内に、```<h1>Hello World</h1>```と記述すると、ブラウザに「Hello World」と表示される。<br>
例）<br>

    class App extends React.Component {
        render () {
            return (
                <h1>Hell World</h1>
            );
        }
    }
・JSXは、HTMLとほとんど同じように記述することができる。見出しには```<h1>```タグや```<h2>```タグ、文章には```<p>```タグ、その他```<div>```タグなど、HTMLと同様のタグが使えるようになっている。<br>
・JSXはほとんどHTMLと同じだが、いくつか違いがある。return内に複数の要素があるとエラーになる。複数の要素がある場合は、下記のように<div>タグで囲んで、1つの要素にまとめること。<br>
例）<br>

    render () {
        return(
            <div>
                <h1>h1 です</h1>
                <h2>h2　です</h2>
                <p>p　です</p>
            </div>
        );
    }
・JSXを{/* */}で囲むと、その部分はコメントになる。コメントにすると、そのJSXは表示されない。正しくコメントにできている場合は、囲んだ部分が灰色になる。<br>
・imgタグは、HTMLでは、```<img src='画像のURL'>```のように閉じタグが必要ない。一方、JSXでは閉じタグが必要である。```<img src='画像のURL' />```のように、タグの終わりにスラッシュ「/」を記述する。<br>
例）<br>

    render () {
        return(
            <img src='https://prog-8.com/family.jpg'/>
        );
    }
・App.jsは下記の要素で構成されている。App.jsを作成する時はいつもこのように書くため、丸暗記する必要はない。<br>
❶Reactをimport<br>
❷React.Componentを継承するクラスの定義<br>
❸JSXを戻り値とするrenderメソッドを定義<br>
❹クラスをexport<br>
    
例）<br>

    ❶import React from 'react';
    ❷class App extends React.Component{
        ❸render () {
            :
        }
    }
    
    ❹export default App;
・JSXとJS ( JavaScript ) の記述部分は分かれている。renderメソッドのreturn内のみ、JSXで記述する必要がある。JSXで記述された要素はブラウザに表示される。<br>
・renderメソッドの、returnの外にはJavaScriptを記述できる。<br>
・returnの中でも、JSXにJavaScriptを埋め込むことが出来る。JSXにJavaScriptを埋め込むには、JavaScriptの部分を中括弧{ }で囲む。また、下記のようにタグの属性の値も、同様に中括弧{ }を使ってJavaScriptを記述することが出来る。<br>
例）<br>

    render () {
        const imgUrl = 'https://prog-8.com/family.jpg';
        return(
            <img src= {imgUrl}/>
        );
    }
・JSXは{/* */}で囲み、JavaScriptでは文頭に「//」を書くと、その行はコメントとみなされる。<br>
・ボタンは<button>タグで指定する。ボタンには<button>タグで囲まれている文字が表示される。<br>
例）<br>

    render () {
        return (
        <div>
            <h1>こんにちは、にんじゃわんこさん！</h1>
            <button>ひつじ仙人</button>
            <button>にんじゃわんこ</button>
        </dive>
        )
    }
・イベントを用いると、「何かが起きたときに、処理を実行するように指定」することができる。アロー関数を使って、タグ内にイベント名={() => { 処理 }}と書くことで、指定したタイミングで処理を実行できる。アロー関数はJavaScriptなので、{}で囲むことを忘れないようにすること。<br>
・onClickイベント-クリックされた時に処理を実行するイベント。<br>
例）<br>

        <div>
            <h1>こんにちは、にんじゃわんこさん！</h1>
            <button onClick={()=>{console.log('ひつじ仙人')}}>
                ひつじ仙人
            </button>
            <button onClick={()=>{console.log('にんじゃわんこ')}}>
                にんじゃわんこ
            </button>
        </dive>
・ユーザーの動きに合わせて変わる値のことを、Reactではstateと呼ぶ。<br>
・stateを使った表示の変更<br>
①stateの定義<br>
②stateの表示<br>
③stateの変更<br>
・stateは、constructorの中で、オブジェクトとして定義する。ここで定義したオブジェクトがstateの初期値となる。その他の部分の、「constructor(props)」や「super(props);」といった処理はいつも同じ記述をするため、定型文として覚えておけば問題ない。<br>
例）<br>

    class App extends React.Component {
        constructor (props) {
            super (props);
            this.state = {name: 'にんじゃわんこ'};
        }
    }
・定義したstateは、this.stateで取得することができる。stateの定義で学んだ通り、stateはオブジェクトなため、console.log(this.state)をするとオブジェクトが出力される。また、this.stateはオブジェクトなため、this.state.プロパティ名とすることで、指定したstateのプロパティ名に対応する値を取得できる、<br>
例）<br>

    class App extends React.Component {
        constructor (props) {
            super (props);
            this.state = {name: 'にんじゃわんこ'};
        }
        render () {
            return(
                <h1>こんにちは、{this.state.name}さん！ </h1>
            );
        }
    }
# 【次やること】
・progateでの学習【学習レッスン React I ~ 3 章：stateとイベントを学ぼう(stateの変更) ~】
# 【感じたこと】
・コールバック関数の学習で、関数について再度出てきて使い方はなんとなく理解できましたが、完璧には理解できませんでした。<br>
・HTMLと違い、imgタグでタグの終わりにスラッシュの入れ忘れに注意したいです。
# 【学習時間】
・本日:2時間<br>
・月合計:6時間8分<br>
・累計:72時間15分
