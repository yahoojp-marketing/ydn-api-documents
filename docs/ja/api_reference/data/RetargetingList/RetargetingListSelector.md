# RetargetingListSelector
RetargetingListSelectorオブジェクトは、サイトリターゲティングのターゲットリストを指定します。
### Service
+ [RetargetingListService](../../services/RetargetingListService.md)

### Namespace
[RetargetingListService#Namespace](../../services/RetargetingListService.md#namespace)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
 </tr>
 <tr>
  <td>targetListIds[0...100]</td>
  <td>xsd:long</td>
  <td>ターゲットリストIDです。</td>
 </tr>
 <tr>
  <td>targetListTypes[0...5]</td>
  <td>enum<br><a href="./TargetListType.md">TargetListType</a></td>
  <td>ターゲットリスト種別です。</td>
 </tr>
 <tr>
  <td>paging</td>
  <td><a href="../Common/Paging.md">Paging</a></td>
  <td>取得範囲です。</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
