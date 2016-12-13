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
targetlist | ターゲットリストIDです。|http://www.example.com/?targetlist={targetlist}
device | デバイスの種類です。<br>以下の内容が返されます。<br>・DESKTOP<br>・WAP_MOBILE<br>・SMARTPHONE<br>・TABLET<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?device={device}
os | OSの種類です。<br>以下の内容が返されます。<br>・IOS<br>・ANDROID<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?os={os}
isApp | iOSアプリ、Androidアプリに配信されたかを表示します。<br>・iOSアプリ、Androidアプリの場合：true<br>・上記以外の場合：false | http://www.example.com/?isApp={isApp}
placementUrl|配信先サイトのURLを表示します。<br>表示できるURLは250桁までで、250桁を超過する部分はカットされます。<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。<br>※palcementUrlはUTF-8でURLエンコードされます。|http://www.example.com/?placementUrl={placementUrl}
interestCategory | インタレストカテゴリーです。<br>インタレストカテゴリーコードの形式は、「TC-IC-××××××××」（DictionaryServiceで照会するコード体系）です。<br>1サイトで、トラッキング結果が3カテゴリーになります。<br>「｜」区切りでコードを分割します。<br>例：「TC-IC-××××××××｜TC-IC-××××××××｜TC-IC-××××××××」 | http://www.example.com/?interestCategory={interestCategory}
siteCategory | サイトカテゴリーです。<br>サイトカテゴリーコードの形式は、「TC-SC-××××××××」（DictionaryServiceで照会するコード体系）です。|http://www.example.com/?siteCategory={siteCategory}
age | オーディエンスの年齢です。<br>※識別できない場合は、値なしです。|http://www.example.com/?age={age}
hasEstimateAge | 年齢拡張フラグです。<br>オーディエンスの年齢を推定判断したかを表します。<br>・年齢推定：true<br>・上記以外：false<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。 | http://www.example.com/?hasEstimateAge={hasEstimateAge}
gender | オーディエンスの性別です。<br>※識別できない場合は、値なしです。|http://www.example.com/?gender={gender}
hasEstimateGender | 性別拡張フラグです。<br>オーディエンスの性別を推定判断したかを表します。<br>・性別推定：true<br>・上記以外：false<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?hasEstimateGender={hasEstimateGender}
searchKeywordId | サーチキーワードIDです。<br>サーチターゲティングで指定したサーチーキーワードを表します。<br>※ターゲティング、インタレストマッチ、インフィード広告商品に指定できます。 | http://www.example.com/?searchKeywordId={searchKeywordId}
ifaSha1 | IFA（広告識別子）のハッシュ値（sha1）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifaSha1={ifaSha1}
ifaMd5 | IFA（広告識別子）のハッシュ値（md5）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifaMd5={ifaMd5}
ifa | IFA（広告識別子）です。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品に指定できます。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifa={ifa}
excluded_targetlist | 除外ターゲットリストです。<br>除外用のターゲットリストIDが返されます。|http://www.example.com/?excluded_targetlist={excluded_targetlist}
