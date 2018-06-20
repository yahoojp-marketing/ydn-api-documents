# リリースノート
## リリースバージョン　　
V201806（WSDLバージョン V201806）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1.システムリリースの定期化とバージョン体系の変更

#### (1)システムリリースの定期化

システムリリースのスケジュールを定期化し、以下のとおり変更しました。

（これまで）
 * リリースタイミング<br>機能のリリースごとに、新バージョンをリリース
 * バージョン体系<br>VX.X（例：V6.1）

（V201806以降）
 * リリースタイミング<br>一定期間ごとに機能をまとめて、新バージョンをリリース<br>
※新しいバージョンをリリースするタイミングで、現在公開中のうち最も古いバージョンのサポート終了日をお知らせします。<br>
 * バージョン体系<br>VYYYYMM（例：V201806）

#### (2)バージョン体系の変更
一部の環境において、自動生成によりEntityが重複してしまう問題を解消するため、NameSpaceを細分化しオブジェクトの構成を変更いたしました。

※詳細は「[バージョン体系とwsdlの構成変更について](./api_reference/appendix/numbering_new_versions.md)」をご確認ください。

### 2.コスト関連の指標で小数点以下の金額を表示

コスト関連の指標について、小数点以下の金額の表示（小数点以下第3位まで）を開始しました。対象は以下のレポートフィールドです。
* cost（コスト）
* averageCpc（平均CPC）
* avgCpv（平均CPV）

※V6.1以前に作成したReportIntervalTypeがONETIME（レポート作成タイミングが一度のみ）のレポートでは、整数値を表示します。小数点以下の表示には、V201806で新たにONETIMEのレポートを作成してください。  
※ReportIntervalTypeがONETIME以外のレポートでは、V201806以降に作成した場合も、引き続き整数値を表示します。

##### 対象ウェブサービス  
 * [ReportService](./api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 3. 動画再生に関するレポートフィールドを追加
動画広告のレポートで、動画再生数に関する以下の項目を追加しました。

* videoViews　（動画再生数）
* videoViewsTo3Sec　（動画が3秒以上再生された回数）
* paidVideoViews　（課金が発生した動画再生数）
* paidVideoViewRate　（課金が発生した動画再生率）

なお、以下のレポートフィールドは、V201806の次のバージョンでは利用できなくなります。  
※V201806、およびV6.1以前のバージョンでは引き続き利用可能です。

* autoVideoPlays（動画の自動再生数）
* clickVideoPlays（クリックによる動画再生数）
* videoPlays（動画が再生開始された回数）
* videoViewedRate（動画の再生率）
これらをレポート定義などでご利用の場合は、お早めに設定の変更をお願いいたします。  
変更先となる項目は、以下をご参照ください。

<table>
<tr><th>提供終了予定</th><th>変更先</th></tr>
<tr><td>autoVideoPlays（動画の自動再生数）</td><td rowspan="2">paidVideoViews（課金が発生した動画再生数）</td></tr>
<tr><td>clickVideoPlays（クリックによる動画再生数）</td></tr>
<tr><td>videoPlays（動画が再生開始された回数）</td><td>videoViews（動画再生数）</td></tr>
<tr><td>videoViewedRate（動画の再生率）	</td><td>paidVideoViewRate（課金が発生した動画再生率）</td></tr>
</table>

##### 対象ウェブサービス  
 * [StatsService](./api_reference/services/StatsService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 4. コンバージョン関連機能の改修
#### （1）コンバージョン最適化で広告グループ単位の設定に対応
従来のキャンペーン単位に加えて、広告グループ単位でもコンバージョン最適化を設定できます。  
※キャンペーンと広告グループのどちらも、「optimizerType」でコンバージョン最適化を設定します。

#### （2）コンバージョン測定に「コンバージョン列に含める/含めない」を追加
コンバージョン測定の設定時に、「コンバージョン列に含める/含めない」　を選択できます。「コンバージョン列に含める」を選択すると、コンバージョン最適化の集計対象となり、特定のコンバージョンのみを反映した最適化が可能です。

#### （3）レポートフィールドの追加　※全バージョン対象
「コンバージョン列に含める/含めない」設定の追加に伴い、レポートフィールドに以下の項目を追加しました。  
現状の項目では、「コンバージョン列に含めない」を設定した場合、コンバージョン数を取得できませんでした。今回追加した、日本語名称に「すべての～」　を含む項目では、「コンバージョン列に含める/含めない」の設定にかかわらず、すべてのコンバージョン数を取得できます。

* allConv（すべてのコンバージョン数）
* allConvRate（すべてのコンバージョン率）
* costPerAllConv（コスト/すべてのコンバージョン数）
* allConvValue（すべてのコンバージョンの価値）
* valuePerAllConv（価値/すべてのコンバージョン数）
* convValue（コンバージョンの価値）
* valuePerConv（価値/コンバージョン数）
* convValueOld（コンバージョンの価値（旧））
* valuePerConvOld（価値/コンバージョン数（旧））

#### （4）コンバージョン測定に計測方法（毎回/初回のみ）を追加
同一訪問者による複数のコンバージョンが発生した場合、毎回コンバージョンとして測定するか、初回のみを測定するかを選択できます。初回のみを選択すると、同一訪問者のコンバージョンを排除したユニークコンバージョン数を取得できます。

#### （5）コンバージョン測定タグの変更
ConversionTrackerServiceで取得するコンバージョン測定タグの一部を変更しました。変更箇所は以下のとおりです。

　　現在　yahoo_ydn_conv_amount  
　　変更後　yahoo_ydn_conv_value  

※実施日以前からコンバージョン測定を行っている場合は、引き続き従来のタグを利用できます。

##### 対象ウェブサービス
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 5. システムの保守、改善の実施
以下のサービスにおいてシステムの保守、改善を実施しました。<br>
対象サービスごとの変更内容は「Serviceの変更による各Versionへの影響」の項目をご参照ください。<br>

##### 対象ウェブサービス  
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [BulkService](/docs/ja/api_reference/services/BulkService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>Ver.6.1以前</th>
<th>V201806</th>
</tr>
<tr>
<td>StatsService</td>
<td>
・コンバージョンの現指標値のみ照会できる。<br><br>
・統計情報を取得した場合、取得時点は「昨日」「今日」等の日単位の情報のみ。<br></td>
<td>
・コンバージョンの現指標値、新指標値を照会できる。追加されたレポートフィールドは以下のとおり。<br>
-allConv（すべてのコンバージョン数）<br>
-allConvRate（すべてのコンバージョン率）<br>
-costPerAllConv（コスト/すべてのコンバージョン数）<br>
-allConvValue（すべてのコンバージョンの価値）<br>
-valuePerAllConv（価値/すべてのコンバージョン数）<br>
-convValue（コンバージョンの価値）<br>
-valuePerConv（価値/コンバージョン数）<br>
-convValueOld（コンバージョンの価値（旧））<br>
-valuePerConvOld（価値/コンバージョン数（旧））<br><br>

・動画再生に関する以下のレポートフィールドを追加。<br>
-videoViews（動画再生数）<br>
-videoViewsTo3Sec（動画が3秒以上再生された回数）<br>
-paidVideoViews（課金が発生した動画再生数）<br>
-paidVideoViewRate（課金が発生した動画再生率）<br><br>

・統計情報の開始と終了を、年月日時分で表示。<br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>
・広告グループ単位でのコンバージョン最適化は設定できない。</td>
<td>
・広告グループ単位でのコンバージョン最適化を設定できる。<br><br>
・以下のオブジェクトを追加。<br>
-AdGroupConversionOptimizer<br>
-AdGroupConversionOptimizerType<br>
-NoneAdGroupConversionOptimizer<br>
-ManualAdGroupConversionOptimizer<br>
-AutoAdGroupConversionOptimizer<br>
-ConversionOptimizerEligibilityFlg<br><br>
・AdGroupOperationからcampaignId項目を削除。<br><br>
・エラーコードを追加。
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>・コンバージョン最適化の設定をtargetCpaで指定。<br>
</td>
<td>
・コンバージョン最適化の設定をoptimizerTypeで指定。<br><br>
・以下のオブジェクトを追加。<br>
-CampaignConversionOptimizer<br>
-CampaignConversionOptimizerType<br>
-ManualCampaignConversionOptimizer<br>
-AutoCampaignConversionOptimizer<br>
-CampaignConversionOptimizerType<br>
-ConversionOptimizerEligibilityFlg<br><br>
・エラーコードを追加。
</td>
</tr>
<tr>
<td>ReportService</td>
<td>・インターフェースに変更はありません。<br></td>
<td>・以下の項目で小数点第3位まで表示。<br>
-cost（コスト）<br>
-averageCpc（平均CPC）<br>
-avgCpv（平均CPV）<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>
・コンバージョンに関する以下のレポートフィールドを追加。<br>
-allConv（すべてのコンバージョン数）<br>
-allConvRate（すべてのコンバージョン率）<br>
-costPerAllConv（コスト/すべてのコンバージョン数）<br>
-allConvValue（すべてのコンバージョンの価値）<br>
-valuePerAllConv（価値/すべてのコンバージョン数）<br>
-convValue（コンバージョンの価値）<br>
-valuePerConv（価値/コンバージョン数）<br>
-convValueOld（コンバージョンの価値（旧））<br>
-valuePerConvOld（価値/コンバージョン数（旧））<br><br>
</td>
<td>
・以下の項目で小数点第3位まで表示。<br>
-cost（コスト）<br>
-averageCpc（平均CPC）<br>
-avgCpv（平均CPV）<br><br>

・コンバージョンに関する以下のレポートフィールドを追加。<br>
-allConv（すべてのコンバージョン数）<br>
-allConvRate（すべてのコンバージョン率）<br>
-costPerAllConv（コスト/すべてのコンバージョン数）<br>
-allConvValue（すべてのコンバージョンの価値）<br>
-valuePerAllConv（価値/すべてのコンバージョン数）<br>
-convValue（コンバージョンの価値）<br>
-valuePerConv（価値/コンバージョン数）<br>
-convValueOld（コンバージョンの価値（旧））<br>
-valuePerConvOld（価値/コンバージョン数（旧））<br><br>
・ReportDefinitionFieldからdisplayFieldName項目を削除し、以下を追加。<br>
-displayFieldNameJA<br>
-displayFieldNameEN<br>
-fieldType<br>
-impossibleCombinationFields<br>
</td>
</tr>
<tr>
<td>BulkService</td>
<td>・インターフェースに変更はありません。<br></td>
<td>・downloadTypeでCAMPAIGN以外の設定を不可に変更。<br><br>
・BulkUploadの検索条件からoutput（フォーマット）の指定を削除。<br>
</td>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>・インターフェースに変更はありません。<br></td>
<td>・ConversionTrackerSelectorに以下の項目を追加。<br>
-countingType<br>
-excludeFromBidding<br><br>
・ConversionTrackerPageに以下の項目を追加。<br>
-totalAllConversions<br>
-totalAllConversionValue<br><br>
・ConversionTrackerに以下の項目を追加。<br>
-countingType<br>
-excludeFromBidding<br>
-allConversions<br>
-allConversionValue<br>
</td></tr>
</tbody>
</table>


## YDN API Ver.6.0の提供終了について
以下の日程でYDN API Ver.6.0のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2018年7月20日（金）
* システム終了日：2018年9月20日（木）
