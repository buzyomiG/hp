---
layout: post
title: "裏話：(iphone)Ver.1.0.1 Release"
categories: iPhone開発
#modified_date: 2025-04-29
---

[link-3]: https://apple.co/4jAiQKn

## Ver.1.0.1 Release

### サポートURLのみ変更

リリース理由は「サポートURLのみ変更」です。

First Release後、Google Admobを有効にしようとしました。

app-ads.txtはサポートページのルートに設定済みです。

> **ステップ 4: AdMob による app-ads.txt ファイルのクロールと検証が終わるのを待つ**
> 
> AdMob による app-ads.txt ファイルのクロールと検証が終わるまでには、最大 24 時間かかることがあります。AdMob では定期的に最新のファイルを確認しますが、早めの確認が必要な場合には AdMob にアプリのクロールをリクエストすることもできます。

途中で何度も「クロールをリクエスト」しても、24 時間待ってもステータスが進みません。

サポートURLは記載していましたが、URLがお問い合わせフォーム（Google for m）のURLになっていることに気づきました。

サポートURLを問い合わせフォームを呼び出すサポートページに修正しました。

アプリには、何も手を入れず、Apple storeの記載変更のみなのですが、プログラムを再度、アップロードしなければなりません。

バージョンのみ変更して、ビルドし直してアップロードしました。

だが、Apple storeに公開後、24 時間待っても一向にステータスが進みません。

ー＞[「裏話：(iphone)Ver.1.0.2 Release」]({% post_url 2025-04-28-title_call(iphone)_1.0.2_ura03 %})に続く。

### 参考リンク

* * *

[アプリの app-ads.txt ファイルを設定する](https://support.google.com/admob/answer/9363762?hl=ja "アプリの app-ads.txt ファイルを設定する")
