# AppConversion
AppConversionオブジェクトは、アプリコンバージョントラッカーの情報を保持します。

### Service
+ [ConversionTrackerService](../../services/ConversionTrackerService.md)

### Namespace
[ConversionTrackerService#Namespace](../../services/ConversionTrackerService.md#namespace)

### Inheritance
+ [ConversionTracker](./ConversionTracker.md)

<table>
 <tr>
  <th>Field</th>
  <th>Type</th>
  <th>Description</th>
  <th>response</th>
  <th>add</th>
  <th>set</th>
 </tr>
 <tr>
  <td>appId</td>
  <td>xsd:string</td>
  <td>計測対象のアプリIDです。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appPlatform</td>
  <td>enum <a href="./AppConversionPlatform.md">AppConversionPlatform</a></td>
  <td>計測対象アプリのプラットフォームです。</td>
  <td>yes</td>
  <td>Required</td>
  <td>Ignore</td>
 </tr>
 <tr>
  <td>appConversionType</td>
  <td>enum <a href="./AppConversionType.md">AppConversionType</a></td>
  <td>アプリコンバージョンの計測タイプです。</td>
  <td>yes</td>
  <td>Optional<br>※Default値：FIRST_OPEN</td>
  <td>Ignore</td>
 </tr>
 </table>


<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
