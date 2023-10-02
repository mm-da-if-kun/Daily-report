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
[１部: Docker とは]<br>
・SaaS:主に業務で使用するソフトウェア（WindowsなどのOSやアプリ）の機能をインターネットなどのネットワークで、その企業が必要な分だけサービスとして利用できるもの。
・オーケストレーション:大規模なITシステムやアカウントの管理をソフトウェアによって自動化する機能のこと。
・ロードバランサー:サーバーにかかる負荷を、平等に振り分けるための装置のこと。
◎Docker Compose:Docker ComposeはDocker CLIをまとめて実行してくれる便利なツールである。`docker compose up`のような`docker compose`ではじまるコマンドを提供してくれる。「２つのコンテナを起動し」「それぞれのネットワークを構築し」「コンテナのデータをホストマシンと共有させる」という複雑なコマンドを、Yamlファイルを書くことで実現できるツールである。要約すると、`docker`コマンドをまとめて実行してくれるようなものである。Docker Composeを導入すれば極めて簡単に同じ構成を再現できるようになる。
◎Docker Hub:Docker HubはDockerのイメージレジストリであるSaasサービスである。
◎ECS/GKE:Amazon Elastic Container Service(ECS)とGoogle Kubernetes Engine(GKE)は、コンテナ管理サービスである。要約するとDocker Engineの入ったLinuxのことで、ローカル開発に使ったコンテナをそのままデプロイできる場所のことである。
◎ECR/GCR:Amazon Elastic Container Registry(ECR)とGoogle Container Registry (GCR)は、非公開のイメージのレジストリである。要約するとプライベートなDocker Hubのこと。
◎Kubernetes (略してk8sともいう):Kubernetesは多数のコンテナを管理するオーケストレーションソフトウェアで、`kubectl apply`のような`kubectl`ではじまるコマンドを提供してくれる。要約するとコンテナを運用するためのツールである。
◎まとめ
・Docker Engineはコンテナを乗せるソフトウェア。
・Docker CLIはコンテナなどを操作するコマンド。
・Docker DesktopはLinuxカーネルやDocker一式が入ってるGUIアプリケーション。
・Docker Composeはコマンドをまとめて実行してくれるツール。
・Docker HubはイメージレジストリのSaasサービス。
・ECS/GKEはDocker Engineの入ったコンテナ管理サービス。
・ECR/GCRは非公開のイメージレジストリ。
・Kubernetesは起動中のコンテナを見てくれるソフトウェア。
[２部: Docker を理解するためのポイント]

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
・本日02時間00分<br>
・月合計:06時間15分<br>
・累計:491間26分<br>
