# AdGroupTargetSelector
The AdGroupTargetSelector object contains a set of criteria (parameters) for get method.

### Service
+ [AdGroupTargetService](../services/AdGroupTargetService.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>get</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>Account ID</td>
  <td>Required</td>
 </tr>
 <tr>
  <td>campaignIds[0..1000]</td>
  <td>xsd:long[]</td>
  <td>Campaign ID</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>adGroupIds[0..1000]</td>
  <td>xsd:long[]</td>
  <td>Ad group ID</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>targetTypes[0..7]</td>
  <td>enum <a href="./TargetType.md">TargetType</a></td>
  <td>Type of targeting</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>Scope of the data</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
