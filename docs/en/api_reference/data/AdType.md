# AdType (enum)
AdType serves the number of characters of the title and description according to selected devices and distribution place. 
In addition, the number of characters of the advertisement which can be specified changes with selected devices.

### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Value | Description | 
|---|---|
| TEXT_LONG_AD1| Text ad is "title is 15 charactors" and "description is 19 charactors/ 19 charactors".<br>                        It is available for PC, Smartphone and Tablet.(Recommended) |
| TEST_LONG_AD2| Text ad is "title is 15 charactors" and "description is 33 charactors".<br>                        It is available for PC, Smartphone and Tablet. |
| TEXT_SHORT_AD1| Short text ad is "title is 12 charactors" and "description is 12 charactors".<br>                        It is available for Mobile.(Recommended) |
| TEXT_SHORT_AD2| Short text ad is "title is 14 charactors" and "description is 19 charactors".<br>                        It is available for Mobile. |
| POS_AD| Positioning text is "description is 33 charactors". |
| APP_AD1| Application install ad is “title is 15 characters”, “Description 90 characters”, “No display URL”, and “Destination URL 11-1024 characters” <br>Display URL default:<br>・For iOS: itunes.apple.com<br>・For Android: play.google.com |
| RESPONSIVE_AD| Responsive Ad that change or crop the image size to fit the ad display frame. <br>・Title: 25 characters (Required)<br>・Description: 90 characters (Required)<br>・Display URL: 4-50 characters (Required)<br>・Destination URL: 11-1024 characters (Required)<br>・Advertiser Indication: 20 characters (Required)<br>・Text for button (Optional)<br>・Logo image: 180 x 180 (Optional). |
| STATIC_FRAME_AD| Static Frame Ads that can use three types of layout to match with ad display frame.<br>*Refer to “AdLayout” for more information on Layout details.<br>. |
| NONE| Text is not included. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
