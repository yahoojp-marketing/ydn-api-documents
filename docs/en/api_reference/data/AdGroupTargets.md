# AdGroupTargets
The AdGroupTargets object is a container for storing specified ad target information.
### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)

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
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>campaignId</td>
  <td>xsd:long</td>
  <td>Campaign ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
 <tr>
  <td>adGroupId</td>
  <td>xsd:long</td>
  <td>Ad group ID.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
<tr>
  <td>targets[0..200]</td>
  <td><a href="./AdGroupTargetList.md">AdGroupTargetList</a><br>
  inherited　<a href="./AdScheduleTargetList.md">AdScheduleTargetList</a><br>
  inherited　<a href="./GeoTargetList.md">GeoTargetList</a><br>
  inherited　<a href="./AgeTargetList.md">AgeTargetList</a><br>
  inherited　<a href="./GenderTargetList.md">GenderTargetList</a><br>
  inherited　<a href="./InterestCategoryTargetList.md">InterestCategoryTargetList</a><br>
  inherited　<a href="./SiteCategoryTargetList.md">SiteCategoryTargetList</a><br>
  inherited　<a href="./SiteRetargetingTargetList.md">SiteRetargetingTargetList</a><br>
  inherited　<a href="./SearchTargetList.md">SearchTargetList</a><br>
  inherited　<a href="./PlacementTargetList.md">PlacementTargetList</a></td>
  <td>The targeting settings on ad.</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
 </tr>
</table>
 
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
