## 　2023年4月3日(月)
# 【取り組んだ課題一覧】
## ☆Linuxの基礎コマンドを理解する
・インプット教材「もLinux標準教科書」を読む<br>
→途中まで、継続
# 【わかったこと】
## ☆Linuxの基礎コマンドを理解する
・suコマンド<br>
・fdiskコマンド<br>
・デバイス構成の確認コマンド<br>
```$ ls -l /dev/sd*```<br>
・パーティション情報の確認、パーティションの作成、パーティションの種類の変更、パーティション情報の保存コマンド<br>
```
# fdisk /dev/sdc
上記コマンドを入力後、コマンド1文字や数値を入力する。
```
・dfコマンド<br>
・mkfsコマンド<br>
・e2labelコマンド<br>
・mount, unmountコマンド<br>
# 【次やること】
## ☆Linuxの基礎コマンドを理解する
・インプット教材「Linux標準教科書」(継続)
# 【感じたこと】
・現状下記のエラーが発生し解決できていないため、詳しく調べてみたいと思います。<br>
```
①fdisk -l：何も表示されない。
②ls -l /dev/sd*：対象の名称が付いているデバイスなし。
③manコマンドでlessコマンドを指定したが見れない。下記エラーが表示。
→No manual entry for less
④作成した〜ユーザに切り替えられない。
→#su - penguin
su: user penguin does not exist
⑤インストールしたが下記エラー発生。
→#nmcli device
Error: Could not create NMClient object: Could not connect: No such file or directory.
⑥下記エラーが発生。
#cat /etc/sysconfig/network-scripts/ifcfg-lo
cat: /etc/sysconfig/network-scripts/ifcfg-lo: No such file or directory
⑦下記エラーが発生。
#cat /etc/sysconfig/network-scripts/ifcfg-enp0s3
cat: /etc/sysconfig/network-scripts/ifcfg-enp0s3: No such file or directory
```
# 【学習時間】
・本日:2時間45分<br>
・月合計:11時11間分<br>
・累計:169時間14分
