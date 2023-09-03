## 　2023年9月2日(土)
# 【取り組んだ課題一覧】
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション10「69.次レクチャーの補足(AnacondaアーカイブのURLについて)」まで<br>
# 【わかったこと】
・コンテナは指定しなければ基本的にroot権限で実行される。<br>
・dockerファイルで作成したファイルはroot権限で実行されて作成されているためrootユーザーが所有するファイルである。<br>
・`-u <user id>:<group id>`:ユーザIDとグループIDを指定してコンテナをrunする。<br>
例）`docker run -it -u $(id -u):$(id -g) -v ~/Desktop/mounted_folder:/created_in_run <image> bash`<br>
→`$id -u`:ユーザID確認,`$id -g`:グループID確認<br>
```
・パーミッションの見方
　　　　　|　①　|　②|　③|
 d rwx　rwx rwx
①所有者
②所有グループ
③その他
・'_':ファイル
・'d':ディレクトリ
・'l':シムリンク
・'r':読み取り
・'w':書き込み
・'x':実行
```
・`-p <host_port>:<container_port>`:ホストのポートをコンテナのポートに繋げる。(ホストとコンテナのポートは同じでなくてもよい。)<br>
例）`docker run -it -p 8888:8888 --rm jupyter/datascience-notebook bash`<br>
・publish:公開する。<br>
・`--ccpus <# of CPUs>`:コンテナがアクセスできる上限のCPUを設定。`<# of CPUs>`には物理コアの数を入力する。<br>
・`--memory <byte>`:コンテナがアクセスできる上限のメモリを設定する。<br>
例）`docker run -it --rm --cpus 4 --memory 2g ubuntu bash`<br>
・`docker inspect <container> | grep -i cpu`:コンテナやイメージの様々な情報を取得する。<br>
・`sysctl -n hw.physicalcpu_max`:物理コア数<br>
`sysctl -n hw.logicalcpu_max`:論理コア数<br>
・`sysctl hw.memsize`:メモリ(byte)<br>
```
・1 K byte = 1024 byte = 2^10(2進数なため)
・1 M byte = 1024 * 1024  byte
・1 G byte = 1024 * 1024 * 1024 byte
```
【次やること】
## ☆ブログでのアウトプット
・他のテーマについてのブログの原稿の下書き、ブログの投稿<br>
→継続<br>
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション10:「70.Dockerfileを書く」から<br>
# 【感じたこと】
・セクション9-62で`docker run -it -u $(id -u):$(id -g)`で実行し権限をみた時にroot表記になっていましたが、バグ？でそのように表示されるようでした。(実際は取得したユーザ。)実行するときちんと想定通りの挙動になりました。気を付けたいと思いました。<br>
・恥ずかしながら「1 K byte = 1024 byte = 2^10(2進数なため)」を知りませんでした。<br>
・本日:2時間30分<br>
・月合計:3時間34分<br>
・累計:406間28分<br>
