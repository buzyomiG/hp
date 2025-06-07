---
layout: post
title: "裏話：(iphone)Ver.2.0.0 Release 02"
categories: iPhone開発
#modified_date: 2025-04-26
---

[link-3]: https://apple.co/4jAiQKn

## Ver.2.0.0 Release　裏話2

### admob広告の制限

開発途中で、またもadmob広告の制限が発生しました。

理由は自身の端末で本番用のテストをしていると、自作自演で広告を稼いでいると判断され、ポリシー違反になったためと思われます。

開発に使うデバイス(以降:テストデバイス)をAdmobに登録すれば良いのです。

大丈夫と高を括って、放置していましたが、制限が発生が頻発するようでは、対応するしかありません。

テストデバイスを設定するためには、　広告 ID または IDFA を確認しなければなりません。

androidの広告IDは確認しやすいのですが、iOSは面倒です。

> iOS
> 
> 現在、Apple の iOS デバイスでは IDFA がデフォルトで表示されません。ただし、サードパーティ製アプリを使って取得することができます。広告 ID を取得可能なアプリを App Store で確認するか、プログラムによって IDFA をご確認ください。

そこで、advertising_id というパッケージを入れ、プログラムを作成したのですが、IDFAは、00000000-0000-0000-0000-000000000000

プログラムが悪いのかと思い、App Storeにリリースされている以下のアプリを入れたのですが、両方とも00000000-0000……

・My Device ID by AppsFlyer

・adjust Insights

さらに調べた結果、端末の設定で「アプリからのトラッキング要求」が許可されていないと、上記表示となることが分かりました。

「アプリからのトラッキング要求」を許可し、無事、IDFAが表示されました。

やっと、admobに設定しました。

設定できたのは、Ver.2.0.0リリース後ですが。

### 参考リンク

* * *

[テストデバイスを設定する](https://support.google.com/admob/answer/9691433?hl=ja "テストデバイスを設定する")

[広告IDをAdmobにコピペできるアプリをつくりました！](https://blog.redridge.net/article/the-app-that-can-copy-the-advertising-id/ "広告IDをAdmobにコピペできるアプリをつくりました！")

[端末の広告ID(IDFA, ADID)はどうすれば取得できますか？](https://docs.repro.io/ja/faq/app/sdk/1.html#id-idfa-adid "端末の広告ID(IDFA, ADID)はどうすれば取得できますか？")

[【iOS14を入れてみた！】モバイルアドフラウドの影響は?iOS14のIDFAオプトイン後を予測。](https://jp.spideraf.com/articles/impact-on-mobile-adfraud "【iOS14を入れてみた！】モバイルアドフラウドの影響は?iOS14のIDFAオプトイン後を予測。")
