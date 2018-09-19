# リリースノート
## リリースバージョン　　
V201809（WSDLバージョン V201809）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. サイトリターゲティングの機能追加

Yahoo!ディスプレイアドネットワーク（YDN）のサイトリターゲティング（RetargetingListService）に、以下の機能を追加しました。

#### ■ターゲットリスト（類似）にターゲットリストのサイズを追加

ターゲットリスト（類似）に、基のターゲットリストとの類似度を示す「ターゲットリストのサイズ」を追加しました。基のターゲットリストとの類似度を10段階で指定することで、リーチする範囲を調整できます。

#### ■アプリのイベント情報をもとにしたターゲティング機能を追加

ターゲットリストの条件種別に、アプリのイベント情報（インストール、商品の購入などのアプリ内動作）を設定する「イベント種別」を追加しました。
これにより、アプリ上のユーザーによる行動をもとにしたターゲティングが可能になります。

##### 対象ウェブサービス  
 * [RetargetingListService](./api_reference/services/RetargetingListService.md)


### 2. パフォーマンスデータの取得可能期間を変更

以下の期間を指定したパフォーマンスデータ（統計情報）の取得が可能になりました。

* 13カ月前の月初から昨日まで
* 任意の日付

##### 対象ウェブサービス  
 * [StatsService](./api_reference/services/StatsService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)

### 3. タブレット版Yahoo! JAPANアプリ（iOS）への動画広告配信に対応

動画広告の配信先に、タブレット版Yahoo! JAPANアプリ（iOS）が追加されました。これに伴い、動画広告の入稿で、配信先デバイスに「タブレット」が選択可能になりました。  
※APIインターフェース上の変更はありません。


### 4. 年齢ターゲティングの対象年齢の範囲を変更

YDNの年齢ターゲティングの範囲を一部変更し、従来の「12歳～14歳」を「13歳～14歳」に変更しました。詳細は「Serviceの変更による各Versionへの影響」でご確認ください。
##### 対象ウェブサービス  
 * [AdGroupTargetService](./api_reference/services/AdGroupTargetService.md)
 * [ReportService](./api_reference/services/ReportService.md)


### 5. システムの保守、改善の実施
システムの保守、改善として以下を実施しました。
「Serviceの変更による各Versionへの影響」の項目も、あわせてご確認ください。

 * 一部のエラーコードについて構成を見直し、整理しました。
詳細は「[エラーコードの再編について](./api_reference/appendix/error_codes_structure.md)」をご確認ください。

 * ReportDefinitionServiceにおけるレポートの作成で、定期レポートの定義が作成不可になりました。V201806以前のバージョンで作成した値の参照は可能です。

 * StatsServiceとConversionTrackerServiceにおいて、パフォーマンスデータの取得期間の日時表示を変更しました。

##### 対象ウェブサービス  
 * 全サービス（エラーコードに関する変更）
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)


## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201806以前</th>
<th>V201809</th>
</tr>
<tr>
<td>RetargetingListService</td>
<td>
・ターゲティングリスト（類似）で、ターゲットリストのサイズの取得および設定が不可<br><br>
・ターゲティングリスト（条件）で、イベント種別の取得および設定が不可<br>
</td>
<td>
・ターゲティングリスト（類似）で、 ターゲットリストのサイズ（10段階）の取得、設定が可能<br>
・ターゲティングリスト（条件）で、イベント種別の取得、設定が可能<br>
・SimilarityTargetListに以下の項目を追加<br>
　- targetListSize<br>
　- targetListSizeReaches<br>
・RuleTypeにEVENT_TYPE項目を追加<br>
・以下のオブジェクトを追加<br>
　- TargetListSize<br>
　- TargetListSizeReaches<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>
・パフォーマンスデータ  の取得期間に、過去13カ月間と任意の日付の指定は不可<br>
・パフォーマンスデータの集計完了日時を以下の形式で表示<br>
YYYYMMDDHHmmss<br>
</td>
<td>
・パフォーマンスデータの取得期間に、過去13カ月間と任意の日付を指定可能<br>
・パフォーマンスデータの集計開始日時と集計完了日時を、以下の形式で表示<br>
　YYYYMMDD<br>
　HHmmss<br>
・StatsPeriodに以下の項目を追加<br>
　- DEFINITE_VALUE_LAST13MONTH<br>
　- CUSTOM_DATE<br>
・StatsSelectorにstatsPeriodCustomDate項目を追加<br>
・以下のオブジェクトを追加<br>
　- PeriodDatetime<br>
　- StatsPeriodCustomDate<br>
</td>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>・パフォーマンスデータ の取得期間に、過去13カ月間と任意の日付の指定は不可<br>
</td>
<td>
・パフォーマンスデータの取得期間に、過去13カ月間と任意の日付を指定可能<br>
・パフォーマンスデータの集計開始日時と集計完了日時を、以下の形式で表示<br>
　YYYYMMDD<br>
　HHmmss<br>
・ConversionTrackerSelectorにstatsPeriodCustomDateを追加<br>
・ConversionTrackerPageにperiodを追加<br>
・StatsPeriodに以下の項目を追加<br>
　- DEFINITE_VALUE_LAST13MONTH<br>
　- CUSTOM_DATE<br>
・以下のオブジェクトを追加<br>
　- Period<br>
　- PeriodDatetime<br>
　- StatsPeriodCustomDate<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>・年齢ターゲティングのレポートの年齢表示は6歳〜11歳、12歳〜14歳だが、2018年9月以降は6歳～12歳、13歳～14歳単位の結果も含まれる<br></td>
<td>・年齢ターゲティングのレポートの年齢表示を6歳～12歳、13歳～14歳に変更<br>
・2018年9月以前の配信で6歳～11歳、12歳～14歳単位の集計結果が含まれる時は、6歳～12歳、13歳～14歳にまとめて表示される<br>
</td>
</tr>
<tr>
<td>AdGroupTargetService</td>
<td>・年齢ターゲティングで12歳～14歳（GT_RANGE12_14）を設定した場合、実際の配信対象は13歳～14歳になる<br>
・13歳～14歳（GT_RANGE13_14）は設定不可
<br></td>
<td>・年齢ターゲティングで13～14歳（GT_RANGE13_14）が設定可能<br>
・12歳～14歳（GT_RANGE12_14）は設定不可<br>
・AgeにGT_RANGE13_14を追加<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>
以下の定期レポート項目の利用は非推奨<br>
　・intervalType<br>
　・addTemplate<br>
</td>
<td>
以下の定期レポート項目を入力してもignoreされる。参照のみ可能<br>
　・intervalType<br>
　・addTemplate<br>
</td>
</tr>
</tbody>
</table>


## YDN API Ver.6.1.0の提供終了について
以下の日程でYDN API Ver.6.1.0のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2018年10月19日（金）
* システム終了日：2019年1月18日（金）
