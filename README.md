# O_o
## 必要環境
* gcloud CLI

## ファイルの説明
### deploy_gce.sh
* ローカル環境から実行するとGCEのインスタンスを作成しそのまま起動できる
  * インスタンス作成時の実行コマンド：`sudo docker run -e TOKEN=$TOKEN --restart=always -d $DEPLOY_CONTAINER`
* 既に同名のインスタンスが存在した場合、削除して作り直す
* GCEの永久無料枠(e2-micro)を利用

### main.py
* discord botの本体（公式のサンプル動かしてるだけX_x）

### dockerfile
* ※自身のアプリをコンテナ化するためのものではなく、GCE上でこのアプリのコードをcloneして、その場で実行するためのコンテナ。なんでこのアプリ固有の情報はURLとかその辺のみ
* 既にビルドしたイメージをdockerhubへ公開しており、GCEではdockerhubの公開イメージを用いる
* 変更なければdocker build等触らないでよい

### requirements.txt
* pythonのrequirements.txt

## 開発のやり方メモ
以下でデプロイまでできる
1. ローカルでコード修正
2. githubにコミット
3. `$ ./deploy_gce.sh`でデプロイ（公開）
