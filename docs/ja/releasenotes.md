# リリースノート
## リリースバージョン　　
V201903（WSDLバージョン V201903）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. ラベル機能に対応
Yahoo!ディスプレイアドネットワーク（YDN）のラベル機能の追加に伴い、以下の点を追加・変更しました。

#### ■ラベルの新規作成、設定、編集、削除の対応
以下の対応が可能になりました。<br>
 * ラベルの新規作成、編集、削除<br>
 * 入稿物（キャンペーン、広告グループ、広告）へのラベルの設定、解除<br>
 * ラベルの設定情報の取得<br>
 * ラベルレポートの取得<br>

※広告管理ツールでは、2019年2月6日（水）にリリースしました。<br>

##### 対象ウェブサービス  
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AdGroupAdLabelService](./api_reference/services/AdGroupAdLabelService.md)
 * [AdGroupLabelService](./api_reference/services/AdGroupLabelService.md)
 * [BulkService](./api_reference/services/BulkService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [CampaignLabelService](./api_reference/services/CampaignLabelService.md)
 * [LabelService](./api_reference/services/LabelService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)

### 2. レポート、および統計情報に新指標を追加
レポートおよび統計情報に費用対効果（ROAS）に関する指標の追加に伴い、以下の変更を実施しました。<br>

* レポート、および統計情報に費用対効果（ROAS）に関する以下の指標を追加しました。<br>
   * コンバージョンの価値/コスト
   * すべてのコンバージョンの価値/コスト
   * コンバージョンの価値（広告のクリック経由）/コスト

 * 広告管理ツールにおいて、パフォーマンスレポートの「コンバージョンラベル名」を「コンバージョン名」に変更したことに対応するため、レポートに「コンバージョン名」を追加しました。<br>
   * 「コンバージョン名」には既存の「コンバージョンラベル名」と同じ値が入ります。<br>
   * 「コンバージョンラベル名」は今後廃止予定のため、当該フィールドをご利用中の場合は「コンバージョン名」への変更をお願いいたします。<br>

※詳細は、[仕様書](./api_reference/appendix/reports)もあわせてご参照ください。<br>
※広告管理ツールでは、2019年2月6日（水）にリリースしました。<br>

##### 対象ウェブサービス  
 * [StatsService](./api_reference/services/StatsService.md)

### 3. 自動タグ設定機能への対応
Yahoo!ディスプレイアドネットワーク（YDN）で自動タグ設定機能のリリースに伴い、自動タグ設定のオンオフを追加しました。<br>
※広告管理ツールでは、2019年1月29日（火）にリリースしました。<br>

##### 対象ウェブサービス  
 * [AccountService](./api_reference/services/StatsService.md)

### 4. ターゲティング機能の改善
ターゲティング機能の改善に伴い、統計情報でターゲティングの実績を表示できるようになりました。<br>
※広告管理ツールでは、2019年2月27日（水）にリリースしました。<br>

##### 対象ウェブサービス  
 * [StatsService](./api_reference/services/StatsService.md)

### 5. 動的ディスプレイ広告への対応
動的ディスプレイ広告について、以下の対応が可能になりました。<br>
 * 動的ディスプレイ広告のキャンペーン作成など
 * キャンペーンへのデータフィードの関連付け
 * 「掲載不可」「掲載停止」ステータスの審査情報のダウンロード（最大10万件まで取得可能）

また、新バージョン、および公開中のすべてのバージョン（V201809、V201812）において、エラー情報のダウンロード上限を最大10万件に変更しました。<br>

※広告管理ツールでは、2019年2月13日（水）にリリースしました。なお、正規代理店のお客様のみ利用可能です。<br>

##### 対象ウェブサービス
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [FeedDataService](./api_reference/services/FeedDataService.md)
 * [FeedHolderService](./api_reference/services/FeedHolderService.md)


## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201812以前</th>
<th>V201903</th>
</tr>
<tr>
<td>BulkService</td>
<td>インポート用テンプレートでキャンペーンラベル、広告グループラベル、広告ラベルをEntityTypesとして指定可能。<br>
</td>
<td>インポート用テンプレートでキャンペーンラベル、広告グループラベル、広告ラベルをEntityTypesとして指定可能。<br>
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>インターフェース変更なし<br>
・動的ディスプレイ広告用キャンペーンは、広告商品情報が返却されません。
</td>
<td>
・設定されたラベル情報を取得できる<br>
・動的ディスプレイ広告用キャンペーンを作成可能。<br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>インターフェース変更なし<br>
</td>
<td>設定されたラベル情報を取得できる。<br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>インターフェース変更なし<br>
・動的ディスプレイ広告は、取得できません。
</td>
<td>
以下の操作ができる。<br>
・ラベル情報の取得<br>
・動的ディスプレイ広告の作成<br>
・動的ディスプレイ広告情報の更新<br>
・動的ディスプレイ広告の削除<br>
・動的ディスプレイ広告の取得<br>
</td>
</tr>
<tr>
<td>CampaignLabelService</td>
<td>-<br>
</td>
<td>
キャンペーンにラベルを設定、または解除できる。<br>
</td>
</tr>
<tr>
<td>AdGroupLabelService</td>
<td>-<br>
</td>
<td>広告グループにラベルを設定、または解除できる。<br>
</td>
</tr>
<tr>
<td>AdGroupAdLabelService</td>
<td>-<br>
</td>
<td>広告にラベルを設定、または解除できる。
</td>
</tr>
<tr>
<td>LabelService</td>
<td>-<br>
</td>
<td>以下の操作ができる。<br>
・ラベルの作成<br>
・ラベルの各エンティティへの設定<br>
・ラベル情報の更新<br>
・ラベル設定の解除<br>
・ラベルの削除<br>
・ラベル情報の取得<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>インターフェース変更なし<br>
</td>
<td>
・費用対効果（ROAS）に関する項目を取得できる。<br>
・ターゲットごとの実績値が取得できる。<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>インターフェース変更なし<br>
</td>
<td>
・ラベルごとのパフォーマンスレポートが取得できる。<br>
・費用対効果（ROAS）に関する項目を取得できる。<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>インターフェース変更なし<br>
</td>
<td>
・ラベルごとのパフォーマンスレポートが取得できる。<br>
・費用対効果（ROAS）に関する項目を取得できる。<br>
</td>
</tr>
<tr>
<td>FeedHolderService</td>
<td>インターフェース変更なし<br>
</td>
<td>
審査否認理由ダウンロード用のURLが取得できる。
</td>
</tr>
<tr>
<td>AccountAdProductService</td>
<td>インターフェース変更なし<br>
</td>
<td>
「DYNAMIC_ADS」が返却される。
</td>
</tr>
<tr>
<td>AccountService</td>
<td>インターフェース変更なし<br>
</td>
<td>
自動タグ設定のオンオフが指定できる。
</td>
</tr>
</tbody>
</table>


## YDN API V201809の提供終了について
以下の日程でYDN API V201809のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2019年4月11日（木）
* システム終了日：2019年7月11日（木）

