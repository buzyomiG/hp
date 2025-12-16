---
layout: post
title: "裏話：TitleCall Pro(Android)初リリース"
categories: title_call_pro(Android)
#author:
#- buzyomi
#meta: "Springfield"
#modified_date: 2025-12-04
---

[link-3]: https://apple.co/4jAiQKn
[link-6]: https://play.google.com/store/apps/details?id=com.spaceyomi.titlecallprof

## Title Call Pro アプリ(Android)初リリース

### [![To Store](/assets/title_call_pro/AppIcon-pro-83.5x83.5@2x.png)][link-6]

#### リリースまで

Title Call Proリリースしました。

Google Play Console デベロッパーとApple Developer Programの[法人化への道のり]( /houjinnka)が終了しました。

無料版の開発の途中から、Pro版の開発は進めていました。

【無料版との違い】

・広告を表示しません。

・読み上げ可能な言語は、60か国語で、無料版に比べ、滑らかです。

【読み上げ可能言語】

af-ZA, am-ET, ar-XA, bg-BG, bn-IN, ca-ES, cmn-CN, cmn-TW, cs-CZ, da-DK, de-DE, el-GR, en-AU, en-GB, en-IN, en-US, es-ES, es-US, et-EE, eu-ES, fi-FI, fil-PH, fr-CA, fr-FR, gl-ES, gu-IN, he-IL, hi-IN, hu-HU, id-ID, is-IS, it-IT, ja-JP, kn-IN, ko-KR, lt-LT, lv-LV, ml-IN, mr-IN, ms-MY, nb-NO, nl-BE, nl-NL, pa-IN, pl-PL, pt-BR, pt-PT, ro-RO,  ru-RU, sk-SK, sr-RS, sv-SE, ta-IN, te-IN, th-TH, tr-TR, uk-UA, ur-IN, vi-VN, yue-HK

【読み上げ可能Voice種別】

Standard, Wavenet, Chirp3-HD, Chirp-HD, Casual, News, Neural2


察しの良い方は、お分かりでしょうが、読み上げエンジンを[Google Cloud Text-to-Speech](https://docs.cloud.google.com/text-to-speech/docs?hl=ja "Google Cloud Text-to-Speech")に変更しています。

上記機能は、法人化の作業が終了するまでに、ほぼほぼ開発済みでしたが、バグ修正と、読み上げ文字数のカウントに関する処理の修正に手間取ってしまいました。

Google Cloud Text-to-Speechは使用量によって月毎に料金が発生します。

合計文字数はGoogleでカウントできるようですが、ユーザーごとの値は分かりません。

> Text-to-Speech の料金は、音声への合成のためにサービスに送信された文字数に基づいて、月単位で請求されます。<br>
> Text-to-Speech を使用するには課金を有効にする必要があります。<br>
>　使用量が 1 か月間に無料で使用できる文字数を超えると、自動的に課金されます。<br>
>　合計文字数を追跡する方法については、API 使用状況のモニタリングをご覧ください。<br>
>　料金は文字ごとに計算されます。<br>

ユーザーごとのカウント数が必要です。

デバッグ時は、読み上げ文字数のカウントは端末に文字数を保存する仕様でした。

それをFirestoreと、Firebase Anonymous Authを使用する方法に変更しました。

読み上げた文字数が一定数を超えたら、当月中は音声再生を行わない仕様です。

将来的には、追加コンテンツなどの購入で読み上げを可能にする考えもありますが、現時点では単に制限するだけです。

で、やっとリリースにこぎつけました。

iPhoneの方が早く完成し、Apple Storeにリリースしましたが、納税フォームのところで止まっています。

現在はAppleに問い合わせ中で、法人化は終了していますが、有料アプリ契約保留中の状態です。

その間にAndroidはリリース完了です。🎊


### 参考リンク

* * *

[Google Cloud Text-to-Speech](https://docs.cloud.google.com/text-to-speech/docs?hl=ja "Google Cloud Text-to-Speech")
