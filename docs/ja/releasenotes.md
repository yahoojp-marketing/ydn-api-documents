# リリースノート
## リリースバージョン　　
V201911（WSDLバージョン V201911）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. リーチレポートの取得  
パフォーマンスレポートで取得できるレポートの種類に、「リーチレポート」を追加しました。指定した期間内に1回以上のビューアブルインプレッションが発生したユニークユーザー数を「リーチ数」として集計、表示します。

##### 対象ウェブサービス  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 2. 効果測定 推奨パートナーによる第三者測定スクリプトタグの受け入れ  
以下の企業が提供する第三者測定スクリプトタグの受け入れに対応しました。<br>
　‐Integral Ad Science Japan株式会社<br>
　‐Oracle America, Inc.（旧MOAT）

##### 対象ウェブサービス  
 * [AdGoupAdService](./api_reference/services/AdGroupAdService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)


### 3. ディスプレイ広告（運用型）の一部機能の対応
ディスプレイ広告（運用型）の、以下の機能に対応しました。<br>

 * 目的を設定したキャンペーンに対応<br>
 * オーディエンスカテゴリーターゲティングへの対応<br>
 * Yahoo!ディスプレイアドネットワーク（YDN）で作成したキャンペーンの、ディスプレイ広告（運用型）形式キャンペーンへの変換<br>
 ※ディスプレイ広告（運用型）は、一部のお客様のみに提供している広告掲載方式です。<br>
 ※BulkServiceでは、download、uploadともにディスプレイ広告（運用型）形式キャンペーンはサポートしていません。<br>

##### 対象ウェブサービス  
 * [AccountService](./api_reference/services/AccountService.md)
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [AdGroupTargetService](./api_reference/services/AdGroupTargetService.md)
 * [CampaignMigrationService](./api_reference/services/CampaignMigrationService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 4. 動的ディスプレイ広告の機能改善
動的ディスプレイ広告で、以下の機能改善に対応しました。<br>
 * キャンペーンバナーの入稿に対応
 * 商品リストの項目追加と一部項目の変更、削除
 * 商品リストのテンプレートの変更
 * トラッキング機能の拡充

各機能の詳細は、「[【YDN】動的ディスプレイ広告と動画広告の機能改善について](https://promotionalads.yahoo.co.jp/support/release/775442.html)」を参照してください。<br>
※動的ディスプレイ広告は、一部のお客様のみに提供している広告掲載方式です。なおこの改善は、2019年12月4日（予定）以降に利用可能となります。   

##### 対象ウェブサービス  
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [FeedItemService](./api_reference/services/FeedItemService.md)
 * [FeedSetService](./api_reference/services/FeedSetService.md)
 * [MediaService](./api_reference/services/MediaService.md)


### 5. 保守対応
DictionaryServiceにおいて、「getColorSet」を廃止しました。

##### 対象ウェブサービス
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 
※事前にお知らせした 「コンバージョン測定タグ、サイトジェネラルタグの新フォーマットに対応」は、リリースを延期しました。リリース時期が決まりましたら、あらためてお知らせいたします。お客様にはご迷惑をおかけして申し訳ありません。  


## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201907以前</th>
<th>V2019011</th>
</tr>
<tr>
<td>AccountService</td>
<td>インターフェース変更なし</td>
<td>
利用可能なキャンペーン目的の権限一覧を取得できる<br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>インターフェース変更なし</td>
<td>
・リンク先URL（キャンペーンバナー）、キャンペーンバナー画像を設定できる<br>
・第三者測定スクリプトタグsrc属性URLを設定できる<br>
・25%、50%、75%の各再生視聴ビーコンURLが設定できる<br>
・ディスプレイ広告（運用型）形式キャンペーン配下の広告を取得、追加、設定できる<br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>インターフェース変更なし</td>
<td>
ディスプレイ広告（運用型）形式キャンペーン配下の広告グループを取得、追加、設定できる<br>
</td>
</tr>
<tr>
<td>AdGroupTargetService</td>
<td>インターフェース変更なし</td>
<td>
ターゲティングでオーディエンスカテゴリーを取得、設定できる<br>
</td>
</tr>
<tr>
<td>CampaignMigrationService</td>
<td>-</td>
<td>
・新規サービスとして追加<br>
・YDNキャンペーンからディスプレイ広告（運用型）形式キャンペーンに変換できる<br>
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>インターフェース変更なし</td>
<td>
ディスプレイ広告（運用型）形式キャンペーンを取得、追加、設定できる<br>
</td>
</tr>
<tr>
<td>DictionaryService</td>
<td>インターフェース変更なし</td>
<td>
・MediaAdFormatにキャンペーンバナー画像フラグを追加<br>
・商品リストで利用可能な地域情報およびGoogleのカテゴリ分類を取得できる<br>
・オーディエンスカテゴリーのマスターデータを取得できる<br>
・第三者測定スクリプトタグsrc属性URLのドメイン一覧を取得できる<br>
・getColorSetを廃止<br>
</td>
</tr>
<tr>
<td>FeedItemService</td>
<td>-<br>
</td>
<td>
・新規サービスとして追加<br>
・アイテムIDを指定して、商品リストの商品情報を更新できる<br>
</td>
</tr>
<tr>
<td>FeedSetService</td>
<td>インターフェース変更なし<br>
</td>
<td>
商品リストに追加された項目を商品セットで利用できる<br>
</td>
</tr>
<tr>
<td>MediaService</td>
<td>インターフェース変更なし<br>
</td>
<td>
キャンペーンバナー画像を取得、追加できる<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>インターフェース変更なし<br>
</td>
<td>
・リーチレポートを指定できる<br>
・リーチレポートの最新データ取得可能日を取得できる<br>
・オーディエンスカテゴリーレポートを指定できる<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>インターフェース変更なし<br>
</td>
<td>
オーディエンスカテゴリーの統計情報を取得できる<br>
</td>
</tr>
</tbody>
</table>


## YDN API V201903の提供終了について
以下の日程でYDN API V201903のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2019年12月25日（水）
* システム終了日：2020年3月25日（水）
