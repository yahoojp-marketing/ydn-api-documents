

# Campaign

Campaignオブジェクトは、キャンペーン情報を表します。<br>

### キャンペーン目的について

- Campaign.campaignGoalがNONEの場合は「目的なし」、NONE以外の場合は「目的あり」と定義します。
- V201911以前に作られたキャンペーンはすべて「目的なし」となります。
- 「目的あり」と「目的なし」のキャンペーンでそれぞれ必須、あるいは更新可能なフィールドが異なるため、以下の表に目的のあり／なし、add／setの場合の必須、更新可能フィールドをまとめます。
   - ※ `--` は、「設定不可」を表します。

| フィールド名            | 目的なし<br>add    | 目的なし<br>set    | 目的あり<br>add    | 目的あり<br>set    |
| ---      | --- | --- | --- | --- |
| campaignType            | Optional           | --       | --       | --       |
| adProductType           | Required           | --       | --       | --       |
| frequencyCap            | Optional           | Updatable          | --       | --       |
| conversionOptimizer     | --       | Updatable          | --       | --       |
| campaignGoal            | --       | --       | Required            | --       |
| viewableFrequencyCap    | --       | --       | Optional           | Updatable          |
| campaignBiddingStrategy | --       | --       | Required           | Updatable          |
| budget.amount           | Optional           | Updatable          | Required            | Updatable          |
| budget.deliveryMethod   | Optional           | Updatable          | --       | --       |

              

### Service

+ [CampaignService](../../services/CampaignService.md)

### Namespace

[CampaignService#Namespace](../../services/CampaignService.md#namespace)

| Field | Type | Description | response | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントID | yes | Requirement | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| campaignId | xsd:long | キャンペーンID | yes | Ignore | Requirement<br>NotUpdatable | Requirement<br>NotUpdatable | |
| campaignName | xsd:string | キャンペーン名 | yes | Requirement | Optional<br>Updatable | Ignore | |
| userStatus | enum [UserStatus](./UserStatus.md) | ユーザー設定の配信ステータス<br>指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。 | yes | Requirement | Optional<br>Updatable | Ignore | |
| servingStatus | enum [CampaignServingStatus](./CampaignServingStatus.md) | 配信ステータス<br>ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。 | yes | Ignore | Ignore | Ignore | |
| startDate | xsd:string | 開始日 | yes | Optional | Optional<br>Updatable | Ignore | |
| endDate | xsd:string | 終了日 | yes | Optional | Optional<br>Updatable | Ignore | |
| budget | [Budget](./Budget.md) | キャンペーン予算 | yes | Requirement | Optional<br>Updatable | Ignore | |
| biddingStrategy | [BiddingStrategy](./BiddingStrategy.md)<br>inherited [ManualCPC](./ManualCPC.md)<br>inherited [ManualCPV](./ManualCPV.md) | 入札最適化方法<br>* 目的ありのキャンペーンでは設定されません。<br> | yes | Ignore | Ignore | Ignore | |
| adProductType | xsd:string | 配信方法<br>※指定可能な値は、[AccountAdProductService](../../services/AccountAdProductService.md)<br>のget操作でご確認ください。 | yes | Optional<br><br>* 目的なしの場合 : 必須<br>* 目的ありの場合 : 設定不可<br> | NotUpdatable | Ignore | |
| frequencyCap | [FrequencyCap](./FrequencyCap.md) | フリークエンシー制御 | yes | Optional<br>* 目的ありの場合 : 設定不可 | Optional<br>Updatable<br>* 目的ありの場合 : 設定不可 | Ignore | |
| conversionOptimizer | [CampaignConversionOptimizer](./CampaignConversionOptimizer.md)<br>inherited [AutoCampaignConversionOptimizer](./AutoCampaignConversionOptimizer.md)<br>inherited [ManualCampaignConversionOptimizer](./ManualCampaignConversionOptimizer.md) | コンバージョン最適化設定<br>* 目的ありの場合 : [ManualCampaignConversionOptimizer](./ManualCampaignConversionOptimizer.md)固定<br> | yes | Ignore | Optional<br>Updatable<br>* 目的ありの場合 : 設定不可 | Ignore | |
| campaignType | enum [CampaignType](./CampaignType.md) | キャンペーンタイプ | yes | Optional<br><br>* 未指定時 : STANDARD<br>* 目的ありの場合 : 設定不可 ( STANDARD固定 )<br> | Ignore | Ignore | |
| appName | xsd:string | アプリの名称 | yes | Optional<br>※campaignTypeがAPPの場合 : Requirement | Ignore | Ignore | |
| appId | xsd:string | iOS:アプリID<br>Android:パッケージ名 | yes | Optional<br>※campaignTypeがAPPの場合 : Requirement | Ignore | Ignore | |
| appOs | enum [DeviceOsType](./DeviceOsType.md) | アプリインストール広告デバイス種別 | yes | Optional<br>※campaignTypeがAPPの場合 : Requirement | Ignore | Ignore | |
| labels[0..1000] | [Label](./Label.md) | ラベル | yes | Ignore | Ignore | Ignore | |
| feedHolderId | xsd:long | フィードホルダーID | yes | Optional<br>※動的ディスプレイ広告の場合 : Requirement | Ignore | Ignore | |
| campaignGoal | xsd:string | キャンペーン目的<br>※指定可能な値は、[AccountService](../../services/AccountService.md)のget操作で得られる[Account](../../data/Account/Account.md)のaccountAuthoritiesフィールドをご確認ください。<br> | yes | Optional<br><br>* 目的なしの場合 : 設定不可<br>* 目的ありの場合 : 必須<br> | Ignore | Ignore | |
| campaignBiddingStrategy | [CampaignBiddingStrategy](./CampaignBiddingStrategy.md) | キャンペーン入札戦略 | yes | Optional<br><br>* 目的なしの場合 : 設定不可<br>* 目的ありの場合 : 必須<br> | Optional<br><br>* 目的なしの場合 : 設定不可<br>* 目的ありの場合 : 必須<br> | Ignore | |
| viewableFrequencyCap | [ViewableFrequencyCap](./ViewableFrequencyCap.md) | ビューアブルフリークエンシー制御 | yes | Optional<br><br>* 目的なしの場合 : 設定不可<br>* 目的ありの場合 : 任意<br> | Optional<br>Updatable<br><br>* 目的なしの場合 : 設定不可<br>* 目的ありの場合 : 任意<br> | Ignore | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
