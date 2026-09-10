---
layout: post
title: "裏話：rejectsの嵐(App Store)"
categories: 裏話 , App Store(iPhone)
#author:
#- buzyomi
#meta: "Springfield"
#modified_date: 2025-12-04
---

[link-3]: https://apps.apple.com/app/id6781913714
[link-6]: https://play.google.com/store/apps/details?id=com.spaceyomi.bestangle

## rejectsの嵐(App Store)

#### ベストアングル公開までの長い長い道のり

カメラアプリのベストアングルをApp Storeにリリースするまでの長い長い道のりについてです。
 
今まで、タイトルコール、タイトルコールProをリリースしたときも、１０年以上前にアプリをリリースしたときも、申請後、こんなにrejectsされたことはありませんでした。
 
凡ミスも多かったのですが、とりあえず、その一部始終を

### 1回目のreject

#### 利用規約(Terms of Use)（EULA）へのリンクがない


> The submission offers auto-renewable subscriptions but does not include a functional link to the Terms of Use (EULA) in the app metadata that appears on the app's App Store product page.<br>
If you are using the standard Apple Terms of Use (EULA), include a link to the Terms of Use in the App Description. If you are using a custom EULA, add it in App Store Connect.

要するにサブスクリプションを提供する場合？アプリのApp Store商品ページに利用規約（EULA）への有効なリンクが必要とのこと

Appleの標準的な利用規約（EULA）も使用できますが、独自のカスタムEULAでもOK

→アプリ用のサポートページにすでに、Privacy Policyのページはありますので、そこに利用規約も追加し、対応しました。


### 2回目のreject

#### アプリまたはメタデータに、サードパーティのプラットフォーム(Google Play)に関する情報がある

サブスクの説明文に「app Store または、Google Play」というような記述があったのがいけなかったようです。

→アプリ内、サポートページのPrivacy Policy、利用規約のページから「Google Play」の文言を削除しました。


#### カメラの「使用目的」が適当

> One or more purpose strings, also called usage description strings, in the app do not sufficiently explain the use of protected resources. Purpose strings must clearly and completely describe the app's use of data and, in most cases, provide an example of how the data will be used.

iOSでカメラアプリを開発する場合、Privacy - Camera Usage Descriptionを追加しないといけません。

アプリの最初の起動時、カメラ許可のダイアログに表示される文言です。

それをデバッグ時のまま、「カメラ使います」のままだったのです。

そりゃあ、却下されますよね。

→きちんと説明文を書きました。😅

### 3回目のreject

#### アプリの顔データについての質問

アプリが顔データをどのように利用しているかの質問です。

→書かれた質問の回答をApple Store Connectで返信しました。

> We need additional information about how the app uses face data. Face data is sensitive user information that must be handled properly to help protect the user's security and privacy.
Next Steps
Provide complete and detailed responses to the following questions:
- What face data does the app collect?
- Provide a complete and clear explanation of all planned use, sharing, retention, deletion, and storage practices for the collected face data.
- Will the face data be shared with any third parties? Where will this information be stored?
- How long will face data be retained? 
- Where in the privacy policy is the app's collection, use, disclosure, sharing, and retention of face data explained? Identify the specific sections in the privacy policy where this information is located.
- Quote the specific text from the privacy policy concerning face data.

#### サブスクのプロモーション画像が、適当

サブスクリプションには、月額プランと、年額プランがあるのですが、プロモーション画像を最初の開発時、適当に両方とも同じものを設定していました。

→きちんと月額プランと、年額プランを分けた画像を設定すれば良いのですが、現時点では、プロモーションは行なっていませんので、プロモーション画像は削除しました。


### 4回目のreject

ここまでは、自分のミスも多く、サブスクの実装も初めてだったので、仰る通りという感じ。

でも、次はバグ？？

#### アプリがスプラッシュ画面で止まるバグ

> Bug description: The app launched to a splash screen and was unresponsive.<br>
Review device details:
- Device type: iPad Air 11-inch (M4)
- OS version: iPadOS 26.6
- Internet Connection: Active

自分の環境では1回も発生したことはありません。

バグが再現しないということを言うにしても、同じ環境で確認しなければ。

今年発売のiPad Air 11-inch (M4)なんて持っていないし、そもそも、iPadを持っていない！

当然、シミュレータでテストするのですが、ここにまた、落とし穴。

iPadOS 26.6を実行するためには、Xcode 26.5が必要。

でも、自分の開発環境は、Xcode 26.2。

Xcode 26.5にアップデートするにはmacOSが古すぎる。

手動でXcode updatesから、ダウンロードしてインストール、GUIでは実行できないので、ターミナルから実行

> open /Applications/Xcode.app/Contents/MacOS/Xcode

Xcode updatesのXcode 26.5のリリースノートにはiPadOS 26.6に対応と書かれていましたが、実際に実行できるのはiPadOS 26.5

→起動処理を一部見直し、iPad Air 11-inch (M4) iPadOS 26.5でバグが再現しないことを確認し、再申請。

### 5回目のreject

#### アプリがスプラッシュ画面で止まるバグ

文言は違いますが、スクリーンショット画像を見ると、スプラッシュ画面で止まるバグです。

> Bug description: We were unable to access the app because the app loaded indefinitely on launch.<br>
Review device details:
- Device type: iPhone 17 Pro Max and iPad Air 11-inch (M3)
- OS version: iOS 26.6 and iPadOS 26.6.1
- Internet Connection: Active

今回は、デバイスにiPhone 17 Pro Maxが。

Pro Maxは持っていませんが、iPhone 17、iPhone 11は持っていますのでそちらでテスト。

レビュー時の状態では、バグは発生しませんが、デバイスがオフラインの場合は、スプラッシュ画面で止まるということに気づきました。

オフラインでもスプラッシュ画面から抜けてホーム画面に行き、アプリが動作するようにプログラムを修正しました。

→以下のデバイスでバグが発生しないことを確認し、再申請
> Physical Devices  
 iPhone 17, iOS 26.6.1  
 iPhone 11, iOS 26.6.1  
Simulators  
iPhone 17 Pro Max, iOS 26.5  
iPad Air 11-inch (M3), iPadOS 26.5

### 6回目の申請→2026/09/09 App Store公開

2026/09/09 App Store公開🎊

8/20(木)に1回目申請してから、ちょうど3週間、長い長い道のりでした。😮‍💨<br>

* * *

### 参考リンク


#### [Xcode Update](https://developer.apple.com/documentation/updates/xcode)

