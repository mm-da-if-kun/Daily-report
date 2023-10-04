## 　2023年10月2日(月)
# 【取り組んだ課題一覧】
## ☆Docker
⚫︎dockerで開発環境を構築する<br>
・dockerで開発環境を構築するについてブログにまとめる<br>
→課題提出<br>
→LGTMをいただいた。<br>
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「１部: Docker とは」(途中)まで<br>
# 【わかったこと】
[１部: Docker とは]<br>
・SaaS:主に業務で使用するソフトウェア（WindowsなどのOSやアプリ）の機能をインターネットなどのネットワークで、その企業が必要な分だけサービスとして利用できるもの。<br>
・オーケストレーション:大規模なITシステムやアカウントの管理をソフトウェアによって自動化する機能のこと。<br>
・ロードバランサー:サーバーにかかる負荷を、平等に振り分けるための装置のこと。<br>
◎Docker Compose:Docker ComposeはDocker CLIをまとめて実行してくれる便利なツールである。`docker compose up`のような`docker compose`ではじまるコマンドを提供してくれる。「２つのコンテナを起動し」「それぞれのネットワークを構築し」「コンテナのデータをホストマシンと共有させる」という複雑なコマンドを、Yamlファイルを書くことで実現できるツールである。要約すると、`docker`コマンドをまとめて実行してくれるようなものである。Docker Composeを導入すれば極めて簡単に同じ構成を再現できるようになる。<br>
◎Docker Hub:Docker HubはDockerのイメージレジストリであるSaasサービスである。<br>
◎ECS/GKE:Amazon Elastic Container Service(ECS)とGoogle Kubernetes Engine(GKE)は、コンテナ管理サービスである。要約するとDocker Engineの入ったLinuxのことで、ローカル開発に使ったコンテナをそのままデプロイできる場所のことである。<br>
◎ECR/GCR:Amazon Elastic Container Registry(ECR)とGoogle Container Registry (GCR)は、非公開のイメージのレジストリである。要約するとプライベートなDocker Hubのこと。<br>
◎Kubernetes (略してk8sともいう):Kubernetesは多数のコンテナを管理するオーケストレーションソフトウェアで、`kubectl apply`のような`kubectl`ではじまるコマンドを提供してくれる。要約するとコンテナを運用するためのツールである。<br>
◎まとめ<br>
・Docker Engineはコンテナを乗せるソフトウェア。<br>
・Docker CLIはコンテナなどを操作するコマンド。<br>
・Docker DesktopはLinuxカーネルやDocker一式が入ってるGUIアプリケーション。<br>
・Docker Composeはコマンドをまとめて実行してくれるツール。<br>
・Docker HubはイメージレジストリのSaasサービス。<br>
・ECS/GKEはDocker Engineの入ったコンテナ管理サービス。<br>
・ECR/GCRは非公開のイメージレジストリ。<br>
・Kubernetesは起動中のコンテナを見てくれるソフトウェア。<br>
# 【次やること】
## ☆Dockerの任意教材
⚫︎実践 Docker - ソフトウェアエンジニアの「Docker よくわからない」を終わりにする本を見る<br>
→「２部: Docker を理解するためのポイント」(途中)から<br>
# 【感じたこと】
・提出した課題についてLGTMをいただきましたが、同時に何点かコメントもいただき早速その内容を修正し確認しました。レビューしていただくことで自身では見落としていた部分に気づくことができたので勉強になりました。<br>
・本日02時間00分<br>
・月合計:08時間15分<br>
・累計:493間26分<br>
