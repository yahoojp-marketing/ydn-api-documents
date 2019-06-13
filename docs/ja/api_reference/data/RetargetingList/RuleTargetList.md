# RuleTargetList
RuleTargetListオブジェクトは、ルール設定のリストを表します。
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
  <td>リターゲティングタグIDです。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isPreset</td>
  <td>enum<br><a href="./IsPreset.md">IsPreset</a></td>
  <td>過去の訪問履歴を利用するかの設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>isOpen</td>
  <td>enum<br><a href="./IsOpen.md">IsOpen</a></a></td>
  <td>ターゲットリストに対してリーチを蓄積するかの設定です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>targetListTypeがDEFAULT_LIST,RULEの場合、Optional/Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>reachPeriod</td>
  <td>xsd:int</td>
  <td>リーチの蓄積期間（1日～540日）です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Optional<br>Updatable</td>
  <td>-</td>
 </tr>
 <tr>
  <td>rules[0...n]</td>
  <td><a href="./Rule.md">Rule</a></td>
  <td>リターゲティングの条件です。</td>
  <td>yes</td>
  <td>-</td>
  <td>Requirement</td>
  <td>Requirement<br>Updatable</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
