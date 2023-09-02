## 　2023年9月1日(金)
# 【取り組んだ課題一覧】
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション9「61.-vオプションを使ってファイルシステムを共有する」まで<br>
# 【わかったこと】
```
⚫︎WORKDIR:Docker instructionの実行ディレクトリを変更する
・構文: WORKDIR <絶対path>
→WORKDIRで指定したフォルダがない場合作成する。
・Docker instructionはルート直下で実行される。(cdコマンドで移動していても)
→「&&」で繋げた場合はcdコマンドで移動した先のディレクトリでtouchコマンド等が実行される
例）
FROM ubuntu:latest
RUN mkdir sample_folder && \
    cd sample_folder && \
    touch sample_file

例）上記をWORKDIRを使用した方法で書き換える
FROM ubuntu:latest
WORKDIR　/sample_folder
RUN touch sample_file
```
・`-v <host>:<container>`:オプションでホストのファイルシステムをコンテナにマウントする。(docker runコマンドのオプション)`-v`で指定したコンテナのフォルダはコンテナにない場合は自動で作成される。<br>
例）`docker run -it -v ~/Desktop/mounted_folder:/new_dir <image> bash`<br>
・コードなどはなるべくHostに置いておいてContainerには持っていかない。<br>
【次やること】
## ☆ブログでのアウトプット
・他のテーマについてのブログの原稿の下書き、ブログの投稿<br>
→継続<br>
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション9:「62.-uオプションを使って，ホストとコンテナのアクセス権限を共有する」から<br>
# 【感じたこと】
・WORKDIRと-vオプションは共通して指定したフォルダがない場合は自動で作成されるとい仕様はコードの記述を少なくできるため忘れないようにしたいと思います。<br>
・近頃集中できていないことが多かったため少し気分転換を行いました。。<br>
・本日:1時間04分<br>
・月合計:1時間04分<br>
・累計:403間58分<br>
