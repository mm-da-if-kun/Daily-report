## 　2023年7月8日(土)
# 【取り組んだ課題一覧】
## ☆HTML/CSSを学ぶ
・「未経験からHTML、CSS をマスターして、WEBデザイナー・エンジニアを目指す　最高の実践コース | Udemy」視聴<br>
→セクション9-10 -最新の目撃情報のCSS(1)- まで<br>
# 【わかったこと】
・レスポンシブWEBデザインを可能にする3つの技術<br>
①メディアクエリ:条件を満たした場合は指定したCSSを適用し、満たさない場合は適用させない。<br>
②フルードグリッド:「グリッドシステム(レイアウトを格子状に分解して配置するデザイン手法)」によるWebデザインとブラウザ幅の変化に応じて内容の大きさを変える「リキッドレイアウト(レイアウトの幅が変更されたとしても元のレイアウトを維持する手法)」を組み合わせた手法のこと。<br>
③フルードイメージ:ブラウザーのウィンドウ幅にあわせて画像のサイズをフィットさせる手法。<br>
・レスポンシブなサイトをサイトを制作する際には小さいデバイスのCSSから作成していく。<br>
→①iPhone②iPad③PCと順に下に記載していく。<br>
例）メディアクエリ<br>
```
/*iPhone用の設定*/
.container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 80px 150px 300px 150px 80px;
    gap: 20px 0px;
}

/*iPad用の設定*/
@media screen and (min-width: 600px) {
    .container {
        grid-template-columns: 2fr 1fr;
        grid-template-rows: 80px 150px 30opx 80px;
    }
}

/*PC用の設定*/
@media screen and (min-width: 834px) {
    .container {
        grid-template-columns: 2fr 3fr 1fr;
        grid-template-rows: 80px 300px 80px;
    }
}
```
・viewport:PCやモバイル（スマホ、タブレット）のようなデバイスごとにコンテンツの表示領域を設定するためのHTML属性値（meta要素のname属性の属性値）のこと。<br>
・「margin-bottom」上下の余白に「%」を指定するときは親要素の横幅である「width」を基準にする。<br>
# 【次やること】
## ☆HTML/CSSを学ぶ
・「未経験からHTML、CSS をマスターして、WEBデザイナー・エンジニアを目指す　最高の実践コース | Udemy」視聴<br>
→セクション9-11 -最新の目撃情報のCSS(2)- から<br>
# 【感じたこと】
・今回は動画内で重要な部分と言っていた通りしっかりと理解しなければいけない大事な部分でした。普段何気なく閲覧しているWebページがこれらの仕組みを使用して作成されている場合もあると知り、少し身近に感じることができました。<br>
・本日:5時間00分<br>
・月合計19時間13分<br>
・累計:264時間28分
