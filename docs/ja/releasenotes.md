# リリースノート
## リリースバージョン　　
5.4 (WSDLバージョン: 5.4.0)

## バージョンアップの種類　　
マイナーバージョンアップ 

## 本リリースの主な内容
#### 1. サーチターゲティングの機能追加 
サーチキーワードの有効期間、および検索回数を指定して、サーチターゲットリストの作成ができるようになりました。<br>

* 対象ウェブサービス  
 * [SearchKeywordIdeaService](/docs/ja/api_reference/services/SearchKeywordIdeaService.md)
 * [SearchKeywordListService](/docs/ja/api_reference/services/SearchKeywordListService.md)

* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。
  
* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。
 
#### 2. 広告の入稿項目にインプレッションビーコンURLを追加
広告の入稿項目にインプレッションビーコンURLを追加しました。外部の広告効果測定ツールを利用している場合、インプレッションビーコンURLを利用したインプレッションの計測が可能になります。<br>

* 対象ウェブサービス  
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
  
* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。

* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。

#### 3.	保守改善の実施
一部のウェブサービスにおいて保守改善を実施します。<br>
保守改善による対象ウェブサービスごとの変更内容は「Serviceの変更による各Versionへの影響」の項目をご参照ください。<br>

*  対象ウェブサービス
 * [AccountService](/docs/ja/api_reference/services/AccountService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)
 * [RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

*  対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。

* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。

## Serviceの変更による各Versionへの影響
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.3以前</p></th>
    <th valign="top"><p>Ver.5.4</p></th>
  </tr>
  <tr>
    <td><p>SearchKeywordIdeaService</p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・サーチキーワードリスト取得データオブジェクト（SearchKeywordIdeaSelector）に<br>
    以下の項目を追加しました。<br>
    　- サーチキーワードの有効期間（searchKeywordRecency）<br>
    　- サーチキーワードの検索回数（searchKeywordFrequency）<br>
    ・以下のEnumを追加しました。<br>
    　- サーチキーワードの有効期間（KeywordRecency）<br>
    　- サーチキーワードの検索回数（KeywordFrequency）</p></td>
  </tr>
  <tr>
    <td><p>SearchKeywordListService</p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・サーチキーワードリスト情報保持データオブジェクト（SearchKeywordList）に<br>
    以下の項目を追加しました。<br>
    　- サーチキーワードの有効期間（searchKeywordRecency）<br>
    　- サーチキーワードの検索回数（searchKeywordFrequency）<br>
    ・サーチキーワードの情報保持オブジェクト（SearchKeyword）から<br>
    以下の項目を削除しました。<br>
    　- サーチキーワード（searchKeyword）<br>
    　- PCの検索ボリューム（desktopSearchVolume）<br>
    　- スマートフォンの検索ボリューム（smartPhoneSearchVolume）<br>
    　- タブレットの検索ボリューム（tabletSearchVolume）<br>
    ・以下のEnumを追加しました。<br>
    　- サーチキーワードの有効期間（KeywordRecency）<br>
    　- サーチキーワードの検索回数（KeywordFrequency）</p></td>
    　</tr>
  <tr>
    <td><p>AdGroupAdService </p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・広告情報を保持するデータオブジェクト（AdGroupAd）に<br>
    以下の項目を追加しました。<br>
    　- インプレッションビーコンURL（impressionBeaconUrls）<br>
    　- インプレッションビーコンURL削除フラグ（isRemoveBeaconUrls）<br>
    ・以下のEnumを追加しました。<br>
    　- 削除フラグ（isRemoveFlg）</p></td>
  </tr>
  <tr>
    <td><p>AccountService</p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・アカウントの登録状況（AccountStatus）の<br>
    「サービス停止」を表すEnum値を以下とおり変更しました。<br>
    　- PENDING → SUSPENDED</p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・データオブジェクトの名称を以下のとおり変更しました。<br>
    - AdGroupTargetList → AdGroupTargets<br>
    - TargetList → AdGroupTargetList</p></td>
  </tr>
  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>変更ありません</p></td>
    <td><p>
    ・データオブジェクトの名称を以下のとおり変更しました。<br>
    - TargetList → RetargetingTargetList</p></td>
  </tr>
</tbody>
</table>

## YDN API Ver.5.1のサポート終了予定日
YDN API Ver.5.1は、2016年9月15日にサポート終了予定です。
