# ResponsiveAd
The ResponsiveAd object stores the Responsive Ad information.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| headline| string| 1| 0| ○| Req| Opt| Ignore| Title of ad. |
| description| string| 1| 0| ○| Req| Opt| Ignore| Description of ad. |
| url| string| 1| 0| ○| Req| Opt| Ignore| Destination URL of ad. |
| displayUrl| string| 1| 0| ○| Req| Opt| Ignore| Display URL of ad. |
| buttonText| enum <a href="./ButtonText.md">ButtonText</a>| 1| 0| ○| Opt| Opt| Ignore| Text for button on ads. |
| principal| string| 1| 0| ○| Req| Opt| Ignore| Advertiser Indication of ad. |
| logoMediaId| long| 1| 0| ○| Opt| Opt| Ignore| Media ID of logo image. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
