---
layout: post
title: "裏話：(android)リリースの保留"
categories: android開発
#modified_date: 2025-04-28
---

[link-3]: https://apple.co/4jAiQKn

## First Release前

### android版TitleCallについて

TitleCallの開発はFlutterで進めており、iPhoneのリリース時、android版もほぼ完成していました。

当初は、android版を先にリリースしようとしていたのですが、大人の事情でiPhoneのリリースを先にしました。

### 大人の事情とは

アプリをリリースする際は、iPhone、androidとも開発者としての登録が必要です。

・Apple Developer Program $99 (14,850円） ※毎年

・Google Play Developer Program $25 (3,750円） ※初回の1回限り

とりあえず、Google Play Developer Programに登録しようとしたところ、以下の記事が。

> **（個人アカウントのみ）ステップ 6: テスト要件とデバイス確認要件を満たす**
> 
> 2023 年 11 月 13 日以降に個人アカウントを作成したデベロッパーが Google Play でアプリを公開するには、特定のテスト要件を満たす必要があります

特定のテスト要件とは

> 20 人以上のテスターが 14 日以上連続でオプトインしてアプリのクローズド テストを実施する必要があります。

法人にはこんなテストを課さないになぜ個人に。

個人には無理でしょ。

で、検索したら、みなさま怒ってましたね。

対応としては、法人（個人事業主）になるか、コミュニティとかで他の人に協力していただいて、個人で行くか。

どちらにしても、「本名と住所の公開」をする必要があります。

名前は同姓同名もあるでしょうが、さすがに個人の住所は公開できません。

android版リリースは保留しました。

友人達には、android版は８月ごろリリースしたいと言っていますが、正直厳しいかも。

### 参考リンク

* * *

[Google Play Console を使ってみる](https://support.google.com/googleplay/android-developer/answer/6112435?hl=ja#zippy=%2C個人アカウントのみステップ-テスト要件とデバイス確認要件を満たす "Google Play Console を使ってみる")

[新しい個人用デベロッパー アカウント向けのアプリテスト要件](https://support.google.com/googleplay/android-developer/answer/14151465?hl=ja "新しい個人用デベロッパー アカウント向けのアプリテスト要件")

[個人開発アプリは、iOSとAndroidのどちらからリリースしたらいい？](https://note.com/yukio_app/n/na77caac38175 "個人開発アプリは、iOSとAndroidのどちらからリリースしたらいい？")


[Google Playのアカウントは組織にするしかない](https://teammoko.jp/googleplay_account_hard "Google Playのアカウントは組織にするしかない")

[Android開発最大の壁「クローズドテスト」](https://zenn.dev/android_tester/articles/e6559bb953d317 "Android開発最大の壁「クローズドテスト」")
