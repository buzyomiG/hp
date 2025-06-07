---
layout: post
title: "裏話：(iphone)Ver.2.0.0 Release 01"
categories: iPhone開発
#modified_date: 2025-04-26
---

[link-3]: https://apple.co/4jAiQKn

## Ver.2.0.0 Release　裏話１

### Ver.2.0.0

#### ・銀行等パスワードを要するサイトに対応しました。

#### ・インターフェイスを変更しました。


#### パスワードを要するサイトには未対応

First リリース時、直前にパスワードを要するサイトにログインできないことに気がつきましたが、とりあえず、リリース。

銀行にログインできないくらいならと思い、App Storeのアプリページに注意書を書きました。

しか〜し、GoogleにもAmazonにも楽天にもログインできない。

いくらなんでも不便すぎる。

アプリをダウンロードしてくださった皆様、申し訳ありませんでした。


多分、日本ではほとんどが知り合いですが、わずかですが海外でもダウンロードしていただいています。

少しずつですが、進化していきますので、よろしくお願いします。🙇‍♂️
　
#### パスワードを要するサイトに対応

パスワード要するサイトに対応することにしました。

今更ですが、開発はflutterで行っています。

Ver.1.x.x時、webviewのパッケージは、「webview_flutter」を使用していました。

WebView ログインは基本 NG 、RFC 8252 で非推奨となっているそうです。

結局のところ、OSネイティブ ASWebAuthenticationSession／Chrome Custom Tabs を使用するのが良いようです。

結果、以下が見つかりました。

・flutter_appauth

・flutter_custom_tabs

しかし、iOS と、Androidで異なるし、カスタマイズもしにくく、中々に面倒くさそう。

[FlutterでAndroidでのAuth0のログイン・ログアウトを実装してみた](https://dev.classmethod.jp/articles/flutter-android-auth0/ "FlutterでAndroidでのAuth0のログイン・ログアウトを実装してみた")

[WebView×OAuth2実践ガイド🚀—Flutter + AppAuthで安全ログインを作る](https://zenn.dev/koshiosaki/articles/9befab66d215b3 "WebView×OAuth2実践ガイド🚀—Flutter + AppAuthで安全ログインを作る")

[FlutterのWebView プラグインどれ使えば？](https://speakerdeck.com/espresso3389/flutterfalsewebview-hurakuintoreshi-eha?slide=10 "FlutterのWebView プラグインどれ使えば？")

しばらく悩んだのですが、アプリ内でログイン情報が必要なわけではないので、別角度から考えることにしました。

結果、 「flutter_inappwebview」 を使用することにしました。

開発当初は、「flutter_inappwebview」を使用していたのですが、このパッケージはadmobと統合できないという記事を読んで、途中から、「webview_flutter」に変更していました。

ここに落とし穴が。

別にWebview上に admob を出すわけではなかったので、元々の「flutter_inappwebview」で良かったのです。

プログラムの構造もWebvieを切り離す形に変更し、それに伴って、アプリのユーザーインターフェイスも一新しました。

### 参考リンク

* * *

[flutter_appauth 9.0.1](https://pub.dev/packages/flutter_appauth/example "flutter_appauth 9.0.1")

[flutter_custom_tabs 2.4.0](https://pub.dev/packages/flutter_custom_tabs/example "flutter_custom_tabs 2.4.0")

[Android カスタムタブの概要](https://developer.chrome.com/docs/android/custom-tabs?hl=ja "Android カスタムタブの概要")
