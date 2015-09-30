# リリースノート
## リリースバージョン　　
5.1 (WSDLバージョン: 5.1.0)
## バージョンアップの種類　　
マイナーバージョンアップ 
## 本リリースの主な内容
#### 1. レポート機能の改善 
レポート機能の変更および追加を行いました。<br>
<br>
※リクエストされたレポート項目（フィールド）の組み合わせにより、レポートの種類（レポートカテゴリ）を自動的に判別してレポートを作成するように機能を変更しました。<br>
（前バージョンまで提供しておりました、レポート種別（レポートタイプ）を指定してレポートを作成する機能は、本バージョンからご利用いただけません。）<br>
※レポート作成機能の変更に伴い、5種類の「レポートカテゴリ」を新設しました。  <br>

レポートカテゴリ | カテゴリに含まれるレポート
---------------- | ------------------------------------
AD | ・アカウントレポート<br>・キャンペーンレポート<br>・広告グループレポート<br>・広告レポート<br>・リンク先URLレポート
INTEREST_CATEGORY | インタレストカテゴリーレポート
SITE_CATEGORY | サイトカテゴリーレポート
URL | 配信先URLレポート
FREQUENCY | フリークエンシーレポート

※対象のレポートにおいて、集計期間を変更しました。（3ヶ月→13ヶ月）<br>
・アカウントレポート<br>
・キャンペーンレポート<br>
・広告グループレポート<br>
・広告レポート<br>
・リンク先URLレポート<br>
・配信先URLレポート<br>
・フリークエンシーレポート<br>
<br>
※対象のレポートにおいて、レポート項目を追加しました。<br>
■広告レポート<br>
　・都道府県<br>
　・都道府県/市区郡<br>
　・性別<br>
　・年齢<br>
　・サーチキーワード<br>
■リンク先URLレポート<br>
　・時間<br>
　・掲載フォーマット/画像タイプ<br>
　・画像名<br>
　・都道府県<br>
　・都道府県/市区郡<br>
　・性別<br>
　・年齢<br>
　・サーチキーワード<br>
　・コンバージョン名<br>
　・コンバージョン測定の目的<br>
<br>
※レポート定義追加の上限数を変更しました。（1個→30個）<br>
<br>
※ソートのリクエスト仕様を複数項目形式に変更しました。（最大5個）<br>
<br>
* 対象ウェブサービス  
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
  
* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。
  
* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。
 
#### 2. キャリア設定の変更   
キャリア設定できる値を削除しました。<br>
・EMOBILE<br>
・WILLCOM<br>
  
* 対象ウェブサービス  
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
  
* 対象データオブジェクト  
 * 対象になるデータオブジェクトはありません。

* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。

#### 3. Serviceの変更による各Versionへの影響  
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.0以前</p></th>
    <th valign="top"><p>Ver.5.1</p></th>
  </tr>

  <tr>
    <td><p>ReportDefinitionService</p></td>
    <td><p>■APIIF変更なし</p></td>
    <td><p>■APIIF変更あり<br>
・Enum の "ReportType"（レポートタイプ）を "ReportCategory"（レポートカテゴリ）に変更しました。<br>
・Enum の "ReportFrequency"（定期レポート作成タイミング）を "ReportIntervalType" に変更しました。<br>
・"ReportFrequencyRange"（フリークエンシーの計測期間）のEnum定義を追加しました。<br>
・"ReportDefinition"（レポート定義情報を保持するオブジェクト）に以下の変更を行いました。<br>
　・"frequencyRange"（フリークエンシーの計測期間）を追加しました。<br>
　・"sort"（ソート）を "sortFields[]" に変更しました。<br>
　　（ソート用のフィールド情報の指定方法がカンマ区切りから複数項目形式に変更になります。）<br>
　・以下のオブジェクトを削除しました：<br>
　　・"campaignId"（キャンペーンID）<br>
　　・"reportType"（レポート種別）<br>
　　・"segments[]"（集計分割指定）<br>
　・"fields[]"（表示項目）に 以下の指定が可能になりました：<br>
　　・"AD_TYPE"（広告タイプ）<br>
　　・"AD_STYLE"（掲載フォーマット）<br>
　　・"MEDIA_AD_FORMAT"（ピクセルサイズ）<br>
　　・"AD_LAYOUT"（広告レイアウト）<br>
　　・"IMAGE_OPTION"（画像自動付与）<br>
<br>
■エラーコード<br>
・テンプレートフラグの設定と他の設定項目の組合せが正しくない場合には「250001：Invalid combination in Template settings.」を返します。<br>
・“fields”に指定できない組み合わせ項目が含まれる場合には「250002：Invalid field settings.」を返します。<br>
・定期レポート作成タイミングの設定と他の設定項目の組み合わせが正しくない場合には「250003：Invalid combination in report date settings.」を返します。<br>
・集計期間種別の設定と他の設定項目の組み合わせが正しくない場合には「250004：Invalid combination in date range type.」を返します。</p></td>
  </tr>
  <tr>
    <td><p>ReportService</p></td>
    <td><p>■APIIF変更なし<br></p></td>
    <td><p>■APIIF変更あり<br>
・"ReportClosedDateRecord"（集計完了日を保持するオブジェクト）を追加しました。<br>
　また、レスポンスで取得可能になった"key" 値は以下のとおりです。<br>
　・FREQ_REPORT_CLOSED_DATE<br>
　・REPORT_CLOSED_DATE</p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>■APIIF変更なし<br>
・2015年9月より、キャリア設定で一部の値を利用できません。<br>
　ご利用されたときは、エラーが返されます。</p></td>
    <td><p>■APIIF変更なし<br>
・キャリア設定で一部の値を利用できません。</p></td>
  </tr>
</tbody></table>

## 技術ドキュメント
本リリースの内容が含まれたドキュメントは、YDN API Ver.5.1です。

## WSDLファイル
本リリースに含まれる機能を利用される場合、ダウンロードページから該当するバージョンのWSDLファイルをダウンロードしてください。

## サンプルプログラム
本リリースバージョンに対応したサンプルプログラムは、ダウンロードページから必要なサンプルプログラムをダウンロードしてください。

## YDN API Ver.5.0以前のご利用について
YDN API Ver.5.0以前も引き続きご利用いただけます。

## YDN API Ver.4.6のサポート終了予定日
YDN API Ver.4.6は、2015年12月以降にサポート終了予定です。 
