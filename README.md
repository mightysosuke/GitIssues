# Git Flow の擬似体験

## 参考資料

https://qiita.com/fukubaka0825/items/c7710b4e87d478c8ba3b

## Git Flow について

Git には、開発しやすくするためのモデルがあります。

そのうちの一つが Git Flow です。

[参考サイト](https://www.sejuku.net/blog/74224)

今回の擬似体験では、master、develop、feature ブランチの 3 つを使います。

`master ブランチ`

master ブランチには常に安定して動く、リリースした後のコードを置いておきます。

git flow ではこのブランチに直接コミットをすることはないので気をつけましょう。

`develop ブランチ`

develop ブランチでは次のバージョンをリリースするために、最新の開発履歴を残しておきます。

言わば git flow を使った開発の中心となるブランチで、常に最新の変更が加えられているブランチになります。

`feature ブランチ`

feature ブランチは、develop ブランチから分岐しているブランチです。

この feature ブランチでは新しく追加する機能の開発や、簡単なバグの修正を行うことが出来ます。

feature ブランチを変更する機能の数だけ切って、その中で個々の機能についての変更を行っていきます。

このブランチで作業し終わったあとはこのブランチは削除するのが一般的です。

## 環境構築

- VSCode をインストールする

  https://code.visualstudio.com/

- XCode をインストールする

```zsh
$ xcode-select --install
```

- Homebrew を入れる

  https://brew.sh/index_ja.html?_fsi=JrbahF8d

```zsh
# git-flowの導入
$ brew install git-flow

# 動作確認
$ git flow
```

## プロジェクトの準備

**好きな場所に batty_coffee_stand ディレクトリを作成**

[カリキュラムのページ](https://tech-boost.jp/common/books/344)

```zsh
$ mkdir batty_coffee_stand
$ cd batty_coffee_stand
$ touch index.html
$ mkdir css

# 前のコマンドの引数のディレクトリに移動
$ cd $_
$ touch style.css

# 一つ上のディレクトリに移動
$ cd ..
$ mkdir image

```

## Git と GitHub の準備

環境は、普段使っている cloud9 の環境またはローカルの環境で

- リモートリポジトリの作成

[GitHub のページ](https://github.com/)

- ローカルリポジトリの作成

```zsh
$ git init
$ git remote add origin https://github.com/アカウント名/batty_coffee_stand.git
$ git add .
$ git commit -m "first commit"
$ git push origin master
```

```zsh
$ git flow init -d
$ git push origin develop
```

## Issue 管理をしてみる

- これらを順番に Issue に書く

```zsh
# Title
HTMLとCSSのベース

# comment
ベースの作成をする
```

```
ヘッダーを実装する

タイトル部分の実装
ナビゲーション部分の実装
```

```
コンテンツ部分を実装する

共通要素の取り出し
2カラムレイアウト
Informationの実装
Staffの実装
Accessの実装
```

```
フッターを実装する

フッターを実装して完成
```

## ブランチを切る(Git Flow)

```zsh
$ git branch -a
$ git flow feature start '#1'
$ git branch
```

## ソースコードを修正する

- Issue に合わせてソースコードを修正

## プルリクをしてマージする

```zsh
$ git add .
$ git commit -m "HTMLとCSSのベース #1"
$ git push origin 'feature/#1'
```

develop <- feature1 へのマージ

## ブランチを削除する

```zsh
$ git checkout develop
$ git pull origin develop
$ git branch -d 'feature/#1'
```

## 残りの Issue を片付ける

## master へのマージをしてみる
