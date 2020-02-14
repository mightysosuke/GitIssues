# Git Flow の擬似体験

## 参考資料

https://qiita.com/fukubaka0825/items/c7710b4e87d478c8ba3b

## Git Flow について

## プロジェクトの準備

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

## git の準備

環境は、普段使っている cloud9 の環境またはローカルの環境で

```zsh
$ git init
$ git add .
$ git commit -m "first commit"
$ git remote add origin https://github.com/アカウント名/gitIssue.git
$ git push -u origin master
```

## ブランチを切ってみる(dev)

```zsh
# developブランチを切る
$ git branch develop

# developブランチへ移動
$ git checkout develop

# masterがdevelopに変わったことを確認

```

- develop ブランチの役割について説明

## Issue 管理をしてみる

- これらを順番に Issue に書く

```zsh
# Title
HTMLとCSSのベース

# コメント
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

## Issue に合わせてブランチを切る

```zsh
# developブランチからfeatureブランチを切る
$ git checkout - b feature1
```

## ソースコードを修正する

- Issue に合わせてソースコードを修正

## プルリクをしてマージする

```zsh
$ git add .
$ git commit -m "HTMLとCSSのベース #1"
$ git push origin feature1
```

develop <- feature1 へのマージ

## ブランチを削除する

```zsh
$ git checkout develop
$ git pull origin develop
$ git branch -d feature1
```

## 残りの Issue を片付ける

## master へのマージをしてみる
