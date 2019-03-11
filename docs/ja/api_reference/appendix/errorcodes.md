# SOAPエラーコード
### エラー処理概要
SOAPリクエストが成功した場合、YDN APIは HTTP 200 OKというレスポンスコードとSOAPのレスポンスを返します。<br> SOAPリクエストの処理中にエラーが発生した場合、YDN API はエラーコードが含まれるメッセージを返します。<br>
詳しくは[Error](/docs/ja/api_reference/data/Common/Error.md), [ErrorDetail](/docs/ja/api_reference/data/Common/ErrorDetail.md)を確認してください。  
   
### エラーレスポンスサンプル

SOAPのエラーレスポンスには、SOAPFault、全体エラー、部分エラーがあります。以下で各レスポンスについて説明します。

#### SOAPFault

WSDL や SOAP 構文違反、システムエラー、認証エラーなどは、SOAPFaultが返却されます。<br>
エラーコードは `<faultcode>` に、エラーメッセージは `<faultstring>` に記述されます。<br>
詳細なエラー原因が `<detail>` に記述される場合もあります。

以下は[AccountService](/docs/ja/api_reference/services/AccountService.md)でログインに失敗したときのエラーレスポンス例です。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>110006</faultcode>
      <faultstring>Can not login for apiAccountId.</faultstring>
      <faultactor/>
      <detail>
        <requestKey>apiAccountId</requestKey>
        <requestValue>xxxx-xxxx-xxxx-xxxx</requestValue>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

なお、APIのバージョンごとにSOAPFaultレスポンスの構造が異なります。V201806では上記レスポンスになります。

#### 全体エラー

SOAPFaultには含まれないが、リクエストの制約等によりリクエスト全体が失敗した場合は、全体エラーが返却されます。<br>
SOAPリクエストの各 `<operand>` 内の制約によりリクエストに失敗した場合は、部分エラーが返却されます。

以下は[AccountService](/docs/ja/api_reference/services/AccountService.md)で、 `Paging` の `numberResults` の値が不正な場合のエラーレスポンス例です。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Account" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>AccountService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse>
      <ns2:error>
        <ns1:code>120003</ns1:code>
        <ns1:message>Invalid number format.</ns1:message>
        <ns1:detail>
          <ns1:requestKey>numberResults</ns1:requestKey>
          <ns1:requestValue>1000000</ns1:requestValue>
        </ns1:detail>
      </ns2:error>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 部分エラー

`<operand>` 内の各要素の制約等によりエラーが発生した場合は、部分エラーが返却されます。<br>
部分エラーは、各 `<operand>` ごとにエラーが発生したかについて返却します。<br>
なお、一回のSOAPリクエストで複数の `<operand>` を送るなど、複数の操作を要求するリクエストを送った場合、`<operationSucceeded>` の値が `true` や `false` である `<values>` が混在するエラーレスポンスになる場合もあります。

以下は[ReportService](/docs/ja/api_reference/services/ReportService.md)で存在しない `reportId` を指定した場合のエラーレスポンス例です。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Report" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse>
      <ns2:rval>
        <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns2:values>
          <ns1:operationSucceeded>false</ns1:operationSucceeded>
          <ns1:error>
            <ns1:code>120022</ns1:code>
            <ns1:message>Deactivated.</ns1:message>
            <ns1:detail>
              <ns1:requestKey>reportId</ns1:requestKey>
              <ns1:requestValue>1234567890</ns1:requestValue>
            </ns1:detail>
          </ns1:error>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### エラーコード
エラーや問題が発生した時、SOAPエラーコードとエラーの内容の一覧です。

#### 共通エラー
##### Service
全サービス共通 
  
コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
110001 | Invalid Request.  | リクエストが無効です。
110002 | Frequency limit exceeded. Please try your request again later.  | 回数の制限を超えました。後で再試行してください。
110003 | Invalid location.  | ロケーションが無効です。
110004 | Quota exceeded. service = %s , Quota = %s | クォータの制限を超えました。 service = %s , Quota = %s
110005 | Not a valid id.  | IDが有効ではありません。
110006 | Can not login for %s.  | %sではログインできません。
110007 | Invalid method.  | methodが無効です。
110008 | Invalid selector.  | selectorが無効です。
110009 | Invalid operations.  | operationsが無効です。
110010 | Invalid operator.  | operatorが無効です。
119999 | An internal error has occurred.  | 内部エラーが発生しました。
120001 | Required.  | 必須です。
120002 | Invalid value.  | 値が無効です。
120003 | Invalid number format.  | 数値形式が無効です。
120004 | Invalid string format.  | 文字列形式が無効です。
120005 | Invalid date format.  | 日付形式が無効です。
120006 | Invalid enum.  | Enum項目の値が未定義です。
120007 | Invalid step value.  | 刻み値が無効です。
120008 | Invalid url format.  | URL形式が無効です。
120009 | Invalid email format.  | 電子メール形式が無効です。
120010 | Too many items.  | 項目の数が多すぎます。
120011 | Too little items.  | 項目の数が少なすぎます。
120012 | Too many values.  | 値の数が多すぎます。
120013 | Too little values.  | 値の数が少なすぎます。
120014 | Too long values.  | 値が長すぎます。
120015 | Too short value.  | 値が短すぎます。
120016 | Too large value.  | 値が大きすぎます。
120017 | Too small value.  | 値が小さすぎます。
120018 | Duplicate values.  | 値が重複しています。
120019 | Can not set empty.  | 空を設定することはできません。
120020 | Can not set value.  | 値を設定することができません。
120021 | Insufficient search parameters.  | 検索パラメーターが不足しています。
120022 | Deactivated.  | アクティブではありません。
120023 | Over limit.  | 制限を超えています。
120024 | Invalid relation.  | 関係が無効です。
120025 | Out of range.  | 有効範囲ではありません。
120026 | Status error.  | ステータスエラーです。
120029 | This value is registered.  | この値は登録済みです。


#### 入稿に関連するエラー
##### Service
[RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
210001 | Selected value is not approved to update.  | 選択した内容は更新が許可されておりません。 
210002 | Cannot update from the dependency.| 依存関係があるため、更新できません。
210003 | A function is not permitted this account.| カスタムオーディエンスが利用できないアカウントです。

##### Service
[AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220016 | Advance setting was made to the product or targeting that is not available.  | 指定された広告商品またはターゲティングの値では拡張設定できません。
220018 | This Target settings is unavailable.  | キャンペーンの商品種別が、ターゲティング設定できない商品です。
220141 | Can not set bidMultiplier. | 入札価格調整率が設定できないターゲティングです。
															
##### Service
[BulkService](/docs/ja/api_reference/services/BulkService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220001 | Over limit of uncompleted bulk download job.  | 未完了のバルクダウンロードジョブ登録数が制限を超えています。
220002 | Over limit of bulk download job.  | バルクダウンロードジョブ登録数が制限を超えています。
220003 | Creating bulk downloadUrl is failed.  | バルクダウンロードURL作成に失敗。
220004 | Bulk download URL has expired.  | バルクダウンロードURLの有効期限が過ぎている。
220005 | Invalid bulk download request.  | バルクダウンロードURLが不正。
220019 | Another job is in progress.  | 別のジョブを実行中です。

##### Service
[CampaignService](/docs/ja/api_reference/services/CampaignService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220007 | Unavailable the adProductType.  | 指定された広告掲載方式は購入できません。
220014 | Budget is lower than bidding price.  | 予算額が入札価格を下回っています。
220121 | Frequency setting was made to the product that is not available.  | 指定された広告商品ではフリークエンシー設定できません。 
220122 | Unavailable combination of frequency settings.  | フリークエンシー設定の組み合わせが不正です。 
220123 | Unavailable conversion optimizer.  | コンバージョンオプティマイザーの設定が出来ない商品です。
220124 | Disable conversion optimizer.  | コンバージョンオプティマイザーの有効設定が不正です。 
220143 | Invalid appId.  | アプリIDのフォーマットが不正です。 
220145 | Invalid conversion optimizer. | コンバージョン最適化は登録時に設定できません。

##### Service
[AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220006 | Unavailable value.  | 利用できない値が入力されています。
220008 | Under examination.  | 編集データが審査中です。
220009 | Ad type you chose does not support the specified adProductType.  | キャンペーンで設定した広告商品種別では指定出来ない広告タイプが入力されています。
220010 | Can not specify APP and OS for the device type.  | 指定されたデバイスでは、APP、OSは指定できません。
220015 | Bidding price is higher than campaign budget.  | 入札価格がキャンペーン予算を超えています。
220113 | Unsupported ad product type.  | キャンペーンの配信方法（AdproductType）が、画像紐づけ不可となっています。
220114 | Invalid ad style.  | 掲載フォーマットが無効です。 
220115 | Unavailable aspect ratio of an image. |指定したピクセルサイズをご利用いただけません。
220126 | Invalid pattern in ad type and layout.  | 広告タイプと広告レイアウトの掛け合わせパターンが合っておりません。 
220127 | Invalid ad type.  | レスポンシブと広告枠サイズ固定の広告タイプ以外は利用できない項目です。 
220128 | Invalid color set ID.  | カラーセットIDが不正です。 
220133 | Not allowed to set impression beacon url. | 広告効果測定ツール提供企業など外部との連係許可がないため、<br>インプレッションビーコンURLの設定はできません。 
220301 | Over limit to delivered ad. | 配信設定中の広告の件数が上限を超えています。
220302 | Over limit to ad under account. | アカウント配下の広告の件数が上限を超えています。
220321 | Invalid displayUrl. | キャンペーンのデバイス種別では設定できない表示URLが入力されています。 
220322 | Invalid tracking parameter. | 無効な文字列（無効なトラッキングパラメータなど）が存在します。
220323 | Unavailable tracking parameter for ad. | 広告商品に対応していないトラッキングパラメータが存在します。
220324 | Unavailable tracking parameter for ad. | YDNと未連携の広告効果測定ツールのため利用できない、または提供終了済みのトラッキングパラメータが存在します。

##### Service
[AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220123 | Unavailable conversion optimizer.  | コンバージョンオプティマイザーの設定が出来ない商品です。 
220124 | Disable conversion optimizer.  | コンバージョンオプティマイザーの有効設定が不正です。 
220125 | Unavailable the dynamicImageExtensions.  | ターゲティング以外の広告商品の場合、画像自動付与フラグの設定はできません。 
220132 | Cannot set the carrier type. | 選択したデバイスは、キャリアの選択ができません。
220138 | Unsupported Os Version. | OSバージョンが不正です。
220139 | Invalid Os Version. | アプリキャンペーンで指定したOSとターゲティングのOSバージョンが適合しません。
220140 | Invalid device type. | キャンペーンタイプがAPPの場合、DeviceTypeはSMARTPHONE、またはTABLETでなければいけません。
220146 | Invalid target cpa value. | 自動入札の時は、目標CPAを1以上に設定してください。
220310 | Over limit to ad group under account. | アカウント配下の広告グループの件数が上限を超えています。

##### Service
[MediaService](/docs/ja/api_reference/services/MediaService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220102 | Over limit of file size.  | 画像ファイルのサイズが上限を超えています。
220103 | Unsupported filename extension.  | 画像ファイルの拡張子がGIF/JPEGと異なります。
220104 | Only GIF89a is supported.  | GIFファイルの規格がGIF89aではありません。
220105 | Animated GIF pixel size does not fit.  | アニメーションGIF形式の規定ピクセルサイズではないため、登録されませんでした。
220106 | Only RGB is supported.  | 画像ファイルの色空間がRGBではありません。
220107 | Invalid aspect ratio of an image.  | 画像ファイルの広告サイズがサポートされていません。
220108 | A function is not permitted this account.  | 画像入稿の権限がありません。
220109 | Duplicate image file.  | 画像ファイルがすでに登録されています。
220110 | Creating media downloadUrl is failed.  | 画像ファイルのダウンロードURLの生成に失敗しました。
220111 | Media download URL has expired.  | 画像ファイルのダウンロードURLの有効期限が過ぎています。
220112 | Invalid media download request.  | 画像ファイルのダウンロードURLの復号に失敗しました。 
220116 | Unsupported file format.  | 画像ファイルのファイル形式が許容されていません。 
220117 | Inifinite loop setting is not allowed for Animated GIF.  | 無限ループのアニメーションGIFです。
220118 | Animated GIF movie time is too long (Max 15 seconds).  | 15秒より長いアニメーションが設定されています。
220119 | Submitted file is transparent GIF.  | 画像ファイルが透過GIFです。
220120 | Submitted file is 0 byte.  | 画像ファイルが0byteです。
220129 | Invalid combination in user status and logo flag. | 配信フラグとロゴフラグの組み合わせが無効です。
220130 | Invalid combination in logo flag and media format. | ロゴフラグと画像フォーマットの組み合わせが無効です。
220131 | Field value is not updatable. | 更新不可項目に変更が実施されました
220135 | Invalid relation in thumbnail flag and media format. | サムネイルフラグと画像フォーマットの組み合わせが無効です。

##### Service
[VideoService](/docs/ja/api_reference/services/VideoService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
220201 | Creating video downloadUrl is failed. | 動画ダウンロードURLの生成に失敗しました。
220202 | Invalid video download request. | 動画ダウンロードURLが不正です。
220203 | Video download URL has expired. | 動画ダウンロードURLの期限が切れています。
220204 | Creating video uploadUrl is failed. | 動画アップロードURLの生成に失敗しました。
220205 | Invalid video upload request. | 動画アップロードURLが不正です。
220206 | Video upload URL has expired. | 動画アップロードURLの期限が切れています。
220207 | Invalid aspect ratio of an video. | 動画ファイルのピクセルサイズが間違っています。
220208 | Duplicate video file. | すでに登録済みの動画ファイルが指定されています。
220209 | Video play time is too long (Max 60 seconds). | 再生時間が60秒を超える動画が指定されています。
220210 | Video play time is too short (Min 5 seconds). | 再生時間が5秒未満の動画が指定されています。
220211 | Invalid video codec. | 動画ファイルの映像コーデックが不正です。
220212 | Invalid audio codec. | 動画ファイルの音声コーデックが不正です。
220213 | Invalid major brand. | 動画ファイルのメジャーブランドが不正です。
220214 | Invalid video index. | moov atomが動画ファイルの先頭にありません。
220215 | Over limit of frame rate. | 動画ファイルのフレームレートが上限値を超えています。
220216 | Over limit of audio volume. | 動画ファイルの音量が上限値を超えています。


### レポート処理に関連するエラー
##### Service
[ReportService](/docs/ja/api_reference/services/ReportService.md),[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
240001 | Over limit of uncompleted report download job.  | 未完了のレポートダウンロードジョブ登録数が制限を超えています。
240002 | Over limit of report download job.  | レポートダウンロードジョブ登録数が制限を超えています。
240003 | Invalid division specified.  | 指定された分割指定が無効です。
240004 | Invalid segment match pattern.  | セグメントの組み合わせが無効です。
240005 | Invalid field item.  | フィールド項目が無効です。
240006 | Invalid sort item.  | ソート項目が無効です。
240007 | Creating report downloadUrl is failed.  | レポートダウンロードURL作成に失敗。
240008 | Report download URL has expired.  | レポートダウンロードURLの有効期限が過ぎています。
240009 | Invalid report download request.  | レポートダウンロードURLが不正です。
240010 | Over limit of report template number.  | 登録されるテンプレート登録数が上限を超えています。 
250001 | Invalid combination in Template settings. | テンプレートフラグが指定されている場合、集計期間に「任意日付」は選択できません。
250002 | Invalid field settings. | フィールドに指定できない組み合わせ項目が設定されています。
250003 | Invalid combination in report date settings. | 指定されたレポート作成のタイミングでは、指定日を設定できません。
250004 | Invalid combination in date range type. | 指定されたレポートの集計期間では、「任意日付」は選択できません。
250005 | Invalid filter`s field. | フィルターに指定できないフィールドを指定しています。

