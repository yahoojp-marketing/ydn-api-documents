# Campaign
Campaignオブジェクトは、キャンペーン情報を表します。
### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンIDです。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ユーザーにより広告配信の有無を調整できる設定です。<br>
  指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>servingStatus</td>
  <td>enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a></td>
  <td>キャンペーンレベルの配信状況です。<br>
  ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>開始日です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>終了日です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>budget</td>
  <td><a href="./Budget.md">Budget</a></td>
  <td>キャンペーン予算です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategy</td>
  <td><a href="./BiddingStrategy.md">BiddingStrategy</a></td>
  <td>入札最適化方法です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adProductType</td>
  <td>xsd:string</td>
  <td>広告商品情報です。<br>※指定可能な値は、<a href="../../services/AccountAdProductService.md">AccountAdProductService</a>のget操作でご確認ください。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>NotUpdatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>frequencyCap</td>
  <td><a href="./FrequencyCap.md">FrequencyCap</a></td>
  <td>フリークエンシー制御です。</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionOptimizer</td>
  <td><a href="./CampaignConversionOptimizer.md">CampaignConversionOptimizer</a><br>
inherited　<a href="./ManualCampaignConversionOptimizer.md">ManualCampaignConversionOptimizer</a><br>
inherited　<a href="./AutoCampaignConversionOptimizer.md">AutoCampaignConversionOptimizer</a></td>
  <td>コンバージョン最適化設定です。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType </a></td>
  <td>キャンペーンタイプです。</td>
  <td>yes</td>
  <td>Optional<br>※未指定時：STANDARD</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appName</td>
  <td>xsd:string</td>
  <td>アプリの名称です。</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：必須</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>iOS:アプリID<br>Android:パッケージ名</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：必須</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appOs</td>
  <td>enum <a href="./DeviceOsType.md">DeviceOsType</a></td>
  <td>アプリインストール広告のデバイス種別</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：必須</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
