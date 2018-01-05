+++
title = "Skycoin BBS v5.0 リリースのお知らせ"
tags = [
    "Development",
    "BBS",
    "CXO",
]
bounty = 1
date = "2017-12-18"
categories = [
    "Development Updates",
]
+++

Skycoin BBS v5.0 は数多くの変更が施されリリースされました！

## 簡易クライアント(thin-client)に関する変更

今回最大の変更は、簡易クライアント(thin-client)の導入です。ノードを設定せずにSkycoin BBSにアクセスできるようになりました！ [bbs.skycoin.net](http://bbs.skycoin.net)へアクセスしよう。

以前のバージョンでは、ローカル環境でのみWebユーザーインターフェイスを介してコンテンツにアクセスしたり、コンテンツを送信したりすることが可能でした。このWebインターフェイス(および呼出API)はノード自体を直接制御し、ノード(またはサーバー側)に格納された秘密キーでコンテンツに署名するため、公開することは適切ではありません。

したがって、簡易クライアント(thin-client)の導入の課題は、ユーザ管理および提出のコンテンツに署名する処理をクライアント側に処理させることが必要です。これにはコンテンツ提出エンドポイント(エンドポイント)と、フロントエンドへの大幅な変更が必要となります。

新しいコンテンツの提出処理の詳細は、BBS Wikiをご確認ください: [github.com/skycoin/bbs/wiki/Content-Submission-Process](https://github.com/skycoin/bbs/wiki/Content-Submission-Process)

現在、フロントエンドのロードは非常に遅いです。これは[GopherJS](https://github.com/gopherjs)を使用してシードと公開鍵/秘密鍵の生成を処理し、データの署名と検証を原因です。今後のリリースでネイティブJavaScriptライブラリを使用してパフォーマンスを向上予定です。

## コマンドラインに関する変更

公開されている簡易クライアント(thin-client)の導入後、管理上の制御を処理するAPIエンドポイントを削除し、対話型のコマンドラインインターフェイスを導入しました。

この変更に関する詳細はこちらに記載しています: [github.com/skycoin/bbs/tree/master/cmd/bbscli](https://github.com/skycoin/bbs/tree/master/cmd/bbscli)

## その他の変更

* インポート/エクスポートの改善（BBS v4.xのインポート/エクスポートと互換性なし）
* Skycoin Messengerとのリモート提出と相互作用のためのコードとパフォーマンスの改善及び簡素化を行いました。また最新のメッセンジャーを使用するように更新されました。
* ファイル管理のパフォーマンスが向上しました。
* 無効なCXOルーツの処理が改善されました。
* 切断処理が改善されました。

## ダウンロード

BBS(掲示板)をダウンロード: [github.com/skycoin/bbs/releases](https://github.com/skycoin/bbs/releases) (ソースコード同封)

こちらからもアクセスできます [bbs.skycoin.net](http://bbs.skycoin.net)

## ドキュメント

Wikiを新設しました！ [github.com/skycoin/bbs/wiki](https://github.com/skycoin/bbs/wiki)

ドキュメントはまだまだ未完成です。ご了承ください。

## コミュニティ

Telegram チャンネル: [@skycoinbbs](https://t.me/skycoinbbs)
