# CampaignSelector
The CampaignSelector object is a container for storing a set of criteria (parameters) for get method.

### Service
+ [CampaignService](../services/CampaignService.md)

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
  <td>campaignIds[0..200]</td>
  <td>xsd:long</td>
  <td>Campaign ID</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>userStatus[0..2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>Delivery status of user settings</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="./Paging.md">Paging</a></td>
  <td>Data acquisition range</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType</a></td>
  <td>Campaign type</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
