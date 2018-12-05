# リリースノート
## リリースバージョン　　
V201812（WSDLバージョン V201812）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. 動画視聴コンバージョンの測定対応

Yahoo!ディスプレイアドネットワーク（YDN）の動画広告において、動画を10秒以上視聴したユーザーが、視聴後に広告クリック以外の方法でコンバージョンに至った件数の測定に対応しました。これに伴い、以下の点を変更しました。

#### ■パフォーマンスデータおよびレポートにおけるコンバージョン関連指標の仕様変更
 * 既存のコンバージョン関連の指標におけるコンバージョン定義の拡大<br>
　変更前：<br>
　広告のクリック経由でサイトを訪問したユーザーによるコンバージョンをカウント対象とする<br>
　変更後：<br>
　広告のクリック経由でサイトを訪問したユーザー、および、動画広告の動画を10秒以上視聴した後に広告のクリック以外の経路でサイトを訪問したユーザーによるコンバージョンをカウント対象とする<br>
　※10秒未満の動画の場合は、視聴を完了した時点で10秒視聴と同義とします。<br>
 * 新指標の追加<br>
　-広告のクリック経由で発生したコンバージョンのみをカウント対象とする指標<br>
　-デバイスをまたいだコンバージョン数を確認する指標<br>

#### ■視聴ビーコンURL項目を追加

AdGroupAdServiceに、動画コンバージョンを測定する視聴ビーコンURL関連の項目を追加しました。  
また、AuditLogService、BulkServiceのダウンロードファイルにも追加しました。  
※ダウンロードファイルへの追加は、提供中の全バージョンが対象です。

#### ■コンバージョンタグの設定項目の追加
ConversionTrackerServiceに、動画の視聴からコンバージョンが発生するまでの測定期間を設定する項目「measurementPeriodView」を追加しました。測定期間は1日～30日間の範囲で設定できます。  
また、AuditLogServiceのダウンロードファイルにも同項目を追加しました。  
※ダウンロードファイルへの追加は、提供中の全バージョンが対象です。

##### 対象ウェブサービス  
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AuditLogService](./api_reference/services/AuditLogService.md)
 * [BulkService](./api_reference/services/BulkService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)


### 2. 動画広告にアスペクト比1:1の動画フォーマットを追加

動画広告にアスペクト比1：1（ピクセルサイズ　600×600）の新フォーマットを追加しました。なお、APIインターフェース上の変更はありません。  
※提供中の全バージョンが対象です。

##### 対象ウェブサービス  
 * [ReportService](./api_reference/services/ReportService.md)


### 3. サーチターゲティングの機能変更

リクエストにおいて、以下を変更しました。
 * keywordsとkeywordIdsの指定が必須ではなくなり、両方同時指定のみ不可に変更
 * keywordsの上限数を100から200に変更
 * スペースの半角・全角の区別を廃止
 * 以下の項目を追加  
　　- sortField（ソート項目）  
　　- sortType（ソート方法）  
　　- matchType（検索方法）  

また、レスポンスに「releaseDate」（キーワード追加日）を追加しました。

##### 対象ウェブサービス  
 * [SearchKeywordIdeaService](./api_reference/services/SearchKeywordIdeaService.md)


### 4. システムの保守、改善の実施

システムの保守、改善として以下を実施しました。 「Serviceの変更による各Versionへの影響」の項目も、あわせてご確認ください。

 * ReportDefinitionServiceおよびReportServiceから、古いレポート項目を削除
 * 仕様書のレポートフィールド集に「動作区分/Behavior Type」列を追加  
各レポートフィールドの動作を表す「動作区分/Behavior Type」列を追加しました。  
※提供中の全バージョンが対象です。

##### 対象ウェブサービス  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)


## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201809以前</th>
<th>V201812</th>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>
・以下の指標で、広告クリックのコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
</td>
<td>
・以下の指標で、広告クリックおよび10秒以上の動画視聴のコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>

・以下の指標を新たに追加<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
・動画の視聴からコンバージョンが発生するまでの測定期間を設定する項目「measurementPeriodView」を追加<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>
・以下の指標で、広告クリックのコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
・以下のレポート項目を表示<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
・以下の指標で、広告クリックおよび10秒以上の動画視聴のコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
・以下の指標を新たに追加<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
・以下のレポート項目を削除<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>・動画視聴コンバージョン用ビーコンURLを登録できない<br>
</td>
<td>
・動画視聴コンバージョン用ビーコンURLを登録できる<br>
・動画視聴コンバージョン用ビーコン関連の以下項目を追加<br>
　- videoStartBeaconUrls<br>
　- isRemoveVideoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- isRemoveVideo3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- isRemoveVideoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
　- isRemoveVideoCompleteBeaconUrls<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>
・以下のレポート項目を表示<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
・以下の指標で、広告クリックおよび10秒以上の動画視聴のコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
・以下の指標を新たに追加<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
・以下のレポート項目を削除<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>
・以下のレポート項目を表示<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
・以下の指標で、広告クリックおよび10秒以上の動画視聴のコンバージョンを測定<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
・以下の指標を新たに追加<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
・以下のレポート項目を削除<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>SearchKeywordIdeaService</td>
<td>
・リクエストで、keywordsとkeywordIdsの指定が必須<br>
</td>
<td>
・リクエストでkeywordsとkeywordIdsの指定が必須ではなくなる。また、以下の項目の指定が可能。<br>
　-searchMatchType<br>
　-sortField<br>
　-sortKey<br>
・レスポンスで、releaseDate項目を追加<br>
</td>
</tr>
<tr>
<td>AuditLogService</td>
<td>
　
</td>
<td>
・動画視聴コンバージョン用ビーコン関連の以下項目を追加<br>
　- videoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
</td>
</tr>
<tr>
<td>BulkService</td>
<td>
　
</td>
<td>
・動画視聴コンバージョン用ビーコン関連の以下項目を追加<br>
　- videoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
</td>
</tr>
</tbody>
</table>


## YDN API V201806の提供終了について
以下の日程でYDN API V201806のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2019年1月15日（火）
* システム終了日：2019年4月15日（月）

