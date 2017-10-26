# リリースノート
## リリースバージョン　　
6.1 (WSDLバージョン: 6.1)

## バージョンアップの種類　　
マイナーバージョンアップ 

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. ターゲティング単位での入札価格調整率の設定 
各種ターゲティングの単位で入札価格調整率が設定できるようになりました。<br>
入札価格調整率が設定可能なターゲティング一覧は以下をご確認ください。

| No | ターゲティング | 入札価格調整率 | 
|---|---|---|
| 1 | AD_SCHEDULE_TARGET | 可 | 
| 2 | AGE_TARGET | 可 | 
| 3 | GENDER_TARGET | 可 | 
| 4 | GEO_TARGET | 可 | 
| 5 | INTEREST_CATEGORY | 可 | 
| 6 | SITE_CATEGORY | 可 | 
| 7 | SITE_RETARGETING | 不可 | 
| 8 | SEARCH_TARGET | 不可 | 
| 9 | PLACEMENT_TARGET | 不可 | 
| 10 | DEVICE_TARGET<br>(V6.1 追加) | 可 | 
| 11 | CARRIER_TARGET<br>(V6.1 追加) | 可 | 
| 12 | APP_TARGET<br>(V6.1 追加) | 不可 | 
| 13 | OS_TARGET<br>(V6.1 追加) | 不可 | 
| 14 | OS_VERSION_TARGET<br>(V6.1 追加) | 不可 | 

##### 対象ウェブサービス  
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)

#### 2.	アプリキャンペーンの追加に対応
スマートフォンやタブレットのアプリをプロモーションするためのアプリキャンペーンの追加に対応しました。これにより以下の機能変更を行いました。<br>
‐アプリ向けのターゲティング機能を追加<br>
‐アプリインストールのコンバージョン計測が可能<br>

##### 対象ウェブサービス  
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [DictionaryService](/docs/ja/api_reference/services/DictionaryService.md)

#### 3.	コンバージョン機能の改善
デバイスをまたいだコンバージョンの計測が可能になりました。これによりコンバージョンの計測期間を7日から90日の範囲内で設定可能になりました。<br>

##### 対象ウェブサービス  
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)


#### 4.	システムの保守、改善の実施
以下のサービスにおいてシステムの保守、改善を実施しました。<br>
対象サービスごとの変更内容は「Serviceの変更による各Versionへの影響」の項目をご参照ください。<br>

##### 対象ウェブサービス  
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [DictionaryService](/docs/ja/api_reference/services/DictionaryService.md)
 * [BulkService](/docs/ja/api_reference/services/BulkService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)


## Serviceの変更による各Versionへの主な影響
<table class="standard">
  <tbody>
  <tr>
    <th>Service</th>
    <th>Ver.6.0以前</th>
    <th>Ver.6.1</th>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>
    変更なし<br><br>
    広告グループ作成時は以下の設定が必要<br>
    ‐device<br>
    ‐deviceApp<br>
    ‐deviceOs<br>
    ‐smartDeviceCarriers
    </p></td>
    <td><p>
    ・AdGroupにdeviceOsVersion（OSバージョン）を追加<br>
    これによりアプリキャンペーンの広告グループにて、OSバージョンを指定できる<br>
    ・エラーコードを追加
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>
    変更なし<br><br>
    ・入札価格調整率の設定、照会は不可<br>
    ・ターゲティング操作はsetメソッドのみ<br>
    ・デバイスターゲティング、OSバージョンターゲティングなどの設定、照会は不可
    </p></td>
    <td><p>
    ・各種ターゲティング単位で入札価格調整率が設定が可能<br>
    ・ターゲティング操作でmutate(add)、mutate(remove)、replaceメソッドを新規追加<br>
    ・以下のターゲティング機能を新規追加<br>
    　‐デバイスターゲティング<br>
    　‐キャリアターゲティング<br>
    　‐ウェブ/アプリターゲティング<br>
    　‐OSターゲティング<br>
    　‐OSバージョンターゲティング<br>
    ・エラーコードを追加
    </p></td>
  </tr>
  <tr>
    <td><p>CampaignService</p></td>
    <td><p>
    変更なし<br><br>
    ・アプリキャンペーンの登録、変更、照会は不可
    </p></td>
    <td><p>
    ・アプリキャンペーンの登録、変更、照会、削除が可能<br>
    ※Ver.6.1以降で登録、変更、照会、削除が可能なキャンペーンの種類は以下のとおり<br>
    　-標準キャンペーン<br>
    　-アプリキャンペーン<br>
    ・エラーコードを追加
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>
    変更なし<br><br>
    </p></td>
    <td><p>
    変更なし<br>
    ※エラーコードの追加のみ
    </p></td>
  </tr>
  <tr>
    <td><p>ConversionTrackerService</p></td>
    <td><p>
    変更なし<br><br>
    ・コンバージョン計測期間の設定、照会は不可（測定期間は30日固定）<br>
    </p></td>
    <td><p>
    ・コンバージョン計測期間を7日から90日の範囲内で設定が可能<br>
    ・アプリインストールのコンバージョン計測が可能
    </p></td>
  </tr>
  <tr>
    <td><p>DictionaryService</p></td>
    <td><p>
    変更なし<br><br>
    </p></td>
    <td><p>
    ・getOsVersion、getMediaAdFormatメソッドを新規追加<br>
    ・アプリキャンペーンにおいてOS、およびOSバージョンをターゲティングで指定できる<br>
    ・アプリのOSとバージョンを照会できる。<br>
    ・入稿できる画像の形式を照会できる。
    </p></td>
  </tr>
  <tr>
    <td><p>ReportService</p></td>
    <td><p>
    変更なし<br><br>
    getDownloadUrlの利用が可能
    </p></td>
    <td><p>
    getDownloadUrlメソッドの利用は不可（getメソッドでダウンロードURLの照会が可能）
    </p></td>
  </tr>
  <tr>
    <td><p>BulkService</p></td>
    <td><p>
    ・BulkUploadStatusSelectorのoutputフォーマットでXML、ZIPPED_XMLを指定した場合、バリデーションエラーに変更<br>
    ・BulkUploadStatusSelectorのlang、encodingをサポート対象外（ignore）に変更<br>
    ・downloadBulkUploadFileUrlとdownloadBulkUploadErrorFileUrlで取得できるファイルが同一になる<br>
    (downloadBulkUploadFileUrlで取得するファイルにもエラーメッセージが含まれるようになる)
    </p></td>
    <td><p>
    ・BulkUploadStatusSelectorのoutputフォーマットを以下のとおり変更<br>
    　-TSV<br>
    　-CSV<br>
    　-ZIPPED_TSV<br>
    　-ZIPPED_CSV<br>
    　※XML、ZIPPED_XMLを削除<br>
    ・BulkUploadStatusSelectorのlang、encodingを削除<br>
    ・ProcessingItemsCountにvideoCount、videoErrorCountを追加<br>
    ・getUploadUrlのリクエストにuploadBulkJobNameを追加<br>
    ・downloadBulkUploadErrorFileUrl項目を削除
    </p></td>
  </tr>
  <tr>
    <td><p>StatsServcie</p></td>
    <td><p>
    変更なし<br><br>
    コンバージョンの旧指標のみ照会可能
    </p></td>
    <td><p>
    ・コンバージョンの旧指標、および新しい指標の照会が可能<br>
    ・コンバージョンの新指標値（クロスデバイスコンバージョンを加味した値）が照会可能
    </p></td>
  </tr>
</tbody>
</table>

## YDN API　レポートドキュメントの改修
YDN APIのレポートドキュメントを改修しました。以下の資料をご参照ください。
 * [レポートフィールド一覧](/docs/ja/api_reference/appendix/reports.md)


## YDN API Ver.5.4のサポート終了予定日
YDN API Ver.5.4は、2017年12月21日（木）にサポート終了予定です。
