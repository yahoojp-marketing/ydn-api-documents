# SOAPエラーコード
### エラー処理概要
SOAPリクエストが成功した場合、YDN APIは HTTP 200 OKというレスポンスコードとSOAPのレスポンスを返します。<br> SOAPリクエストの処理中にエラーが発生した場合、YDN API はエラーコードが含まれるメッセージを返します。<br>
詳しくは[Error](/docs/ja/api_reference/data/Common/Error.md), [ErrorDetail](/docs/ja/api_reference/data/Common/ErrorDetail.md)を確認してください。  
   
### エラーレスポンスサンプル

SOAPのエラーレスポンスとして、SOAPFault、全体エラー、部分エラーについて説明いたします。

#### SOAPFault

WSDL や SOAP 構文違反、システムエラー、認証エラーなどは、SOAPFaultレスポンスとなります。<br>
なお、SOAPFaultはサービスによって以下のどちらかの形式のレスポンスになります。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>110006</faultcode>
      <faultstring>Can not login.</faultstring>
      <faultactor/>
      <detail>
        <requestKey>apiAccountId</requestKey>
        <requestValue>xxxx-xxxx-xxxx-xxxx</requestValue>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header/>
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>SOAP-ENV:Client</faultcode>
      <faultstring xml:lang="en">110006:Can not login.</faultstring>
      <detail>
        <ApiExceptionFault xmlns="http://im.yahooapis.jp/V201812/Account">{"details":[{"key":"license","value":["xxxx-xxxx-xxxx-xxxx"]},{"key":"apiAccountId","value":["xxxx-xxxx-xxxx-xxxx"]}]}</ApiExceptionFault>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 全体エラー

SOAPFaultではないものの、リクエストの制約等によりリクエスト全体が失敗した場合は全体エラーがレスポンスされます。<br>
なお、SOAPリクエストの各 `<operand>` 内の制約によりリクエストに失敗した場合、部分エラーがレスポンスされます。

以下は[AccountService](/docs/ja/api_reference/services/AccountService.md)で `Paging` の `numberResults` の値が不正な場合のエラーレスポンス例です。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header xmlns:ns1="http://im.yahooapis.jp/V201812/Account" xmlns:ns2="http://im.yahooapis.jp/V201812">
    <ns1:ResponseHeader>
      <ns2:service>Account</ns2:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getResponse xmlns="http://im.yahooapis.jp/V201812/Account" xmlns:ns1="http://im.yahooapis.jp/V201812">
      <error>
        <ns1:code>F0001</ns1:code>
        <ns1:message>Invalid format.</ns1:message>
        <ns1:detail>
          <ns1:requestKey>selector/paging/numberResults</ns1:requestKey>
          <ns1:requestValue>1000000</ns1:requestValue>
        </ns1:detail>
      </error>
    </getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 部分エラー

`<operand>` 内の各要素の制約等によりエラーが発生した場合、部分エラーがレスポンスされます。<br>
部分エラーは全体エラーと異なり、各 `<operand>` ごとにエラーが発生したかどうかを返します。<br>
なお、一回のSOAPリクエストで複数の `<operand>` を送るなど、複数の操作を要求するようなリクエストを送った場合、`<operationSucceeded>` の値が `true` であったり `false` であったりする `<values>` が混在するエラーレスポンスになる場合もあります。

以下は[ReportService](/docs/ja/api_reference/services/ReportService.md)で存在しない `reportId` を指定した場合のエラーレスポンス例です。

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header xmlns:ns1="http://im.yahooapis.jp/V201812/Report" xmlns:ns2="http://im.yahooapis.jp/V201812">
    <ns1:ResponseHeader>
      <ns2:service>Report</ns2:service>
      <ns2:timeTakenSeconds>0.1234</ns2:timeTakenSeconds>
      <ns2:requestTime>1234567890</ns2:requestTime>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns3:mutateResponse xmlns:ns2="http://im.yahooapis.jp/V201812" xmlns:ns3="http://im.yahooapis.jp/V201812/Report">
      <ns3:rval>
        <ns2:ListReturnValue.Type>ReportReturnValue</ns2:ListReturnValue.Type>
        <ns2:Operation.Type>ADD</ns2:Operation.Type>
        <ns3:values>
          <ns2:operationSucceeded>false</ns2:operationSucceeded>
          <ns2:error>
            <ns2:code>I0001</ns2:code>
            <ns2:message>Deactivated Id.</ns2:message>
            <ns2:detail>
              <ns2:requestKey>reportId</ns2:requestKey>
              <ns2:requestValue>1234567890</ns2:requestValue>
            </ns2:detail>
          </ns2:error>
        </ns3:values>
      </ns3:rval>
    </ns3:mutateResponse>
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
110005 | Not a valid id.  | IDが有効ではありません。
110006 | Can not login.  | ログインできません。
110007 | Invalid method.  | methodが無効です。
110008 | Invalid selector.  | selectorが無効です。
110009 | Invalid operations.  | operationsが無効です。
110010 | Invalid operator.  | operatorが無効です。
118888 | Out of service. | APIがメンテナンス中、またはご利用できません。
119999 | An internal error has occurred.  | 内部エラーが発生しました。
120020 | Can not set value.  | 値を設定することができません。
120026 | Invalid account. | アカウントが無効です。
F0001  | Invalid format.   | 値の形式が不正です。
F0002  |	Invalid file format. | アップロードファイルの形式が不正です。
R0001 | Require. | 必須です。
V0001 | Invalid value. | 値が無効です。
V0002 | Empty file. | アップロードファイルが0byteです。
V0003 | Over limit of the file. | アップロードファイルサイズが上限を超過しています。
L0001 | Lower list size. | 配列の要素数が下限値を下回っています。
L0002 | Over list size. | 配列の要素数が上限値を超過しています。
U0001 | Url has expired. | アップロードURLまたはダウンロードURLの有効期限が切れています。
U0002 | Invalid url. | アップロードURLまたはダウンロードURLが不正です。
S0001 | Invalid Status. | ステータスが無効です。
I0001 | Deactivated Id. | IDが無効です。
D0001 | Duplicate. | 一意な値が重複しています。
RL001 | Invalid relation. | リクエストの関連性が矛盾しています。<br> たとえば、開始＞終了の日付指定を行なっているなど
LT001 | Over limit. | 登録できる上限値を超過しています。


#### 入稿に関連するエラー
##### Service
[RetargetingListService](/docs/ja/api_reference/services/RetargetingListService.md),<br>
[AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md),<br>
[BulkService](/docs/ja/api_reference/services/BulkService.md),<br>
[CampaignService](/docs/ja/api_reference/services/CampaignService.md),<br>
[AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md),<br>
[AdGroupService](/docs/ja/api_reference/services/AdGroupService.md),<br>
[MediaService](/docs/ja/api_reference/services/MediaService.md),<br>
[VideoService](/docs/ja/api_reference/services/VideoService.md),<br>
[CampaignLabelService](/docs/ja/api_reference/services/CampaignLabelService.md),<br>
[AdGroupLabelService](/docs/ja/api_reference/services/AdGroupLabelService.md),<br>
[AdGroupAdLabelService](/docs/ja/api_reference/services/AdGroupAdLabelService.md),<br>
[LabelService](/docs/ja/api_reference/services/LabelService.md)<br>
[FeedDataService](/docs/ja/api_reference/services/FeedDataService.md)<br>
[FeedFtpRequestService](/docs/ja/api_reference/services/FeedFtpRequestService.md)<br>
[FeedFtpService](/docs/ja/api_reference/services/FeedFtpService.md)<br>
[FeedHolderService](/docs/ja/api_reference/services/FeedHolderService.md)<br>
[FeedSetService](/docs/ja/api_reference/services/FeedSetService.md)<br>

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
210001 | Selected value is not approved to update.  | 選択した内容は更新が許可されておりません。 
210002 | Cannot update from the dependency.| 依存関係があるため、更新できません。
210003 | A function is not permitted this account.| 利用が許可されていないアカウントです。 
220007 | Unavailable the adProductType.  | 指定された広告掲載方式は購入できません。
220009 | Ad type you chose does not support the specified adProductType.  | キャンペーンで設定した広告商品種別では指定出来ない広告タイプが入力されています。
220010 | Can not specify APP and OS for the device type.  | 指定されたデバイスでは、APP、OSは指定できません。
220014 | Budget is lower than bidding price.  | 予算額が入札価格を下回っています。
220015 | Bidding price is higher than campaign budget.  | 入札価格がキャンペーン予算を超えています。
220016 | Advance setting was made to the product or targeting that is not available.  | 指定された広告商品またはターゲティングの値では拡張設定できません。
220018 | This Target settings is unavailable.  | キャンペーンの商品種別が、ターゲティング設定できない商品です。
220019 | Another job is in progress.  | 別のジョブを実行中です。
220103 | Unsupported filename extension.  | 画像ファイルの拡張子がGIF/JPEGと異なります。
220104 | Only GIF89a is supported.  | GIFファイルの規格がGIF89aではありません。
220105 | Animated GIF pixel size does not fit.  | アニメーションGIF形式の規定ピクセルサイズではないため、登録されませんでした。
220106 | Only RGB is supported.  | 画像ファイルの色空間がRGBではありません。
220107 | Invalid aspect ratio of an image.  | 画像ファイルの広告サイズがサポートされていません。
220113 | Unsupported ad product type.  | キャンペーンの配信方法（AdproductType）が、画像紐づけ不可となっています。
220115 | Unavailable aspect ratio of an image. |指定したピクセルサイズをご利用いただけません。
220117 | Inifinite loop setting is not allowed for Animated GIF.  | 無限ループのアニメーションGIFです。
220118 | Animated GIF movie time is too long (Max 15 seconds).  | 15秒より長いアニメーションが設定されています。
220119 | Submitted file is transparent GIF.  | 画像ファイルが透過GIFです。
220121 | Frequency setting was made to the product that is not available.  | 指定された広告商品ではフリークエンシー設定できません。 
220122 | Unavailable combination of frequency settings.  | フリークエンシー設定の組み合わせが不正です。
220123 | Unavailable conversion optimizer.  | コンバージョンオプティマイザーの設定が出来ない商品です。
220124 | Disable conversion optimizer.  | コンバージョンオプティマイザーの有効設定が不正です。 
220125 | Unavailable the dynamicImageExtensions.  | ターゲティング以外の広告商品の場合、画像自動付与フラグの設定はできません。 
220129 | Invalid combination in user status and logo flag. | 配信フラグとロゴフラグの組み合わせが無効です。
220130 | Invalid combination in logo flag and media format. | ロゴフラグと画像フォーマットの組み合わせが無効です。
220131 | Field value is not updatable. | 更新不可項目に変更が実施されました
220132 | Cannot set the carrier type. | 選択したデバイスは、キャリアの選択ができません。
220133 | Not allowed to set impression beacon url. | 広告効果測定ツール提供企業など外部との連係許可がないため、<br>インプレッションビーコンURLの設定はできません。 
220135 | Invalid relation in thumbnail flag and media format. | サムネイルフラグと画像フォーマットの組み合わせが無効です。
220141 | Can not set bidMultiplier. | 入札価格調整率が設定できないターゲティングです。
220207 | Invalid aspect ratio of an video. | 動画ファイルのピクセルサイズが間違っています。
220209 | Video play time is too long (Max 60 seconds). | 再生時間が60秒を超える動画が指定されています。
220210 | Video play time is too short (Min 5 seconds). | 再生時間が5秒未満の動画が指定されています。
220211 | Invalid video codec. | 動画ファイルの映像コーデックが不正です。
220212 | Invalid audio codec. | 動画ファイルの音声コーデックが不正です。
220213 | Invalid major brand. | 動画ファイルのメジャーブランドが不正です。
220214 | Invalid video index. | moov atomが動画ファイルの先頭にありません。
220215 | Over limit of frame rate. | 動画ファイルのフレームレートが上限値を超えています。
220216 | Over limit of audio volume. | 動画ファイルの音量が上限値を超えています。
220301 | Over limit to delivered ad. | 配信設定中の広告の件数が上限を超えています。
220302 | Over limit to ad under account. | アカウント配下の広告の件数が上限を超えています。
220310 | Over limit to ad group under account. | アカウント配下の広告グループの件数が上限を超えています。
220311 | Over limit to label under account. | アカウント配下のラベルの件数が上限を超えています。
220322 | Invalid tracking parameter. | 無効な文字列（無効なトラッキングパラメータなど）が存在します。
220323 | Tracking parameter  is not available for this type of ad distribution. | 指定された広告掲載方式に対し、トラッキングパラメータは対応していません。
220324 | Entered tracking parameter cannot be used. | 入力されたトラッキングパラメータは利用できません。
220325 | Invalid relation of video and thumbnail format. | 動画とサムネイルのフォーマットが異なります。
220326 | Not allowed to set video beacon url. | 動画視聴用のbeacon urlを設定する権限がありません。
220328 | Invalid condition, which matches all items.| 全商品が該当する条件のため、設定できません。

### レポート処理に関連するエラー
##### Service
[ReportService](/docs/ja/api_reference/services/ReportService.md),<br>
[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

コード         | メッセージ                  | 説明                   
-------------- | --------------------------- | ---------------------------
240001 | Over limit of uncompleted report download job.  | 未完了のレポートダウンロードジョブ登録数が制限を超えています。
240003 | Invalid division specified.  | 指定された分割指定が無効です。
240004 | Invalid segment match pattern.  | セグメントの組み合わせが無効です。
240005 | Invalid field item.  | フィールド項目が無効です。
240006 | Invalid sort item.  | ソート項目が無効です。
240010 | Over limit of report template number.  | 登録されるテンプレート登録数が上限を超えています。 
250001 | Invalid combination in Template settings. | テンプレートフラグが指定されている場合、集計期間に「任意日付」は選択できません。
250002 | Invalid field settings. | フィールドに指定できない組み合わせ項目が設定されています。
250003 | Invalid combination in report date settings. | 指定されたレポート作成のタイミングでは、指定日を設定できません。
250004 | Invalid combination in date range type. | 指定されたレポートの集計期間では、「任意日付」は選択できません。
250005 | Invalid filter`s field. | フィルターに指定できないフィールドを指定しています。

