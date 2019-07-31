# ConversionTrackerOperation
ConversionTrackerOperationオブジェクトは、mutateメソッドで操作対象となるコンバージョントラッカー情報を保持します。

### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ Operation

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>add</th>
  <th>set</th>
 </tr>
 <tr>
  <td>accountId</td>
  <td>xsd:long</td>
  <td>アカウントIDです。</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 <tr>
  <td>operand[1..500]</td>
  <td><a href="./ConversionTracker.md">ConversionTracker</a><br>
  inherited <a href="./WebConversion.md">WebConversion</a><br>
  inherited <a href="./AppConversion.md">AppConversion</a>
  </td>
  <td>操作対象となるコンバージョントラッカー情報のリストです。</td>
  <td>Requirement</td>
  <td>Requirement</td>
 </tr>
 </table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
