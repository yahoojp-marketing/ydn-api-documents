# Tracking Parameters
Retrieving the information on which type of ads are clicked will be possible from YDN API tracking parameters. <br>
This functions can easily confirm the effect of ads, which it may leads to a better advertisement.<br>
<br>
Tracking Parameters for YDN API are as follows.<br>
<br>

Parameter | Description | URL Format   
----------- | ----------------- | ---------------- 
creative | Returns Ad ID. | http://www.example.com/?creative={creative} 
media | Returns Media ID.| http://www.example.com/?media={media}
campaignid | Returns Campaign ID.| http://www.example.com/?campaignid={campaignid}
adgroupid | Returns Ad Group ID.| http://www.example.com/?adgroupid={adgroupid}
device | Returns the device type.<br>Returns the elements as follows:<br> -DESKTOP<br> -WAP_MOBILE<br> -SMARTPHONE<br> -TABLET<br>* Returns NONE, if cannot be identified. | http://www.example.com/?device={device}
os | Returns the OS type.<br>Returns the elements as follows:<br> -IOS<br> -ANDROID<br>* Returns NONE, if cannot be identified. | http://www.example.com/?os={os}
isApp | Returns the App type.<br>Tracks if delivered to iOS apps and/or Android apps<br> - true: delivered to iOS apps and/or Android apps<br> - false: not delivered to iOS apps or Android apps | http://www.example.com/?isApp={isApp}
ifaSha1 | Returns Hash (sha1) of Ad identifier.<br>Tracks Hash (sha1) of IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br>*Not available for Interest Match <br>(available for targeting and Infeed Ads).<br>*Not available for standard campaign. <br>*For mobile app campaign, only available with tracking tools（＊）integrated with YDN. | http://www.example.com/?ifaSha1={ifaSha1}
ifaMd5 | Returns Hash (md5) of Ad identifier.<br>Tracks Hash (md5) of IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br><br>*Not available for Interest Match <br>(available for targeting and Infeed Ads).<br>*Not available for standard campaign. <br>*For mobile app campaign, only available with tracking tools（＊）integrated with YDN.| http://www.example.com/?ifaMd5={ifaMd5}
ifa | Returns Ad identifier.<br>Tracks IFA (Ad identifier).<br> - For iOS: IDFA<br> - For Android OS: AdvertisingID<br><br>*Not available for Interest Match <br>(available for targeting and Infeed Ads).<br>*Not available for standard campaign. <br>*For mobile app campaign, only available with tracking tools（＊）integrated with YDN.| http://www.example.com/?ifa={ifa}

（＊）Check this [help topic](https://help.marketing.yahoo.co.jp/en/?p=9910) about tracking tool integrated with YDN.  
