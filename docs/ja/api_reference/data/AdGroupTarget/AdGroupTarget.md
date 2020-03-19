

# AdGroupTarget

AdGroupTargetオブジェクトは、広告グループに設定されているターゲティング情報を格納します。<br/>

**従来キャンペーンと目的別キャンペーンで設定できるターゲティングの違いについて**

従来キャンペーンと目的別キャンペーンでは設定できるターゲティングには以下のように違いがあります。

|                       ターゲティング | 従来キャンペーン | 目的別キャンペーン | 備考                                                                                                                                                     |
|-------------------------------------:|:----------------:|:------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
|           曜日・時間帯ターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                   地域ターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                   年齢ターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                   性別ターゲティング |        ○         |         ○          |                                                                                                                                                          |
| インタレストカテゴリーターゲティング |        ○         |         -          | 目的別キャンペーンでは指定できません。                                                                                                                   |
|       サイトカテゴリーターゲティング |        ○         |         ○          |                                                                                                                                                          |
|               サイトリターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                 サーチターゲティング |        ○         |         ○          |                                                                                                                                                          |
|         プレイスメントターゲティング |        ○         |         ○          |                                                                                                                                                          |
|               デバイスターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合、SMARTPHONEかTABLETのうちどちらか一つは設定必須です。 |
|               キャリアターゲティング |        ○         |         -          | 目的別キャンペーンでは指定できません。                                                                                                                   |
|          ウェブ/アプリターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                     OSターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合、Campaignで指定したappOsと同じOSが設定されます。      |
|           OSバージョンターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合飲のみ指定可能                                         |
| オーディエンスカテゴリターゲティング |        -         |         ○          | 従来キャンペーンでは指定できません。                                                                                                                     |
        

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | add | set | remove | replace |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Ignore | Ignore | Ignore | Ignore | |
| campaignId | xsd:long | キャンペーンIDです。 | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| adGroupId | xsd:long | 広告グループIDです。 | yes | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | Requirement<br/>NotUpdatable | |
| bidMultiplier | xsd:double | 入札価格調整率です。<br/>※入札価格調整率が設定できないターゲティングの場合は返却されません。 | yes | Optional | Optional | Ignore | Optional | |
| target | [Target](./Target.md)<br>inherited [AdScheduleTarget](./AdScheduleTarget.md)<br>inherited [GeoTarget](./GeoTarget.md)<br>inherited [AgeTarget](./AgeTarget.md)<br>inherited [GenderTarget](./GenderTarget.md)<br>inherited [InterestCategoryTarget](./InterestCategoryTarget.md)<br>inherited [SearchTarget](./SearchTarget.md)<br>inherited [SiteCategoryTarget](./SiteCategoryTarget.md)<br>inherited [SiteRetargetingTarget](./SiteRetargetingTarget.md)<br>inherited [PlacementTarget](./PlacementTarget.md)<br>inherited [DeviceTarget](./DeviceTarget.md)<br>inherited [CarrierTarget](./CarrierTarget.md)<br>inherited [AppTarget](./AppTarget.md)<br>inherited [OsTarget](./OsTarget.md)<br>inherited [OsVersionTarget](./OsVersionTarget.md)<br>inherited [AudienceCategoryTarget](./AudienceCategoryTarget.md) | 広告グループのターゲティング情報です。 | yes | Requirement | Requirement | Requirement | Requirement | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
