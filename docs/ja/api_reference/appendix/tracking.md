# トラッキングパラメータ
YDN APIでは、ユーザーがどの種類の広告をクリックしてサイトを訪れたかの情報をトラッキングパラメータで知ることができます。<br>
クリックされた広告タイプを知ることで広告の効果を確認でき、よりよい広告の出力につなげることが可能になります。<br>
<br>

パラメータ | 概要 | URLフォーマット   
----------- | ----------------- | ---------------- 
creative | 広告IDです。 | http://www.example.com/?creative={creative} 
media | メディアIDです。|http://www.example.com/?media={media}
targetlist | ターゲットリストIDです。|http://www.example.com/?targetlist={targetlist}
device | デバイスです。<br>デバイスの種類をトラッキングします。<br>以下の内容が返されます。<br>・DESKTOP<br>・WAP_MOBILE<br>・SMARTPHONE<br>・TABLET<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?device={device}
os | OSです。<br>OSの種類をトラッキングします。<br>以下の内容が返されます。<br>・IOS<br>・ANDROID<br>※識別できない場合は、NONEとなります。 | http://www.example.com/?os={os}
isApp | アプリフラグです。<br>IOSアプリ、ANDROIDアプリに配信されたものかどうかをトラッキングします。<br>・IOSアプリ、ANDROIDアプリの場合：true<br>・上記以外の場合：false | http://www.example.com/?isApp={isApp}
placementUrl|配信先URLです。<br>配信サイトのURLをトラッキングします。<br>URLは250桁までです。250桁を超過する場合は250桁でURLをカットされます。<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。<br>※palcementUrlはUTF-8でURLエンコードされます。|http://www.example.com/?placementUrl={placementUrl}
interestCategory | インタレストカテゴリです。<br>インタレストカテゴリをトラッキングします。<br>インタレストカテゴリコードの形式は、「TC-IC-××××××××」（DictionaryServiceで照会するコード体系）です。<br>1サイトで、トラッキング結果が3カテゴリになります。<br>「｜」区切りでコードを分割します。<br>例：「TC-IC-××××××××｜TC-IC-××××××××｜TC-IC-××××××××」 | http://www.example.com/?interestCategory={interestCategory}
siteCategory | サイトカテゴリです。<br>サイトカテゴリをトラッキングします。<br>サイトカテゴリコードの形式は、「TC-SC-××××××××」（DictionaryServiceで照会するコード体系です）。|http://www.example.com/?siteCategory={siteCategory}
age | 年齢です。<br>オーディエンスの年齢をトラッキングします。<br>※識別できない場合は、値なしです。|http://www.example.com/?age={age}
hasEstimateAge | 年齢拡張フラグです。<br>オーディエンスの年齢を推定判断したかどうかをトラッキングします。<br>・年齢推定：true<br>・上記以外：false<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。 | http://www.example.com/?hasEstimateAge={hasEstimateAge}
gender | 性別です。<br>オーディエンスの性別をトラッキングします。<br>※識別できない場合は、値なしです。|http://www.example.com/?gender={gender}
hasEstimateGender | 性別拡張フラグです。<br>オーディエンスの性別を推定判断したかどうかをトラッキングします。<br>・性別推定：true<br>・上記以外：false<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?hasEstimateGender={hasEstimateGender}
searchKeywordId | サーチキーワードIDです。<br>サーチターゲティングで指定したサーチーキーワードをトラッキングします。<br>※ターゲティング、インタレストマッチ、インフィード広告商品は指定可です。 | http://www.example.com/?searchKeywordId={searchKeywordId}
ifaSha1 | 広告識別子のハッシュ値（sha1）です。<br>IFA（広告識別子）のハッシュ値（sha1）をトラッキングします。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifaSha1={ifaSha1}
ifaMd5 | 広告識別子のハッシュ値（md5）です。<br>IFA（広告識別子）のハッシュ値（md5）をトラッキングします。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifaMd5={ifaMd5}
ifa | 広告識別子です。<br>IFA（広告識別子）をトラッキングします。<br>・iOSの場合：IDFA<br>・Android OSの場合：AdvertisingID<br>※ターゲティングとインフィード広告商品は指定可です。<br>※インタレストマッチ商品は指定不可です。|http://www.example.com/?ifa={ifa}

