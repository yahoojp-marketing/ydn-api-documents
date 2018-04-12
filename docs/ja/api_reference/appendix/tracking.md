# トラッキングパラメータ
YDN APIでは、ユーザーがどの種類の広告をクリックしてサイトを訪れたかの情報を得るために、トラッキングパラメータを利用できます。<br>
クリックされた広告の詳細を知ることで広告の効果を確認でき、よりよい広告の出力につなげることが可能です。<br>
YDN APIで利用できるトラッキングパラメータは、以下のとおりです。
<br>

パラメータ | 概要 | URLフォーマット   
----------- | ----------------- | ---------------- 
creative | 広告IDです。 | http://www.example.com/?creative={creative} 
media | メディアIDです。|http://www.example.com/?media={media}
campaignid | キャンペーンIDです。| http://www.example.com/?campaignid={campaignid}
adgroupid | 広告グループIDです。| http://www.example.com/?adgroupid={adgroupid}
device | デバイスの種類です。<br>以下の内容が返却されます。<br>・DESKTOP<br>・WAP_MOBILE<br>・SMARTPHONE<br>・TABLET<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?device={device}
os | OSの種類です。<br>以下の内容が返却されます。<br>・IOS<br>・ANDROID<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?os={os}
isApp | iOSアプリ、Androidアプリに配信されたかを表示します。<br>・iOSアプリ、Androidアプリの場合：true<br>・上記以外の場合：false | http://www.example.com/?isApp={isApp}
ifaSha1 | IFA（広告識別子）のハッシュ値（sha1）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br><br>※インタレストマッチでは指定できません<br>（ターゲティングとインフィード広告では指定できます）。<br>※標準キャンペーンでは指定できません。<br>※アプリキャンペーンの場合でも、YDNと連携済みの広告効果測定ツール（*）以外との組み合わせでは指定できません。|http://www.example.com/?ifaSha1={ifaSha1}
ifaMd5 | IFA（広告識別子）のハッシュ値（md5）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br><br>※インタレストマッチでは指定できません<br>（ターゲティングとインフィード広告では指定できます）。<br>※標準キャンペーンでは指定できません。<br>※アプリキャンペーンの場合でも、YDNと連携済みの広告効果測定ツール（*）以外との組み合わせでは指定できません。|http://www.example.com/?ifaMd5={ifaMd5}
ifa | IFA（広告識別子）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br><br>※インタレストマッチでは指定できません<br>（ターゲティングとインフィード広告では指定できます）。<br>※標準キャンペーンでは指定できません。<br>※アプリキャンペーンの場合でも、YDNと連携済みの広告効果測定ツール（*）以外との組み合わせでは指定できません。|http://www.example.com/?ifa={ifa}

（*）YDNと連携済みの広告効果測定ツールは[ヘルプページ](https://help.marketing.yahoo.co.jp/ja/?p=12897)をご確認ください。
