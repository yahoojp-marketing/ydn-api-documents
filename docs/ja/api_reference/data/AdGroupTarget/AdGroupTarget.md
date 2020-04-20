

# AdGroupTarget

AdGroupTargetオブジェクトは、広告グループに設定されているターゲティング情報を格納します。<br/>

**従来キャンペーンと目的別キャンペーンで設定できるターゲティングの違い**

ディスプレイ広告（YDN）のキャンペーン（以下、従来キャンペーンと表記）と、ディスプレイ広告（運用型）の目的別キャンペーンでは、設定できるターゲティングは異なります。詳細は以下のとおりです。

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
|               デバイスターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合は設定必須、かつSMARTPHONEかTABLETのみ設定可能です。 |
|               キャリアターゲティング |        ○         |         -          | 目的別キャンペーンでは指定できません。                                                                                                                   |
|          ウェブ/アプリターゲティング |        ○         |         ○          |                                                                                                                                                          |
|                     OSターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合、Campaignで指定したappOsと同じOSが設定されます。      |
|           OSバージョンターゲティング |        ○         |         ○          | 従来キャンペーンの「アプリキャンペーン」<br>もしくは<br>目的別キャンペーン「アプリ訴求」<br>の場合のみ指定できます。                                     |
| オーディエンスカテゴリターゲティング |        -         |         ○          | 従来キャンペーンでは指定できません。                                                                                                                     |

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)


### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Type</th>
      <th>Description</th>
      <th>response</th>
      <th>add</th>
      <th>set</th>
      <th>remove</th>
      <th>replace</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>accountId</td>
      <td>xsd:long</td>
      <td>アカウントIDです。</td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
    <tr>
      <td>campaignId</td>
      <td>xsd:long</td>
      <td>キャンペーンIDです。</td>
      <td>yes</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
    </tr>
    <tr>
      <td>adGroupId</td>
      <td>xsd:long</td>
      <td>広告グループIDです。</td>
      <td>yes</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
    </tr>
    <tr>
      <td>bidMultiplier</td>
      <td>xsd:double</td>
      <td>入札価格調整率です。<br>※入札価格調整率が設定できないターゲティングの場合は返却されません。</td>
      <td>yes</td>
      <td>Optional</td>
      <td>Optional</td>
      <td>Ignore</td>
      <td>Optional</td>
    </tr>
    <tr>
      <td rowspan="3">target</td>
      <td><a href="./Target.md">Target</a><br>
      inherited <a href="./AdScheduleTarget.md">AdScheduleTarget</a><br>
      inherited <a href="./GeoTarget.md">GeoTarget</a><br>
      inherited <a href="./AgeTarget.md">AgeTarget</a><br>
      inherited <a href="./GenderTarget.md">GenderTarget</a><br>
      inherited <a href="./InterestCategoryTarget.md">InterestCategoryTarget</a><br>
      inherited <a href="./SearchTarget.md">SearchTarget</a><br>
      inherited <a href="./SiteCategoryTarget.md">SiteCategoryTarget</a><br>
      inherited <a href="./SiteRetargetingTarget.md">SiteRetargetingTarget</a><br>
      inherited <a href="./PlacementTarget.md">PlacementTarget</a><br>
      inherited <a href="./AudienceCategoryTarget.md">AudienceCategoryTarget</a></td>
      <td rowspan="3">広告グループのターゲティング情報です。</td>
      <td>yes</td>
      <td>Requirement</td>
      <td>Requirement</td>
      <td>Requirement</td>
      <td>Requirement</td>
    </tr>
    <tr>
      <td>
      inherited <a href="./DeviceTarget.md">DeviceTarget</a><br>
      inherited <a href="./CarrierTarget.md">CarrierTarget</a><br>
	※
      </td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Requirement</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
    <tr>
      <td>
      inherited <a href="./AppTarget.md">AppTarget</a><br>
      inherited <a href="./OsTarget.md">OsTarget</a><br>
      inherited <a href="./OsVersionTarget.md">OsVersionTarget</a><br>
      </td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
  </tbody>
</table>
※SET時に必要なtargetIdは、AdGroupオブジェクトにデバイスやキャリアが設定されている場合にレスポンスされます。<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
