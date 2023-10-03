## 　2023年10月2日(月)
# 【取り組んだ課題一覧】
## ☆Docker
⚫︎dockerで開発環境を構築する<br>
・dockerで開発環境を構築するについてブログにまとめる<br>
→課題提出(レビュー待ち)<br>
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「１部: Docker とは」(途中)まで<br>
# 【わかったこと】
[２部: Docker を理解するためのポイント]
◎新コマンドと旧コマンドについて

| 旧コマンド | 新コマンド |
|:------------:|:------------:|
| docker build | docker image build |
| docker run | docker container run |
| docker pull | docker image pull |
| docker create | docker container create |
| docker start | dokcer container start |
| docker images | docker image ls |
| docker ps | docker container ls |

◎まとめ
①基本の要素
・コンテナはホストマシン上の隔離されたプロセス
・イメージはレイヤーというメタ情報の集積で、Docker Hubなどで公開される
・Dockerfileはイメージにレイヤーを重ねるテキストファイルで、GitHubなどで共有する
②基本のコマンド
・コンテナを起動する(`container run`)
・イメージを作成する(`image build`)
・コンテナを操作する(`container exec`)
③コマンドの形
・なにをどうするかの意識が一番大事
・理解しやすい新コマンドと短く書ける旧コマンドがある
④Docker の周辺知識
・Docker Composeはコンテナをまとめて起動するツールで、開発環境の構築に便利
・Kubernetesはコンテナを運用するツールで、インフラ構築に便利
[２部: コンテナの基礎操作]
◎まとめ
・コンテナを起動するには`container run`
・コンテナ一覧を確認するなら`container ls`
・起動中のコンテナを停止するなら`container stop`
・停止済のコンテナを削除するなら`container rm`
・起動中のコンテナを削除するなら`container rm --force`
[２部: コンテナ起動時の基本の指定]
・アーキテクチャとは、情報システムの設計方法、設計思想、およびその設計思想に基づいて構築されたシステムの構造などのこと

# 【次やること】
## ☆Docker
⚫︎dockerで開発環境を構築する<br>
・dockerで開発環境を構築するについてブログにまとめる<br>
→課題提出(レビュー待ち)<br>
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「１部: Docker とは」(途中)から<br>
# 【感じたこと】
・本日も引き続き課題を行い、提出することができました。この後の任意のインプット教材も読みさらにDockerへの理解を深めていきたいです。<br>
・本日01時間00分<br>
・月合計:08時間15分<br>
・累計:493間26分<br>
