# ReportDefinitionField
ReportDefinitionFieldオブジェクトは、ReportDefinitionの作成に使用できるフィールドを表します。
### Service
+ [ReportDefinitionService](../../services/ReportDefinitionService.md)

### Namespace
[ReportDefinitionService#Namespace](../../services/ReportDefinitionService.md#namespace)

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
 <tr>
  <td>fieldName</td>
  <td>xsd:string</td>
  <td>フィールド名です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayFieldNameJA</td>
  <td>xsd:string</td>
  <td>ダウンロードしたレポートに表示される名前です（日本語）。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>displayFieldNameEN</td>
  <td>xsd:string</td>
  <td>ダウンロードしたレポートに表示される名前です（英語）。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>xmlAttributeName</td>
  <td>xsd:string</td>
  <td>ダウンロードしたレポートのXMLアトリビュートです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
  <tr>
  <td>fieldType</td>
  <td>xsd:string</td>
  <td>フィールドタイプ（数字、文字列、ENUM値など）です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>filterable</td>
  <td>xsd:boolean</td>
  <td>フィールドへのフィルター指定の可否です。trueの場合、フィルター指定が可能です。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
 <tr>
  <td>impossibleCombinationFields[0..n]</td>
  <td>xsd:string</td>
  <td>組み合わせ不可フィールドです。</td>
  <td>yes</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
  <td>-</td>
 </tr>
</table>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
