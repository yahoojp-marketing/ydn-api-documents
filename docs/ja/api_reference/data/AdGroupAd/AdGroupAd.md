# AdGroupAd
AdGroupAdオブジェクトは、広告の情報を格納するコンテナです。
### Service
+ [AdGroupAdService](../../services/AdGroupAdService.md)

### Namespace
[AdGroupAdService#Namespace](../../services/AdGroupAdService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>get</th>
  <th>add</th>
  <th>set</th>
  <th>remove</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントID</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>キャンペーンID</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>キャンペーン名</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>広告グループID </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>広告グループ名</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adId</td>
  <td>xsd:long</td>
  <td>広告ID </td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adName</td>
  <td>xsd:string</td>
  <td>広告名 </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>adStyle</td>
  <td>enum <a href="AdStyle.md">AdStyle</a></td>
  <td>掲載フォーマットの種別<br>
  ※デフォルト値は「TEXT」</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>mediaId</td>
  <td>xsd:long</td>
  <td>画像ID</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>配信状況</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>approvalStatus</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>審査状況</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes</td>
  <td>xsd:string<br>-num DisapprovalReasonCode</td>
  <td>掲載拒否の理由</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>bid</td>
  <td>AdGroupAdBid<br>inherited<br>
  <a href="./ManualCPCAdGroupAdBid.md">ManualCPCAdGroupAdBid</a><br> <a href="./ManualCPVAdGroupAdBid.md">ManualCPVAdGroupAdBid</a></td>
  <td>入札価格</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>ad</td>
  <td><a href="Ad.md">Ad</a><br>
  inherited <a href="TextAd.md">TextAd</a><br>
  inherited <a href="MobileAd.md">MobileAd</a><br>
  inherited <a href="PosAd.md">PosAd</a><br>
  inherited <a href="ResponsiveAd.md">ResponsiveAd</a><br>
  inherited <a href="StaticFrameAd.md">StaticFrameAd</a><br>
  inherited <a href="VideoAd.md">VideoAd</a><br>
  inherited <a href="DynamicAd.md">DynamicAd</a><br>
  inherited <a href="None.md">None</a></td>
  <td>広告を含むコンテナ</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>impressionBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>インプレッションビーコンURL</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>isRemoveBeaconUrls</td>
  <td>enum <a href="./IsRemoveFlg.md">isRemoveFlg</a></td>
  <td>インプレッションビーコンURL<br>削除フラグです。<br>
  設定値が「TRUE」の場合、設定されている<br>インプレッションビーコンURLの<br>値が無効になります。</td>
  <td>-</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
<tr>
  <td>labels[0..1000]</td>
  <td><a href="./Label.md">Label</a></td>
  <td>ラベル</td>
  <td>yes</td>
  <td>-</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
