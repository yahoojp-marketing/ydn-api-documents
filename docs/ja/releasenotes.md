# リリースノート
## リリースバージョン　　
5.3 (WSDLバージョン: 5.3.0)

## バージョンアップの種類　　
マイナーバージョンアップ 

## 本リリースの主な内容
#### 1. 統計情報の取得機能を追加 
キャンペーン、広告グループ、広告、メディア（画像）の単位で統計情報を取得する機能を追加しました。<br>

* 対象ウェブサービス  
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)

* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。
  
* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。
 
#### 2. 操作履歴のダウンロード機能を追加 
操作履歴データのダウンロード機能を追加しました。<br>

* 対象ウェブサービス  
 * [AuditLogService](/docs/ja/api_reference/services/AuditLogService.md)
  
* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。

* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。

#### 3. サイトリターゲティング機能におけるルールタイプの追加 
ルールタイプに以下を追加しました。<br>
    - ページ種別<br>
    - アイテムID<br>
    - アイテムカテゴリーID<br>

* 対象ウェブサービス  
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

* 対象ウェブサービス  
 * 対象になるデータオブジェクトはありません。
 
* 対象Enumerations  
 * [RuleType(enum)](/docs/ja/api_reference/data/RuleType.md)

## Serviceの変更による各Versionへの影響
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.2以前</p></th>
    <th valign="top"><p>Ver.5.3</p></th>
  </tr>
  <tr>
    <td><p>StatsService</p></td>
    <td><p>・機能提供を開始 しました。</p></td>
    <td><p>・統計情報の取得条件に、メディアIDを指定できるように なりました。</p></td>
  </tr>
  <tr>
    <td><p>AuditLogService</p></td>
    <td><p>・機能提供はありません。<br></p></td>
    <td><p>・新規公開です。</p></td>
  </tr>  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>・変更はありません。</p></td>
    <td><p>・RuleType（ルールタイプ）のEnum値に以下を追加しました。<br>
    　- PAGE_TYPE（ページ種別）<br>
    　- ITEM_ID（アイテムID）<br>
    　- ITEM_CATEGORY_ID（アイテムカテゴリーID）
    </p></td>
  </tr>
</tbody>
</table>

## YDN API Ver.5.1のサポート終了予定日
YDN API Ver.5.1は、2016年9月にサポート終了予定です。
