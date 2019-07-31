# CampaignSelector
CampaignSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service
+ [CampaignService](../../services/CampaignService.md)

### Namespace
[CampaignService#Namespace](../../services/CampaignService.md#namespace)

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
  <td>検索条件 : アカウントID</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>campaignIds[0..200]</td>
  <td>xsd:long</td>
  <td>検索条件 : キャンペーンID</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>labelIds[0..1000]</td>
  <td>xsd:long</td>
  <td>検索条件 : ラベルID</td>
  <td>Optional</td>
 </tr>
  <tr>
  <td>containsLabelIdFlg</td>
  <td>xsd:boolean</td>
  <td>ラベルID取得フラグ</td>
  <td>Optional</td>
 </tr>
   <tr>
  <td>feedHolderIds[0..10]</td>
  <td>xsd:long</td>
  <td>検索条件 : フィードホルダーID</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>userStatus[0..2]</td>
  <td>enum <a href="./UserStatus.md">UserStatus</a></td>
  <td>検索条件 : ユーザー設定の配信ステータス</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>検索条件 : 取得範囲</td>
  <td>Optional</td>
 </tr>
 <tr>
  <td>campaignType</td>
  <td>enum <a href="./CampaignType.md">CampaignType</a></td>
  <td>検索条件 : キャンペーンタイプ</td>
  <td>Optional</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
