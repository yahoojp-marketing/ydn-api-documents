# AdGroupTarget
The AdGroupTargets object is a container for storing targeting information specified ad group.
### Service
+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace
[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

<table>
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
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad group ID.</td>
  <td>yes</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
  <td>Required<br>NotUpdatable</td>
 </tr>
 <tr>
  <td>bidMultiplier</td>
  <td>xsd:double</td>
  <td>Bid adjustment.<br>&lowast;If bid adjustment is unable to set targeting, not returned.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional</td>
  <td>Ignore</td>
  <td>Optional</td>
 </tr>
<tr>
  <td>target</td>
  <td><a href="./Target.md">Target</a><br>
  inherited <a href="./AdScheduleTarget.md">AdScheduleTarget</a><br>
  inherited <a href="./GeoTarget.md">GeoTarget</a><br>
  inherited <a href="./AgeTarget.md">AgeTarget</a><br>
  inherited <a href="./GenderTarget.md">GenderTarget</a><br>
  inherited <a href="./InterestCategoryTarget.md">InterestCategoryTarget</a><br>
  inherited <a href="./SiteCategoryTarget.md">SiteCategoryTarget</a><br>
  inherited <a href="./SiteRetargetingTarget.md">SiteRetargetingTarget</a><br>
  inherited <a href="./SearchTarget.md">SearchTarget</a><br>
  inherited <a href="./PlacementTarget.md">PlacementTarget</a><br>
  inherited <a href="./DeviceTarget.md">DeviceTarget</a><br>
  inherited <a href="./CarrierTarget.md">CarrierTarget</a><br>
  inherited <a href="./AppTarget.md">AppTarget</a><br>
  inherited <a href="./OsTarget.md">OsTarget</a><br>
  inherited <a href="./OsVersionTarget.md">OsVersionTarget</a>
  </td>
  <td>Targeting information of ad group.</td>
  <td>yes</td>
  <td>Required</td>
  <td>Required</td>
  <td>Required</td>
  <td>Required</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
