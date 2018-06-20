# AdGroupAd
The AdGroupAd object is a container for storing ad information.
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
  <td>Account ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>campaignName</td>
  <td>xsd:string</td>
  <td>Campaign name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad group ID. </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupName</td>
  <td>xsd:string</td>
  <td>Ad group name.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adId</td>
  <td>xsd:long</td>
  <td>Ad ID. </td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement<br>NotUpdatable</td>
  <td>Requirement<br>NotUpdatable</td>
 </tr>  
 <tr>
  <td>adName</td>
  <td>xsd:string</td>
  <td>Ad name. </td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>   
 <tr>
  <td>adStyle</td>
  <td>enum <a href="AdStyle.md">AdStyle</a></td>
  <td>Type of ad style.<br>
  *Default value : TEXT </td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>mediaId</td>
  <td>xsd:long</td>
  <td>Media ID (Image ID).</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>userStatus</td>
  <td>enum <a href="UserStatus.md">UserStatus</a></td>
  <td>Display status.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>  
  <tr>
  <td>approvalStatus</td>
  <td>enum <a href="ApprovalStatus.md">ApprovalStatus</a></td>
  <td>Editorial review status.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>disapprovalReasonCodes</td>
  <td>xsd:string<br>-num DisapprovalReasonCode</td>
  <td>Reject reason on editorial review.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>bid</td>
  <td>AdGroupAdBid<br>inherited<br>
  <a href="./ManualCPCAdGroupAdBid.md">ManualCPCAdGroupAdBid</a><br> <a href="./ManualCPVAdGroupAdBid.md">ManualCPVAdGroupAdBid</a></td>
  <td>Bid value.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
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
  inherited <a href="None.md">None</a></td>
  <td>Container including ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>impressionBeaconUrls[0..2]</td>
  <td>xsd:string</td>
  <td>Impression beacon URL.</td>
  <td>yes</td>
  <td>-</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isRemoveBeaconUrls</td>
  <td>enum <a href="isRemoveFlg.md">isRemoveFlg</a></td>
  <td>Remove flag of impression beacon URL.<br>
  If set 'TRUE', the set value on the impression beacon URL is invalid,</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
