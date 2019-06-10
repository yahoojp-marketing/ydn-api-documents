# RuleTargetList
RuleTargetList object displays the list of rule settings.
### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

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
  <td>retargetingTagId</td>
  <td>xsd:string</td>
  <td>ID of Retargeting Tag.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isPreset</td>
  <td>enum<br><a href="./IsPreset.md">IsPreset</a></td>
  <td>Flag settings for history of past visit.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isOpen</td>
  <td>enum<br><a href="./IsOpen.md">IsOpen</a></a></td>
  <td>Display the status to reserve the reach or not for the target list.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>targetListType=DEFAULT_LIST,RULE：Optional/Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reachPeriod</td>
  <td>xsd:int</td>
  <td>Cookies validation period. (1 - 540 days)</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>rules[0...n]</td>
  <td><a href="./Rule.md">Rule</a></td>
  <td>Rules for Retargeting.</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
