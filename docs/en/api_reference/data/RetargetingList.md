# RetargetingList
RetargetingList object diplays the target list for site retargeting.
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

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
  <td>Account ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>targetListId</td>
  <td>xsd:long</td>
  <td>Target List ID.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Requirement<br>NonUpdatable</td>
  <td>Requirement<br>NonUpdatable</td>
 </tr>
  <tr>
  <td>targetListName</td>
  <td>xsd:string</td>
  <td>Target List name.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>description</td>
  <td>xsd:string</td>
  <td>Description of Target List.</td>
  <td>yes</td>
  <td>Optional</td>
  <td>Optional<br>Updatable</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>deliveryStatus</td>
  <td>enum<br><a href="./DeliveryStatus.md">DeliveryStatus</a></td>
  <td>Ad distribution statys.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
  <tr>
  <td>reach</td>
  <td>xsd:long</td>
  <td>Number of reaches.</td>
  <td>yes</td>
  <td>Ignore</td>
  <td>Ignore</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>targetList</td>
  <td><a href="./RetargetingTargetList.md">RetargetingTargetList</a><br><br>inherited<br>
  <a href="./RuleTargetList.md">RuleTargetList</a><br>
  <a href="./CombinationTargetList.md">CombinationTargetList</a><br>
 <a href="./SimilarityTargetList.md">SimilarityTargetList</a><br>
 <a href="./CustomAudienceTargetList.md">CustomAudienceTargetList</a></td>
  <td>Settings of Target List.</td>
  <td>yes</td>
  <td>Requirement</td>
  <td>Requirement</td>
  <td>Ignore</td>
 </tr>
</table>


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
