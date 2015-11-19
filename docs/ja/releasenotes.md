# リリースノート
## リリースバージョン　　
5.2 (WSDLバージョン: 5.2.0)

## バージョンアップの種類　　
マイナーバージョンアップ 

## 本リリースの主な内容
#### 1. キャリアターゲティング機能の追加 
広告グループ単位でキャリアを指定してターゲティングを行うことができるようになりました。<br>

* 対象ウェブサービス  
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)

* 対象データオブジェクト  
 * 各Service下にあるデータオブジェクトよりご確認ください。
  
* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。
 
#### 2. サイトリターゲティングタグ機能の追加 
サイトリターゲティングのタグに関する機能で、以下の仕様が追加されました。<br>
　・ タグの作成<br>
　・ タグの詳細情報の取得<br>
 
* 対象ウェブサービス  
 * [RetargetingTagService](/docs/ja/api_reference/services/RetargetingTagService.md)
  
* 対象データオブジェクト  
 * 対象になるデータオブジェクトはありません。

* 対象Enumerations  
 * 各Service下にあるデータオブジェクトよりご確認ください。

## Serviceの変更による各Versionへの影響
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.1以前</p></th>
    <th valign="top"><p>Ver.5.2</p></th>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>変更はございません。</p></td>
    <td><p>・ 広告グループ情報（AdGroup）にモバイルキャリア（smartDeviceCarriers）フィールドを追加しました。<br>
    ・ デバイスキャリア選択のEnum（SmartDeviceCarrier）を追加しました。<br>
    ・ キャリア種別の設定ができないデバイスを選択した場合の エラーを追加しました。</p></td>
  </tr>
  <tr>
    <td><p>RetargetingTagService</p></td>
    <td><p>変更はございません。<br></p></td>
    <td><p>・ リターゲティングタグ情報（RetargetingTag）にタグ詳細（tag）フィールドを追加しました。<br>
    ・ リターゲティングタグ操作対象のタグ情報（RetargetingTagOperation）と実行結果の情報（RetargetingTagReturnValue）を追加しました。</p></td>
  </tr></tbody>
</table>

## YDN API Ver.4.6とVer.4.7のサポート終了予定日
YDN API Ver.4.6とVer.4.7は、2015年12月25日（金）にサポート終了予定です。 
