# AdGroup
AdGroupオブジェクトは、広告グループ情報を保持します。
### Service
+ [AdGroupService](../../services/AdGroupService.md)

### Namespace
[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

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
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>広告グループID</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>広告グループ名</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum<br><a href="./UserStatus.md">UserStatus</a></td>
  <td>広告グループのユーザー設定の配信ステータス</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>bid</td>
  <td>AdGroupBid<br>
  inherited　<a href="./ManualCPCAdGroupBid.md">ManualCPCAdGroupBid</a><br>
  inherited　<a href="./ManualCPVAdGroupBid.md">ManualCPVAdGroupBid</a>
  </td>
  <td>入札価格情報</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>conversionOptimizer</td>
  <td>AdGroupConversionOptimizer<br>
inherited　<a href="./NoneAdGroupConversionOptimizer.md">NoneAdGroupConversionOptimizer</a><br>
inherited　<a href="./ManualAdGroupConversionOptimizer.md">ManualAdGroupConversionOptimizer</a><br>
inherited　<a href="./AutoAdGroupConversionOptimizer.md">AutoAdGroupConversionOptimizer</a>
  </td>
  <td>コンバージョン最適化設定</td>
  <td>yes</td>
  <td>Optional<br>Default : NoneAdGroupConversionOptimizer</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>device [0...5]</td>
  <td>enum<br><a href="./DeviceType.md">DeviceType</a></td>
  <td>配信デバイス種別</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceApp[0...3]</td>
  <td>enum<br><a href="./DeviceAppType.md">DeviceAppType</a></td>
  <td>配信のアプリ種別</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceOs [0...3]</td>
  <td>enum<br><a href="./DeviceOsType.md">DeviceOsType</a></td>
  <td>配信のOS種別</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>smartDeviceCarriers[0...5]</td>
  <td>enum<br><a href="./SmartDeviceCarrier.md">SmartDeviceCarrier</a></td>
  <td>モバイルキャリア</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>deviceOsVersion</td>
  <td>xsd:string</td>
  <td>OSバージョン<br>※deviceOsVersionを空で指定する場合：「NONE」</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>dynamicImageExtensions</td>
  <td>enum<br><a href="DynamicImageExtensions.md">DynamicImageExtensions</a></td>
  <td>画像自動付与設定<br>※Default値：PAUSED</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>labels[0..1000]</td>
  <td>enum<br><a href="./Label.md">Label</a></td>
  <td>ラベル</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>feedSetId</td>
  <td>xsd:long</td>
  <td>商品セットID</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable<</td>
  <td>Ignore</td>
  </tr>
  <tr>
   <td>isRemoveFeedSetId</td>
   <td>xsd:boolean</td>
   <td>商品セットとの関連付けを削除（配信停止）</td>
   <td>yes</td>
   <td>Optional</td>
   <td>Optional<br>Updatable<</td>
   <td>Ignore</td>
  </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
