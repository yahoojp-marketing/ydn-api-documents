# StaticFrameAd
The StaticFrameAd object stores the Static Frame Ad information.
### Service
+ [AdGroupAdService](../services/AdGroupAdService.md)

| Field | Data Type | maxOccurs | minOccurs | response | add | set | remove | Description | 
|---|---|---|---|---|---|---|---|---|
| size| string| 1| 0| ○| Req| Req<br>Not updatable| Ignore| Ad size. |
| headline| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| Title of ad. |
| description| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| Description of ad. |
| url| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| Destination URL of ad. |
| displayUrl| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| Display URL of ad. |
| layout| string| 1| 0| ○| Opt(size=300X250)| Req(size=300X250)<br>Not updatable| Ignore| Ad layout. <br>Please refer to <a href="./AdLayout.md">AdLayout</a> for the possible layout type.|
| buttonText| enum <a href="./ButtonText.md">ButtonText</a>| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| Text for button on ad. |
| principal| string| 1| 0| ○| Req(size=300X250)| Opt(size=300X250)| Ignore| Advertiser Indication of ad. |
| logoMediaId| long| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| Media ID of logo image of ad. |
| colorSetId| long| 1| 0| ○| Opt(size=300X250)| Opt(size=300X250)| Ignore| Color set ID of ad. |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
