# Shogi.js (Ver. 2.0) [![Build Status](https://travis-ci.org/na2hiro/Shogi.js.svg?branch=master)](https://travis-ci.org/na2hiro/Shogi.js)
将棋の盤駒をモデルとするシンプルなJavaScriptライブラリ．TypeScript．

## インストール

```
npm install shogi.js
```

## 概要
* 最低限の将棋の法則に従って操作ができる．
	* 局面を平手に並べることができる．
	* 駒を移動(move)すると，移動先の駒を取れる．
	* 駒を打つ(drop)ことができる．
	* 動作を戻すことができる．
* モード(editMode)
	* 通常(false)
		* 手番，動きを守っているかどうかをチェック
		* 二歩検査
		* 手番を管理
	* 編集(true): 
		* 手番や動きをチェックしない
		* 手番を変更する
		* 盤上の駒を駒台に載せる
		* 盤上の駒を裏返し・反転させる

通常モードは棋譜再生および対局を，編集モードは盤面編集をモデル化するものである．

## クラス概要
各クラスのメソッドの概要についてはコメントを確認されたい．
また，`test`ディレクトリ以下のテストで実際の挙動を確認されたい．

* class Shogi
	* 将棋盤を管理するクラス
* enum Color
	* Black=0, White=1
* class Piece
	* 駒を表すクラス

## TODO
* 駒箱

## 開発

### 準備

```
$ npm install

```

上記コマンドを実行することで開発に必要なパッケージをインストールできます．

* TypeScript 2.0
* Webpack 3 (バンドルツール)
* Browserify (JSバンドルツール)
* Jest (テストフレームワーク，カバレッジ計測)
* TSLint (Linter)

### コマンド


```
$ npm run build
$ npm run build:watch
```

ビルドが走ります．`build:watch`の場合，変更されるたびにビルドが走ります．

```
$ npm run test:watch
```

コンソールでテスト結果が表示されます．コードの変更が保存されるたびに必要なテストが再実行されるため，実装が既存の有効なテストを壊してないか簡単に確認できます．

```
$ npm run test
```

全てのテストが走るとともにカバレッジレポートが表示されます．`coverage/lcov-report/index.html`では，行ごとのカバレッジを確認できます．追加されたコードのブランチカバレッジが100%になるようにしてください．push時にチェックされ満たしていなければ却下されるはずです．

```
$ npm run lint
```

コードの品質が検査されます．エラーがあればそれに従い直してください．push前にもチェックされます．

```
$ npm run lint:fix
```

自動的に修正可能な問題(インデント等)を直してくれます．

```
$ npm run docs
```

`docs/` 以下にドキュメントを生成します．

## license

MIT License (see LICENSE.txt)
