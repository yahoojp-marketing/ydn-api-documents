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
  <td>アカウントID</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>ユーザー設定の配信ステータス<br>
  指定しない場合は、フィルタ条件にすべての掲載状況が含まれます。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>servingStatus</td>
  <td>enum <a href="./CampaignServingStatus.md">CampaignServingStatus</a></td>
  <td>配信ステータス<br>
  ユーザーによる広告配信の調整に関わらず、キャンペーンとしての状態を表します。</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>startDate</td>
  <td>xsd:string</td>
  <td>開始日</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>endDate</td>
  <td>xsd:string</td>
  <td>終了日</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>budget</td>
  <td><a href="./Budget.md">Budget</a></td>
  <td>キャンペーン予算</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>biddingStrategy</td>
  <td><a href="./BiddingStrategy.md">BiddingStrategy</a></td>
  <td>入札最適化方法</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adProductType</td>
  <td>xsd:string</td>
  <td>配信方法<br>※指定可能な値は、<a href="../../services/AccountAdProductService.md">AccountAdProductService</a>のget操作でご確認ください。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>NotUpdatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>frequencyCap</td>
  <td><a href="./FrequencyCap.md">FrequencyCap</a></td>
  <td>フリークエンシー制御</td>
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
  <td>コンバージョン最適化設定</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType </a></td>
  <td>キャンペーンタイプ</td>
  <td>yes</td>
  <td>Optional<br>※未指定時：STANDARD</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appName</td>
  <td>xsd:string</td>
  <td>アプリの名称</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：Requirement</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>iOS:アプリID<br>Android:パッケージ名</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：Requirement</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appOs</td>
  <td>enum <a href="./DeviceOsType.md">DeviceOsType</a></td>
  <td>アプリインストール広告デバイス種別</td>
  <td>yes</td>
  <td>Optional<br>※campaignTypeがAPPの場合：Requirement</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>labels[0..1000]</td>
  <td><a href="./Label.md">Label</a></td>
  <td>ラベル</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
   <tr>
  <td>feedHolderId</td>
  <td>xsd:long</td>
  <td>フィードホルダーID</td>
  <td>yes</td>
  <td>Optional<br>※動的ディスプレイ広告の場合：Requirement</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
