# リリースノート
## リリースバージョン　　
V201907（WSDLバージョン V201907）

## 本リリースの主な内容
※対象データオブジェクトとEnumerationは、データオブジェクト（Enumeration）集をご確認ください。 

### 1. 動的ディスプレイ広告の機能改善
動的ディスプレイ広告の機能改善として、商品リストファイルのアップロードに以下の機能を追加しました。

 * デバッグモードに対応<br>
 * ファイルアップロード時にアップロード経路やエラー情報などの詳細情報を取得<br>
 * 定期アップロードに関するステータスを追加<br>

##### 対象ウェブサービス  
 * [FeedDataService](./api_reference/services/FeedDataService.md)

### 2. 画像・動画のアスペクト比による入稿
画像・動画のアスペクト比による入稿に対応しました。<br>
これに伴い、「DictionaryService」のgetMediaAdFormatで、アスペクト比による入稿が可能かを示すフラグ、アスペクト比、最大画像サイズなどの取得に対応しました。<br>

##### 対象ウェブサービス  
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [MediaService](./api_reference/services/MediaService.md)
 * [VideoService](./api_reference/services/VideoService.md)


### 3. PCブランドパネルの入稿に対応
広告掲載方式「PCブランドパネル」の入稿に対応するため、以下の変更を実施しました。<br>

 * CampaignService（公開中の全バージョン）：<br>
　「PCブランドパネル（静止画）」、「PCブランドパネル（動画）」のキャンペーン作成取得、更新、削除に対応<br>
 * AdGroupAdService：<br>
　バナー（動画）広告の作成、取得、更新、削除に対応<br>
　※「PCブランドパネル」は一部のお客様のみに提供している広告掲載方式です。<br>
<br>

##### 対象ウェブサービス
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)


### 4. 効果測定指標の追加、変更
パフォーマンスレポートや統計情報に使用する測定指標を追加、変更しました。<br>

#### 計測方法の変更
以下の指標について、計測方法をクライアントサイド計測に変更しました。<br>
 * インプレッション数<br>
 * クリック率<br>
　※2019年6月30日以前の数値は取得できません。<br>
　※従来のサーバーサイド計測の数値は、新たに追加する「インプレッション数（旧）」「クリック率（旧）」でご確認ください。<br>

#### 定義の変更
平均CPVの定義を、以下のとおり変更しました。<br>
 * 従来　　動画再生にかかったコスト÷課金が発生した動画再生数<br>
 * 変更後　動画再生にかかったコスト÷動画の10秒再生数<br>
※動画の10秒再生数は、課金が発生した動画再生数と同様です。<br><br>

#### 測定タイミングの変更　※API全バージョンが対象<br>
「ビューアブルインプレッション数」（従来の名称は「ビューインプレッション数」）の測定タイミングを、以下のとおり変更しました。実施日以降に発生したビューアブルインプレッションのみが対象です。<br>
 * 従来　　広告の配信日時を発生日時として測定<br>
 * 変更後　　広告がビューアブル（ユーザーの視認範囲に広告が表示された状態）になった時点を発生日時として測定<br><br>

#### 指標の追加
新たに以下の指標を追加しました。<br>
<table>
<tr><th>日本語表示名</th><th>パフォーマンスレポートのフィールド名</th><th>統計情報のフィールド名</th><th>説明</th></tr> 
<tr><td>インプレッション数（旧）</td><td>IMPS_PREV</td><td>impsPrev</td><td>サーバーサイド計測によるインプレッション数。<br>
2019年6月30日以前のインプレッション数は、この指標でご確認ください。</td></tr>
<tr><td>クリック率（旧）</td><td>CLICK_RATE_PREV</td><td>clickRatePrev</td><td>サーバーサイド計測によるクリック率。<br>
2019年6月30日以前のクリック率は、この指標でご確認ください。</td></tr>
<tr><td>メジャードインプレッション数</td><td>MEASURED_IMPS</td><td>measuredImps</td><td>クライアントサイド計測による、ビューアブルインプレッション数の計測が可能なインプレッション数</td></tr>
<tr><td>メジャードインプレッション測定率</td><td>MEASURED_IMPS_RATE</td><td>measuredImpsRate</td><td>クライアントサイド計測による、インプレッションに対するメジャードインプレッションの測定率。</td></tr>
<tr><td>ビューアブルインプレッション率</td><td>VIEWABLE_IMPS_RATE</td><td>viewableImpsRate</td><td>クライアントサイド計測による、ビューアブルインプレッション数の計測が可能なインプレッション率。</td></tr>
<tr><td>ビューアブルクリック数</td><td>VIEWABLE_CLICK</td><td>viewableClicks</td><td>クライアントサイド計測による、ビューアブルインプレッションに対するクリック数。</td></tr>
<tr><td>ビューアブルクリック率</td><td>VIEWABLE_CLICK_RATE</td><td>viewableClickRate</td><td>クライアントサイド計測による、ビューアブルインプレッションに対するクリック率。</td></tr>
<tr><td>動画の10秒再生数</td><td>VIDEO_VIEWS_TO_10_SEC</td><td>videoViewsTo10Sec</td><td>動画が10秒以上再生された回数。<br>※課金が発生した動画再生数と同数になります。</td></tr>
</table>

##### 対象ウェブサービス  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [StatsService](./api_reference/services/StatsService.md)


### 5. 一部のAdTypeに関する名称の変更

YDNでの広告タイプの名称変更に伴い、一部のEnum名およびEntity名を変更しました。<br>
公開中の全バージョンのインポート用テンプレートおよび操作履歴でも、上記の名称に変更されています。なお、インポート用テンプレートを使ったインポートでは、従来の名称も利用可能です。<br>
※V201907においてレポートのフィルターでAdTypeを設定する場合は、変更後のAdType名称での設定が必要です。<br>

<table>
<tr><th>従来の従来のEnum名</th><th>従来のEntity名</th><th>変更後のEnum名</th><th>変更後のEntity名</th></tr> 
<tr><td>RESPONSIVE_AD</td><td>ResponsiveAd</td><td>RESPONSIVE_IMAGE_AD</td><td>ResponsiveImageAd</td></tr>
<tr><td>VIDEO_AD</td><td>VideoAd</td><td>RESPONSIVE_VIDEO_AD</td><td>ResponsiveVideoAd</td></tr>
<tr><td>NONE</td><td>None</td><td>BANNER_IMAGE_AD</td><td>BannerImageAd</td></tr>
</table>

##### 対象ウェブサービス
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [StatsService](./api_reference/services/StatsService.md)


### 6. アニメーションGIF画像のアップロード停止
アニメーションGIF画像のアップロード停止に伴い、DictionaryServiceのgetMediaAdFormatから「animation」フィールドを廃止しました。<br>

##### 対象ウェブサービス
 * [DictionaryService](./api_reference/services/DictionaryService.md)


### 7. 機能名および効果測定指標名の変更
一部の機能と効果測定指標の名称を変更しました。詳細は[こちら](https://promotionalads.yahoo.co.jp/support/release/677944.html)でご確認ください。<br>
これに伴い、統計情報（StatsService）で以下項目の名称を変更しました。<br>
 * totalClickCost　→　cost 
 * avgClickCost　→　avgCpc

##### 対象ウェブサービス
 * [StatsService](./api_reference/services/StatsService.md)


### 8. 保守対応
#### レポート関連サービスの統合
ReportServiceをReportDefinitionServiceと統合しました。<br>
以後のレポート定義とレポートジョブは、ReportDefinitionServiceで作成してください。詳細は以下の仕様ドキュメントでご確認ください。<br>

 * [リファレンス](./api_reference/services/ReportDefinitionService.md)<br>
 * [ベストプラクティス](./bestpractice/ydn_report.md)<br>

#### 定期レポートの実行を停止（公開中の全バージョン）
V201806以前に作成した定期レポートについて、intervalTypeをONETIMEに変更しました。これにより、定期レポートの実行はすべて停止されています。<br>

#### LocationServiceの廃止<br>
LocationServiceを廃止しました。


##### 対象ウェブサービス
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * LocationService ※V201907で廃止
 * ReportService　※V201907で廃止


## Serviceの変更による各Versionへの主な影響
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201903以前</th>
<th>V201907</th>
</tr>
<tr>
<td>FeedDataService</td>
<td>インターフェイス変更なし<br>
</td>
<td>・getUploadUrlで、デバッグモードを利用できる<br>
・getUploadStatusで、ファイルアップロード経路、エラー率、取り込み完了日時、定期アップロード用に追加されたステータスを取得できる<br>
</td>
</tr>
<tr>
<td>DictionaryService</td>
<td>インターフェイス変更なし</td>
<td>
・animation、idフィールドは取得できない<br>
・アスペクト比入稿向けの情報を取得できる<br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>PCブランドパネルのキャンペーンを作成、更新、取得、削除できる</td>
<td>
・PCブランドパネルのキャンペーンを作成、更新、取得、削除できる<br>
・BannerVideoAd広告（バナー（動画）広告）を作成、更新、取得、削除できる<br>
・名称変更後のAdTypeのEnum名、Entity名を取得できる<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>インターフェイス変更なし</td>
<td>クライアントサイド計測による新指標、及び名称が変更された旧指標を取得できる
</td>
</tr>

<tr>
<td>ReportDefinitionService</td>
<td>インターフェイス変更なし</td>
<td>・クライアントサイド計測による新指標、及び名称が変更された旧指標を取得できる<br>
・レポート定義の作成とジョブ登録を同時に行える<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>インターフェイス変更なし</td>
<td>廃止</td>
</tr>
<tr>
<td>LocationService</td>
<td>同じロケーションが一律で返却される（既存ユーザーへの影響はなし）</td>
<td>廃止</td>
</tr>

</tbody>
</table>


## YDN API V201812の提供終了について
以下の日程でYDN API V201812のサポートおよびシステムの提供を終了いたします。
* サポート終了日：2019年9月2日（月）
* システム終了日：2019年12月2日（月）
