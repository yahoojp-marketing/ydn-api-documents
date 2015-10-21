# Tracking Parameters
Retrieving the information on which type of ads are clicked will be possible from YDN API tracking parameters. <br>
This functions can easily confirm the effect of ads, which it may leads to a better advertisement.<br>
<br>

Parameter | Description | URL Format   
----------- | ----------------- | ---------------- 
creative | Returns AdTrackID. | http://www.example.com/?creative={creative} 
media | Returns Media ad ID.|http://www.example.com/?media={media}
targetlist | Returns Site Retargeting ad ID.|http://www.example.com/?targetlist={targetlist}
device | Returns the device type.<br>Returns the elements as follows:<br> -DESKTOP<br> -WAP_MOBILE<br> -SMARTPHONE<br> -TABLET<br>* Returns NONE, if cannot be identified. | http://www.example.com/?device={device}
os | Returns the OS type.<br>Returns the elements as follows:<br> -IOS<br> -ANDROID<br>* Returns NONE, if cannot be identified. | http://www.example.com/?os={os}
isApp | Returns App flag.<br>Tracks if delivered to IOS apps and/or ANDROID apps<br> - true: delivered to IOS apps and/or ANDROID apps<br> - false: not delivered to IOS apps or ANDROID apps | http://www.example.com/?isApp={isApp}
placementUrl|Returns Placement URL.<br>URL is up to 250 characters.<br>If exceeds 250 characters, URL will display up to 250th characters.<br>* Available only for targeting related products and Infeed Ads.<br>* Not available for Interest Match.<br>* placementUrl will URL encode to UTF-8.|http://www.example.com/?placementUrl={placementUrl}
interestCategory | Returns Interest Category.<br>Format of Interest Category code is: TC-IC-xxxxxxxx (Code scheme referred from DictionaryService)<br>Tracking results will be three categories in one site.<br>Code will be divided by “｜” sign <br>(Ex: "TC-IC-xxxxxxxx｜TC-IC-xxxxxxxx｜TC-IC-xxxxxxxx")| http://www.example.com/?interestCategory={interestCategory}
siteCategory | Returns Site Category.<br>Format of Interest Category code is: TC-SC-xxxxxxxx (Code scheme referred from DictionaryService)|http://www.example.com/?siteCategory={siteCategory}
age | Returns users' age.<br>Returns no values, if cannot identified.|http://www.example.com/?age={age}
hasEstimateAge | Returns age estimation flag.<br>Tracks if users' age was estimated.<br> - true: age estimated <br> - false: age not estimated <br>* Available only for targeting related products and Infeed Ads. <br>* Not available for Interest Match.| http://www.example.com/?hasEstimateAge={hasEstimateAge}
gender | Returns users' gender.<br>Returns no values, if cannot identified.|http://www.example.com/?gender={gender}
hasEstimateGender | Returns gender estimation flag.<br>Tracks if users' gender was estimated.<br> - true: gender estimated<br> - false: gender not estimated<br>* Available for targeting related products and Infeed Ads.<br>* Not available for Interest Match.|http://www.example.com/?hasEstimateGender={hasEstimateGender}
searchKeywordId | Returns Search keyword ID.users'<br>Tracks Search keyword designated in Search Targeting.<br>* Available for targeting related products, Interest Match, and Infeed Ads.| http://www.example.com/?searchKeywordId={searchKeywordId}
ifaSha1 | Returns Hash (sha1) of Ad identifier.<br>Tracks Hash (sha1) of IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br>* Available for targeting related products and Infeed Ads. <br>* Not available for Interest Match.|http://www.example.com/?ifaSha1={ifaSha1}
ifaMd5 | Returns Hash (md5) of Ad identifier.<br>Tracks Hash (md5) of IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br>* Available for targeting related products and Infeed Ads. <br>* Not available for Interest Match.|http://www.example.com/?ifaMd5={ifaMd5}
ifa |Returns Ad identifier.<br>Tracks IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br>* Available for targeting related products and Infeed Ads.<br>* Not available for Interest Match.|http://www.example.com/?ifa={ifa}
