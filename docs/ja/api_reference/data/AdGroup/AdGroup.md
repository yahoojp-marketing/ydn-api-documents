

# AdGroup

AdGroupオブジェクトは、広告グループ情報を保持します。<br/>

- 広告グループに紐づくキャンペーンが「目的あり」か「目的なし」かによって広告グループに指定可能なフィールドや値が異なるため、以下の表に目的のあり／なし、add／setの場合の必須、更新可能フィールドや値をまとめます。
   - ※ `--` は、「設定不可」を表します。

| フィールド名           | 目的あり<br>                      | 目的なし<br>キャンペーンタイプ : CampaignType.APP | 目的なし<br>キャンペーンタイプ : CampaignType.STANDARD |
| ---     | ---                | ---                                | ---                                     |
| device                 | Optional ( SMARTPHONE or TABLET ) | Optional ( SMARTPHONE or TABLET )                 | Optional ( DESKTOP or WAP_MOBILE or NONE )             |
| deviceOs               | --                      | --                                      | --                                           |
| smartDeviceCarriers    | --                      | Optional                                          | Optional                                               |
| dynamicImageExtensions | --                      | Optional                                          | Optional                                               |
| adGroupBiddingStrategy | Optional                          | --                                      | --                                           |

        

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントID | yes | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignId | xsd:long | キャンペーンID | yes | Requirement | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| campaignName | xsd:string | キャンペーン名 | yes | Ignore | Ignore | Ignore | |
| adGroupId | xsd:long | 広告グループID | yes | Ignore | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupName | xsd:string | 広告グループ名 | yes | Requirement | Optional<br/>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | 広告グループのユーザー設定の配信ステータス | yes | Requirement | Optional<br/>Updatable | Ignore | |
| bid | AdGroupBid<br>inherited [ManualCPCAdGroupBid](./ManualCPCAdGroupBid.md)<br>inherited [ManualCPVAdGroupBid](./ManualCPVAdGroupBid.md) | 入札価格情報 | yes | Optional<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Optional<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Ignore | |
| conversionOptimizer | [AdGroupConversionOptimizer](./AdGroupConversionOptimizer.md)<br>inherited [AutoAdGroupConversionOptimizer](./AutoAdGroupConversionOptimizer.md)<br>inherited [ManualAdGroupConversionOptimizer](./ManualAdGroupConversionOptimizer.md)<br>inherited [NoneAdGroupConversionOptimizer](./NoneAdGroupConversionOptimizer.md) | コンバージョン最適化設定 | yes | Optional<br/>Default : NoneAdGroupConversionOptimizer | Optional<br/>Updatable | Ignore | |
| device[0...5] | enum [DeviceType](./DeviceType.md) | 配信デバイス種別 | yes | Requirement | Optional<br/>Updatable | Ignore | |
| deviceApp[0...3] | enum [DeviceAppType](./DeviceAppType.md) | 配信のアプリ種別 | yes | Optional | Optional<br/>Updatable | Ignore | |
| deviceOs[0...3] | enum [DeviceOsType](./DeviceOsType.md) | 配信のOS種別 | yes | Optional | Optional<br/>Updatable | Ignore | |
| smartDeviceCarriers[0...5] | enum [SmartDeviceCarrier](./SmartDeviceCarrier.md) | モバイルキャリア | yes | Optional<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Optional<br/>Updatable<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Ignore | |
| deviceOsVersion | xsd:string | OSバージョン<br/>※deviceOsVersionを空で指定する場合：「NONE」 | yes | Optional | Optional<br/>Updatable | Ignore | |
| dynamicImageExtensions | enum [DynamicImageExtensions](./DynamicImageExtensions.md) | 画像自動付与設定<br/>※Default値：PAUSED | yes | Optional<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Optional<br/>Updatable<br>*目的ありのキャンペーン配下の広告グループの場合 : 設定不可 | Ignore | |
| labels[0..1000] | [Label](./Label.md) | ラベル | yes | Ignore | Ignore | Ignore | |
| feedSetId | xsd:long | 商品セットID | yes | Optional | Optional<br/>Updatable | Ignore | |
| isRemoveFeedSetId | xsd:boolean | 商品セットとの関連付けを削除（配信停止） | yes | Optional | Optional<br/>Updatable<br><br>  ※Default値<br>  -false<br> | Ignore | |
| adGroupBiddingStrategy | [AdGroupBiddingStrategy](./AdGroupBiddingStrategy.md) | 広告グループ入札戦略 | yes | Optional<br>*目的なしのキャンペーン配下の広告グループの場合 : 設定不可 | Optional<br>*目的なしのキャンペーン配下の広告グループの場合 : 設定不可 | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
