# AdGroupTarget
AdGroupTargetオブジェクトは、広告グループに設定されているターゲティング情報を格納します。
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
  <td>target</td>
  <td><a href="./Target.md">Target</a><br>
  inherited　<a href="./AdScheduleTarget.md">AdScheduleTarget</a><br>
  inherited　<a href="./GeoTarget.md">GeoTarget</a><br>
  inherited　<a href="./AgeTarget.md">AgeTarget</a><br>
  inherited　<a href="./GenderTarget.md">GenderTarget</a><br>
  inherited　<a href="./InterestCategoryTarget.md">InterestCategoryTarget</a><br>
  inherited　<a href="./SiteCategoryTarget.md">SiteCategoryTarget</a><br>
  inherited　<a href="./SiteRetargetingTarget.md">SiteRetargetingTarget</a><br>
  inherited　<a href="./SearchTarget.md">SearchTarget</a><br>
  inherited　<a href="./PlacementTarget.md">PlacementTarget</a><br>
  inherited　<a href="./DeviceTarget.md">DeviceTarget</a><br>
  inherited　<a href="./CarrierTarget.md">CarrierTarget</a><br>
  inherited　<a href="./AppTarget.md">AppTarget</a><br>
  inherited　<a href="./OsTarget.md">OsTarget</a><br>
  inherited　<a href="./OsVersionTarget.md">OsVersionTarget</a>
  </td>
  <td>広告グループのターゲティング情報です。</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
