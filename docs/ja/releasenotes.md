# リリースノート
## リリースバージョン　　
6.0 (WSDLバージョン: 6.0)

## バージョンアップの種類　　
メジャーバージョンアップ 

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

#### 1. 動画広告の機能を追加 
動画広告の機能を追加しました。これにより、動画広告の入稿や、動画広告関連の統計情報の取得などが可能になりました。<br>

##### 対象ウェブサービス  
 * [VideoService](/docs/ja/api_reference/services/VideoService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [MediaService](/docs/ja/api_reference/services/MediaService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [BulkService](/docs/ja/api_reference/services/BulkService.md)

#### 2.	Yahoo! DMP連携対応
Yahoo! DMPのカスタムオーディエンスリストの作成、変更等に対応しました。  
※利用にはYahoo! DMPのご契約が必要です。

##### 対象ウェブサービス  
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)


#### 3.	システムの保守、改善の実施
以下のサービスにおいてシステムの保守、改善を実施しました。<br>
対象サービスごとの変更内容は「Serviceの変更による各Versionへの影響」の項目をご参照ください。<br>

##### 対象ウェブサービス  
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [AccountAdProductService](/docs/ja/api_reference/services/AccountAdProductService.md)
 * [AuditLogService](/docs/ja/api_reference/services/AuditLogService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)


## Serviceの変更による各Versionへの影響

<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.4以前</p></th>
    <th valign="top"><p>Ver.6.0</p></th>
  </tr>
  <tr>
  <td colspan="3"><b>動画広告機能の追加</b></td>
</tr>
  <tr>
    <td><p>VideoService</p></td>
    <td><p>機能提供なし</p></td>
    <td><p>・動画広告入稿サービスの新規公開<br>
・以下のオブジェクトを追加<br>
　-VideoSelector（getメソッドの検索条件（実行パラメータ）を保持）<br>
　-VideoOperation（mutateメソッドで操作対象キャンペーンを保持）<br>
　-VideoPage（getメソッドの実行結果（全Entityのリスト）を保持）<br>
　-VideoReturnValue（mutateメソッドの実行結果（全Entityのリスト）を保持）<br>
　-VideoValues（get/mutateメソッドの実行結果（1Entity）を保持）<br>
　-VideoRecord（動画の情報を保持）<br>
　-VideoSetting（動画の設定内容を保持）<br>
　-UploadVideo（アップロードする動画の情報を格納）<br>
　-UploadUrlPage（getUploadUrlメソッドの実行結果（全Entityのリスト）を保持）<br>
　-UploadUrlValues（動画のアップロード先URL情報を格納）<br>
　-UploadUrlValue（動画のアップロード先URL情報を保持）<br>
・以下のEnumを追加<br>
　-VideoFileType（動画のファイルタイプ）<br>
　-VideoApprovalStatus（動画の審査ステータス）<br>
　-VideoProcessStatus（動画の処理ステータス）<br>
　・動画広告用のエラーコードを追加<br>
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「ManualCPVAdGroupAdBid」（CPV入札価格情報を保持するオブジェクト）の追加<br>
    ・「AdGroup」の「bid」項目のinheritedに、「ManualCPVAdGroupBid」を追加
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「VideoAd」（動画広告オブジェクト）の追加<br>
    ・「ManualCPVAdGroupAdBid」（CPV入札価格情報を保持するオブジェクト）の追加<br>
    ・「AdGroupAd」の「ad」項目のinheritedに「VideoAd」を追加<br>
    ・「AdGroupAd」の「bid」項目のinheritedに「ManualCPVAdGroupAdBid」を追加</p>
    </td>
  </tr>
  <tr>
    <td><p>CampaignService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「biddingStrategyType」に「MANUAL_CPV」を追加<br>
    ・「Campaign」の「biddingStrategy」項目で、Add、Setのリクエスト時は「Ignore」に変更<br>
   </p></td>
  </tr>
  <tr>
    <td><p>MediaService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「ThumbnailFlg」（動画サムネイル画像フラグオブジェクト）の追加<br>
    ・「MediaRecord」に「ThumbnailFlg」項目を追加<br>
    </p></td>
  </tr>
    <tr>
    <td><p>StatsService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「StatsType」に「VIDEO」項目を追加<br>
    ・「StatsType」の「MEDIA」項目を「IMAGE」に変更<br>
   ・「Stats」に動画広告関連の以下項目を追加<br>  
    　-autoVideoPlays（動画自動再生数）<br>
　-clickVideoPlays（動画クリック再生数）<br>
　-videoViewedRate（動画再生率　※動画再生数/インプレッション数）<br>
　-averageCpv（平均CPV）<br>
　-videoPlays（動画総再生数）<br>
　-videoViewsTo25（動画25%再生数）<br>
　-videoViewsTo50（動画50%再生数）<br>
　-videoViewsTo75（動画75%再生数）<br>
　-videoViewsTo95（動画95%再生数）<br>
　-videoViewsTo100（動画100%再生数）<br>
　-averageRateVideoViewed（動画平均再生割合　※動画平均再生時間/動画平均最長再生時間）<br>
　-averageDurationVideoViewed（動画平均再生時間（秒））<br>
    </p></td>
  </tr>
  <tr>
    <td><p>BulkService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「EntityType」に「VIDEO」（動画）項目を追加</p></td>
  </tr>
  
  <tr>
  <td colspan="3"><b>Yahoo! DMP連携対応</b></td>
</tr>
  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>カスタムオーディエンスリストの削除のみ可能</p></td>
    <td><p>「CustomAudienceTargetList」（Yahoo! DMPの行動履歴を利用するターゲットリストのオブジェクト）を追加<br>
    ・「RetargetingListSelector」の「targetListTypes」項目を「0...5」に変更<br>
    ・「RetargetingListOperation」から「targetListType」項目を削除<br>
    ・「RetargetingList」に「accountId」項目を追加<br>
    ・「RetargetingList」の「targetList」項目のinheritedに「CustomAudienceTargetList」を追加<br>
    ・「RuleTargetList」の「reachPeriod」項目のtypeをintに変更<br>
    </p></td>
  </tr>

  <tr>
  <td colspan="3"><b>システムの保守改善</b></td>
</tr>
<tr>
    <td><p>StatsService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・WSDLを修正</p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>変更なし</p></td>
    <td><p>
  ・「SearchTarget」から「searchKeywordListStatus」項目を削除<br>
  ・「SiteRetargetingTarget」から「targetListStatus」項目を削除<br>
  ・以下のEnumを削除<br>
    　-TargetListStatus<br>
　-SearchTargetListStatus<br>
・WSDLを修正</p></td>
  </tr>
<tr>
    <td><p>AuditLogService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・WSDLを修正</p></td>
  </tr>
  <tr>
    <td><p>AccountAdProductService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「AdProduct」から「status」項目を削除<br>
    ・「AdProductStatus」を削除</p></td>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「SmartDeviceCarrier」に「NONE」項目を追加</p></td>
  </tr>
  <tr>
    <td><p>AccountService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「AccountStatus」に「CANCELED（解約済み）」を追加</p></td>
  </tr>
  <tr>
    <td><p>ReportDefinitionService</p></td>
    <td><p>変更なし</p></td>
    <td><p>・「ReportFilter」（フィルター定義を保持するオブジェクト）を追加<br>
    ・「FilterOperator」（フィルターで指定可能な演算子）を追加<br>
    ・「ReportDefinitionField」に「filterable」項目を追加<br>
    ・「ReportDefinition」に「filters」項目を追加
    </p></td>
  </tr>
</tbody>
</table>

## YDN API　レポートドキュメントの改修
YDN APIのレポートドキュメントを改修しました。今後は以下の資料をご参照ください。
 * [レポートフィールド一覧](/docs/ja/api_reference/appendix/reports.md)


## YDN API Ver.5.3のサポート終了予定日
YDN API Ver.5.3は、2017年7月にサポート終了予定です。詳細な日程が決まり次第、お知らせいたします。

