# AdGroup
AdGroupオブジェクトは、広告グループの情報を格納するコンテナです。
### Service
+ [AdGroupService](../services/AdGroupService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| accountId| xsd:long| アカウントIDです。 |
| campaignId| xsd:long| キャンペーンIDです。 |
| campaignName| xsd:string| キャンペーン名です。 |
| adGroupId| xsd:long| 広告グループIDです。 |
| adGroupName| xsd:string| 広告グループ名です。 |
| userStatus| enum <a href="../data/UserStatus.md">UserStatus</a>| 配信状況です。 |
| bid| AdGroupBid<br>enum <a href="../data/ManualCPCAdGroupBid.md">ManualCPCAdGroupBid</a>| 入札金額です。 |
| device| enum <a href="../data/DeviceType.md">DeviceType</a>| 配信するデバイス名です。 |
| deviceApp| enum <a href="../data/DeviceAppType.md">DeviceAppType</a>| 配信するアプリケーションの指定です。 |
| deviceOs| enum <a href="../data/DeviceOsType.md">DeviceOsType</a>| 配信先のOSの指定です。 |
| smartDeviceCarriers| enum <a href="../data/SmartDeviceCarrier.md">SmartDeviceCarrier</a>| モバイルキャリアの指定です。 |
| dynamicImageExtensions| enum <a href="../data/DynamicImageExtensions.md">DynamicImageExtensions</a>| 画像自動付与設定です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
