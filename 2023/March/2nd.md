## 　2023年3月2日(木)
# 【取り組んだ課題一覧】
## ☆プログラミングに触れてみる
・progateでプログラミングに触れてみよう  
→progateでの学習【学習レッスン JavaScript VI ~ 1 章：配列を操作するメソッドを学ぼう(mapメソッド) ~】まで
# 【わかったこと】
## ☆【学習レッスン JavaScript V】
・ エクスポートできるのはクラスだけではない。文字列や数値や関数など、どんな値でもエクスポートが可能。エクスポートする際は、下記のように「export default 定数名」とする。インポートする際は「import 定数名 from "./ファイル名"」とする。<br>
例）<br>
【sample1.js】

    const text = "Hello World";
    export default text;
    
 【sample2.js】

    import text from "./sample1";
    console.log(text);
・export defaultはデフォルトエクスポートと呼ばれ、そのファイルがインポートされると自動的に「export default 値」の値がインポートされる。そのためエクスポート時の値の名前と、インポート時の値の名前に違いがあっても問題ない。<br>
例）<br>
【dogData.js】

    const dog = new Dog("レオ", 4, "チワワ");
    export default dog;
    
 【script.js】

    import doggy from "./dogData";
    doggy.info();
・デフォルトエクスポートは1ファイル1つの値のみ使える。このファイルをインポートする際には、デフォルトエクスポートの値を自動でインポートするため、値が1つのみとなっている。複数の値をエクスポートしたい場合は、「名前付きエクスポート」を用いる。<br>
・名前付きエクスポートとは下記のように、defaultを書かずに、名前を{}で囲んでエクスポートする書き方のことをいう。名前付きエクスポートした値をインポートする場合は、エクスポート時と同じ名前で値を指定する。インポートする値は、エクスポート時と同様に、「import { 値の名前 } from "./ファイル名"」と{}で囲んで指定する。<br>
例）<br>
【dogData.js】

    const dog = new Dog("レオ", 4, "チワワ");
    export {dog1};
    
 【script.js】

    import {dog1} from "./dogData";
    dog1.info();
・名前付きエクスポートは、デフォルトエクスポートと違い、複数の定数やクラスを指定してエクスポートが出来る。また、下記のように、「export { 名前1, 名前2 }」という形で書くことにより、1つのファイルから複数のエクスポートが出来る。インポートの際も、コンマで区切ることで複数のインポートができる。<br>
例）<br>
【dogData.js】

    const dog1 = new Dog("レオ", 4, "チワワ");
    const dog2 = new Dog("ベン", 2, "プードル");
    export {dog1, dog2};
    
 【script.js】

    import {dog1, dog2} from "./dogData";
    console.log("---------");
    dog1.info();
    console.log("---------");
    dog2.info();
・相対パス-「./ファイル名」のようなファイルの指定のこと。記述されているファイルからみた位置関係を示している。下記では"./dogData"と書いてある。この相対パスは「script.js」からみた「dogData.js」の位置を表している。ドット1つの「./」は相対パスが書かれているファイルと同じディレクトリを意味する。つまり下記で書かれている相対パス"./dogData"は「script.js」と同じsrcディレクトリの中にある「dogData.js」ファイルを意味している。また、1つ上の階層に戻る場合はドット2つの「../」を用いる。<br>
例）<br>
  
    import {dog1, dog2} from "./dogData";
    :
・JavaScriptの世界では、誰かが作った便利なプログラムがパッケージという形で公開されている。また、JavaScriptの機能を使うことで、このパッケージを自分のプログラムの中に組み込んで使うことができる。パッケージを自分のプログラムで使うためには、importを用いてパッケージをインポートする。パッケージのimportは、ファイル名ではなくパッケージ名を指定する。インポートすれば、そのファイルでパッケージが使えるようになる。<br>
・chalkは出力する文字の色を変えることが出来る。下記のように文字列を、chalk.yellowやchalk.bgCyanで囲むだけで、文字の色を変更できる。<br>
例）<br>

    import chalk from "chalk";
    
    console.log(chalk.yellow("Hello World"));
    console.log(chalk.bgCyan("Hello World"));
・readline-syncというパッケージを導入すると、コンソールへの値の入力と、その入力された値をプログラムの中で使うことができるようになる。下記のようにインポートし、readlineSync.question(質問文) のように記述する。質問文が出力されると一旦処理が止まり、コンソールに値が入力されると、次の処理に進む。入力された値は、定数や変数に代入することが出来る。下記のように、readlineSync.questionの部分を定数に代入すると、入力された値がそのまま定数nameに代入される。(年齢のように整数を入力してほしい場合はquestionIntを用いる。)<br>
例）<br>

    import readlineSync from "readline-sync";
    
    const name = readlineSync.question("名前を入力してください：");
    console.log(`${name}と入力されました`);
## ☆【学習レッスン JavaScript VI】
・pushメソッド-pushメソッドとは、配列の最後に新しい要素を追加するメソッドのこと。pushメソッドの後の()の中に追加したい要素を入力する。下記の例では、pushメソッドの引数「4」が配列の最後に追加されている。<br>
例）<br>

    const numbers = [1, 2, 3];
    console.log(numbers);
    numbers.push(4);
    console.log(numbers);
・forEachメソッド-forEachメソッドは配列の中の要素を1つずつ取り出して、全ての要素に繰り返し同じ処理を行うメソッドのこと。下記の例では、配列numbersの要素が順番にすべて出力されている。forEachメソッドの引数には、アロー関数が入っている。配列内の要素が1つずつ順番にアロー関数の引数に代入され、処理が繰り返し実行される。また、引数に入っている関数はコールバック関数と呼ぶ。forEachメソッドのように引数にコールバック関数を使うメソッドはコードが長くなりやすいため、下記のように書くことが多い。処理の前の中括弧「{」から改行することで、長いコードでも見やすくなるという利点がある。<br>
例）<br>

    const numbers = [1, 2, 3];
    numbaers.forEach((number)=>{
        console.log(number);
    })
・findメソッド-findメソッドとは、条件式に合う1つ目の要素を配列の中から取り出すメソッドのこと。下記の例では、配列numbersの中から、3より大きい1つ目の要素である5がfoundNumberに代入されコンソールに出力されている。findメソッドを使うときは下記のように書く。配列numbersの要素が1つずつ引数numberに代入されて処理が進む。コールバック関数の中は { return 条件 } と書くことで、条件に合う要素が戻り値となる。findメソッドは条件に合う要素が見つかった時に終了ため、条件に合う最初の1つの要素しか取り出せない。<br>
例）<br>

    const numbers = [1, 3, 5, 7];
    const foundNumber = numbers.find((number)=>{
        return number > 3;
    });
    console.log(foundNumber);
・配列の要素がオブジェクトの場合もfindメソッドを使うことができる。下記の例ではオブジェクトのプロパティを条件の中で使用している。オブジェクトのプロパティを条件として使用する場合、そのプロパティを持っているオブジェクトそのものを取り出す。<br>
例）<br>

    const characters = [
        {id: 1, name: "にんじゃわんこ"},
        {id: 2, name: "ひつじ仙人"}
    ];
    const foundCharaster = characters.find((character)=>{
        return character.id === 1;
    });
    console.log(foundCharaster);
・filterメソッド-filterメソッドとは記述した条件に合う要素のみを取り出して新しい配列を作成するメソッドのこと。の例では配列numbersから「3より大きい数字」をすべて取り出している。下記の例では配列numbersの要素が1つずつ引数numberに代入される。その後、filterメソッド内で「3より大きい数字」かどうかを判定し、条件に合う要素が定数filteredNumbersに配列として代入される。<br>
例）<br>

    const numbers = [1, 3, 5, 7];
    const filteredNumbers = numbers.filter((number)=>{
        return number > 3;
    });
    console.log(filteredNumbers);
・findメソッドと同様に、配列の要素がオブジェクトの場合もfilterメソッドを使うことができる。下記の例ではオブジェクトのプロパティを条件の中で使用している。オブジェクトのプロパティを条件として使用する場合、そのプロパティを持っているオブジェクトそのものを取り出す。<br>
例）<br>

    const characters = [
        {name: "にんじゃわんこ", age: 14},
        {name: "ベイビーわんこ", age: 5},
        {name: "ひつじ仙人", age: 100}
    ];
    const filteredCharacters = characters.filter((character)=>{
        return character.age > 10;
    });
    console.log(filteredCharacters);
・mapメソッド-mapメソッドとは、配列内のすべての要素に処理を行い、その戻り値から新しい配列を作成するメソッドのこと。下記の例では配列numbersの全ての要素を2倍した要素を持つ、新しい配列を作成している。下記の例では、配列numbersの要素が1つずつ引数numberに代入されている。その後、mapメソッド内の 「要素を2倍する処理」 をした配列が新しく作られ、定数doubledNumbersに配列として代入されている。コールバック関数の中の処理は { return 値 } と書く。<br>
例）<br>

    const numbers = [1, 2, 3];
    const doubledNumbers = numbers.map((number)=>{
        return number * 2;
    });
    console.log(doubledNumbers);
・mapメソッドもこれまでのメソッドと同様に、配列のオブジェクト要素に対しても使うことができる。下記の例では、mapでfirstNameプロパティとlastNameプロパティを繋げる処理をしている。<br>
例）<br>

    const names = [
        {firstName: "Kate", lastName: "Jones"},
        {firstName: "Brain", lastNmae: "Smith"}
    ];
    const fullNames = names.map((name)=>{
        return name.firstName + name.lastNmae;
    });
    console.log(fullNames);
# 【次やること】
・progateでの学習【学習レッスン JavaScript VII ~ 1 章：コールバック関数を学ぼう(コールバック関数を学ぼう) ~】
# 【感じたこと】
・
# 【学習時間】
・本日:2時間5分<br>
・月合計:4時間8分<br>
・累計:70時間15分
