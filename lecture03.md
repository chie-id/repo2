# 第３回課題:Webアプリケーションを起動する

## 概要
### ●cloud9に『APサーバー』と『DBサーバー』をインストールする
### ●サンプルアプリケーション(Roby on Rails)を起動してブラウザで表示させる

## 実施内容
### 1.cloud9に課題用の環境を作成する
### 2.GitHub上のサンプルアプリケーションをcloud9にクローンする
- コマンド：git clone "code"
  
### 3.cloud9に『Ruby:ver3.1.2（サンプルアプリケーションでの使用ver）』をインストールする
- コマンド：rvm install 3.1.2
- 補足①：verはライブラリのインストールに関係してくる
- 補足②：verが古い場合はアップグレードする

### 4.cloud9に『MySQL（DBサーバー）』をインストールしてセットアップする
- 操作手順は↓を参照する
　https://github.com/MasatoshiMizumoto/raisetech_documents/blob/main/aws/docs/install_mysql_on_cloud9_amazon_linux_2.md

### 5.サンプルアプリケーション内の設定ファイルを編集・保存する（例）
- 『database.yml.sampleファイル』をコピーして『database.ymlファイル』を作成する
- コマンド：cp config/database.yml.sample cp config/database.yml
- 『database.ymlファイル』にパスワードを記入、ソケットのパスを書き換える（test/development両方とも）

### 6.『RubyGems』から『bundlerとライブラリ』をインストールする
- コマンド：bunble install など
- 補足：依存関係にあるライブラリが一括でインストールされる

### 7.『yarn』と『npm』がインストールされているか調べる→『yarn』をインストールする
- コマンド：npm install --global yarn 


### 8.環境構築するためのコマンドを実行する（今回の実行環境）
- コマンド：bin/setup

### 9.アプリケーションサーバーの起動するためのコマンドを実行する（今回の実行環境）

- ローカル環境　→　コマンド：bin/dev
- Cloud9 →　コマンド：bin/cloud9_dev

### 10.ブラウザでWebアプリケーションを表示して動作確認をする

- Cloud9のメニューバー：Preview→Preview Running Application→Browserを押下

### 11.RailsのBlocked hostセキュリティを解消する
- Webアプリケーション上に表示されている↓をコピーする
- config.hosts << "542e434945414549915bf29e23ee129a.vfs.cloud9.ap-northeast-1.amazonaws.com"

- 『development.rbファイル』のendの上の行にペーストする→保存する

## 学び
### APサーバー
- プログラムで作られたアプリケーションを実行するために必要なサーバー
- ブラウザとの連携してWebに関する処理も行うことができる（内部にWebサーバーを持っているため）
- Rubyの場合はPuma(Railsに組み込まれている)

### フレームワーク
- アプリケーションを開発するための機能がデフォルトで揃っているもの
- Rubyの場合はRoby on Rails

### ライブラリ
- 予め書き込まれたプロクラムの集合体
- 繰り返し使用できる
- 作業を簡略化するために使用する
- 便利機能の集まり
- Ruby(Rails)の場合はGem

### 構成管理ツール
- 言語ごとにコマンドが決められている
- コマンド実行するとインターネット上のリポリトジからローカルに情報をダウンロードすることができる
-  Rubyの場合はbunbler

### bunbler
- gemの依存関係とバージョンを管理するためのツール
- RubyGems（Rubyのパッケージ管理システム）から情報をインストールする

### SQL
- DBからデータを取り出したり、追加したりする操作を指示するための言語

### yarn/npm
- nodeのパッケージを管理するためのツール

