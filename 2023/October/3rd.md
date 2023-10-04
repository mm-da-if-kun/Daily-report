## 　2023年10月3日(火)
# 【取り組んだ課題一覧】
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「２部: コンテナに接続する」(途中)まで<br>
# 【わかったこと】
[２部: Docker を理解するためのポイント]<br>
◎新コマンドと旧コマンドについて<br>

| 旧コマンド | 新コマンド |
|:------------:|:------------:|
| docker build | docker image build |
| docker run | docker container run |
| docker pull | docker image pull |
| docker create | docker container create |
| docker start | dokcer container start |
| docker images | docker image ls |
| docker ps | docker container ls |

◎まとめ<br>
①基本の要素<br>
・コンテナはホストマシン上の隔離されたプロセス<br>
・イメージはレイヤーというメタ情報の集積で、Docker Hubなどで公開される<br>
・Dockerfileはイメージにレイヤーを重ねるテキストファイルで、GitHubなどで共有する<br>
②基本のコマンド<br>
・コンテナを起動する(`container run`)<br>
・イメージを作成する(`image build`)<br>
・コンテナを操作する(`container exec`)<br>
③コマンドの形<br>
・なにをどうするかの意識が一番大事<br>
・理解しやすい新コマンドと短く書ける旧コマンドがある<br>
④Dockerの周辺知識<br>
・Docker Composeはコンテナをまとめて起動するツールで、開発環境の構築に便利<br>
・Kubernetesはコンテナを運用するツールで、インフラ構築に便利<br>
[２部: コンテナの基礎操作]<br>
◎まとめ<br>
・コンテナを起動するには`container run`<br>
・コンテナ一覧を確認するなら`container ls`<br>
・起動中のコンテナを停止するなら`container stop`<br>
・停止済のコンテナを削除するなら`container rm`<br>
・起動中のコンテナを削除するなら`container rm --force`<br>
[２部: コンテナ起動時の基本の指定]<br>
・アーキテクチャ:情報システムの設計方法、設計思想、およびその設計思想に基づいて構築されたシステムの構造などのこと。<br>
・`--rm`オプションを使うと、コンテナが停止したときに自動で削除されるようになる。<br>
[２部: コンテナの状態遷移]<br>
◎まとめ<br>
・コンテナはメインプロセス(PID = 1)を実行するために起動する<br>
・コンテナが停止する理由は大きく分けて２つある<br>
①コンテナを停止する<br>
②メインプロセスが終了する<br>
・即時停止とバックグラウンド実行(`--detach`オプション)と混同しない<br>
[２部: コンテナの状態保持]<br>
◎まとめ<br>
・コンテナは起動するたびに違うコンテナである<br>
・コンテナの操作はほかのコンテナに影響しない<br>
・別のコンテナに変更を反映するには、なんらかの対処が必要<br>
* Dockerfile<br>
* ボリュームやバインドマウント<br>
[２部: コンテナに接続する]<br>
◎まとめ<br>
・`container exec`で起動中のコンテナに命令ができる<br>
・`container run`と`container exec`を混同しない<br>
・SSH接続は基本的にはせず、`bash`を命じれば良い<br>
# 【次やること】
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「２部: イメージの基礎」(途中)から<br>
# 【感じたこと】
・本日は昨日に引き続き任意課題のインプットを行いました。今まで学習してきた内容がわかりやすく記載されていました。また新・旧コマンドについても記載されていて以前疑問に思っていたことも解決しました。<br>
・本日02時間45分<br>
・月合計:11時間00分<br>
・累計:496間11分<br>
