---
layout: post
title: "Title Call Pro(Android)First Release"
categories: title_call_pro(Android)
#author:
#- buzyomi
#meta: "Springfield"
#modified_date: 2025-04-16
---

[link-3]: https://apple.co/4jAiQKn
[link-6]: https://play.google.com/store/apps/details?id=com.spaceyomi.titlecallprof

## Title Call Pro aprication(Android) First Release

### [![To Store](/assets/title_call_pro/AppIcon-pro-83.5x83.5@2x.png)][link-6]

#### Until Release

Title Call Pro has been released.

[The process of incorporating as a legal entity]( /houjinnka) for Google Play Console Developers and the Apple Developer Program has been completed.

Development of the Pro version had been underway since the middle of developing the free version.

【Differences from Free Version】

・No ads displayed.

・Supports 60 languages for text-to-speech, with smoother speech compared to the free version.

【Supported Languages】

af-ZA, am-ET, ar-XA, bg-BG, bn-IN, ca-ES, cmn-CN, cmn-TW, cs-CZ, da-DK, de-DE, el-GR, en-AU, en-GB, en-IN, en-US, es-ES, es-US, et-EE, eu-ES, fi-FI, fil-PH, fr-CA, fr-FR, gl-ES, gu-IN, he-IL, hi-IN, hu-HU, id-ID, is-IS, it-IT, ja-JP, kn-IN, ko-KR, lt-LT, lv-LV, ml-IN, mr-IN, ms-MY, nb-NO, nl-BE, nl-NL, pa-IN, pl-PL, pt-BR, pt-PT, ro-RO, ru-RU, sk-SK, sr-RS, sv-SE, ta-IN, te-IN, th-TH, tr-TR, uk-UA, ur-IN, vi-VN, yue-HK

【Supported Voice Types for Text-to-Speech】

Standard, Wavenet, Chirp3-HD, Chirp-HD, Casual, News, Neural2

Those who are observant may have noticed that we've switched the text-to-speech engine to [Google Cloud Text-to-Speech](https://docs.cloud.google.com/text-to-speech/docs "Google Cloud Text-to-Speech").

The above features were mostly developed before the incorporation process was completed, but I got bogged down in bug fixes and adjustments to the processing for counting the number of characters read aloud.

Google Cloud Text-to-Speech charges monthly based on usage.

While Google can count the total number of characters, it doesn't provide per-user values.

>  Text-to-Speech is priced based on the number of characters sent to the service to be synthesized into audio each month. You must enable billing to use Text-to-Speech, and will be automatically charged if your usage exceeds the number of free characters allowed per month. For information about how to keep track of your character totals, see Monitoring API usage. Price is calculated per character.

User-specific count tracking is required.

During debugging, the character count for read-aloud text was stored locally on the device.

We've changed this to use Firestore and Firebase Anonymous Auth.

The system now prevents audio playback for the current month once the read-aloud character count exceeds a certain threshold.

In the future, we may consider enabling reading through purchases like additional content, but for now, it's simply a restriction.

And finally, we've managed to get it released.

The iPhone version finished first and was released to the App Store, but it's currently stuck at the tax form stage.

We're currently in contact with Apple. While the incorporation process is complete, the paid app contract is on hold.

Meanwhile, the Android release is complete. 🎊

### Reference Links

* * *

[Google Cloud Text-to-Speech](https://docs.cloud.google.com/text-to-speech/docs "Google Cloud Text-to-Speech")
