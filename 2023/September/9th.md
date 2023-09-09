## 　2023年9月9日(土)
# 【取り組んだ課題一覧】
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション12「101.本セクションまとめ」まで<br>
# 【わかったこと】
・SFTP:SSHで暗号化された通信路を使って安全にファイルを送受信するプロトコル。<br>
例）`sftp -i mydocker.pem ubuntu@<hostname>`<br>
→抜ける時は「exit」を入力してEnterを押す。<br>
```
⚫︎SFTPコマンド
・put:コマンドでローカルマシンのファイルをリモート側に送信する。
例）put local/path [remote/path]
・get:リモートホストの1個のファイルをローカルホストに転送する。
例）get remote/path [local/path]
```
・`docker load`:ファイルもしくは標準入力を通して、tar アーカイブ（ gzip 、 bzip2 、 xz で圧縮している場合も）からイメージやリポジトリを取り込む。<br>
例）`docker load < myimage.tar`<br>
```
・Docker image→tarファイル
docker save {image} > {tar_file}
・tarファイル→Docker image
docker load < {tar_file}
```
・Linuxだと「/var/lib/docker」にDockerのオブジェクトが保存されていく。(Docker daemonのディレクトリ。)<br>
→容量が足りない場合ここの容量を増やしていく。<br>
・Docker daemonの設定ファイル:`etc/docker/daemon.json`<br>
→Docker daemonのオプション等を変更できる。<br>
・`adduser`:新規ユーザーを作成し、設定を決めるコマンド。<br>
構文）`sudo adduser --uid <uid> <username>`<br>
・`nvidia-smi`:NVIDIAのGPUの使用率やメモリ使用量、消費電力、温度などを確認できる。<br>
【次やること】
## ☆Docker
・「米国AI開発者がゼロから教えるDocker講座 | Udemy」視聴<br>
→セクション13:「102.業務で使える超本格Web開発環境を構築する」から<br>
# 【感じたこと】
・進捗は遅いですがエラーが度々出ながらも確実に進めているのでよかったです。<br>
・始めのほうで学習した内容で忘れてしまっている部分があるのでもう一周することも視野に入れて進めていきたいと思います。<br>
・本日4時間54分<br>
・月合計:16時間33分<br>
・累計:419間27分<br>
