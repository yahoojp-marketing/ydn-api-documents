# BulkService
BulkServiceは、バルクシートを使用した一括アップロードおよびダウンロード機能を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/BulkService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/BulkService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
バルクシートを使用した一括アップロードおよびダウンロードの機能を提供します。

#### 操作
1. getBulkDownloadで、一括ダウンロードをするデータをリクエストします。<br>
2. レスポンス内に含まれるdownloadBulkJobId（以下バルクID）を取得します。<br>
3. 取得したバルクIDを利用し、getBulkDownloadStatusでステータスを確認します。<br>
4. ステータスが"COMPLETED"ならば、レスポンスにダウンロードURLが戻ります。<br>
5. ステータスが"IN_PROGRESS"ならば、一定時間をおき再度ステータスの確認を実施します。<br>
6. ステータスが"SYSTEM_ERROR"であれば、ダウンロードURLは戻りません。再度一括ダウンロードのリクエストを実施します。<br>
7. ステータスが"TIMEOUT"（タイムアウト）ならば、再度一括ダウンロードのリクエストを実施します。<br>
　問題が解決しない場合は、弊社API担当者まで連絡をして下さい。

### ダウンロード処理の流れ
1. getUploadUrlで一括アップロード用のURLをリクエストします。<br>
2. アップロード用のURLがレスポンスとして戻されます。<br>
3. アップロードURLにバルクシートのアップロード処理を実施します。<br>
4.アップロード処理が完了すると、HTTPのレスポンス内に含まれる、uploadBulkJobId（以下バルクID）を取得します。<br>
5. uploadBulkJobIdをもとに、getBulkUploadStatusでアップロードのステータスを取得します。<br>
6. ステータス(uploadBulkJobStatu)が"IN_PROGRESS"ならば、アップロード処理の実行中です。<br>
　ステータスの確認を完了になるまで実施してください。<br>
7. ステータスが"COMPLETED"ならば、アップロード処理が正常に終了しました。<br>
　processingItemsCountで処理した件数を確認できます。<br>
　エラーの詳細を取得したい場合は、downloadBulkUploadFileUrlでバルクシートに処理結果が追記されたファイルをダウンロードできます。

### 注意事項
・セキュリティ上、ダウンロードURLは15分間のみ有効です。<br>
　URL取得後、15分経過した場合は、再度getBulkDownloadにて新規のダウンロードURLを取得して下さい。<br>
・ダウンロードファイルには、削除されたキャンペーン情報は含まれません。<br>
・getBulkDownloadでURLを作成した、IPアドレスでのみダウンロード処理が可能です。<br>
・1アカウントあたりのダウンロードジョブの制限数はありません。<br>
　ただし、一度に大量のダウンロードジョブを登録した場合は、処理待ちの状態となります。<br>
　一度に大量のバルクダウンロードは実施せず、複数回に分けて実施することをお勧めします。<br>

## getBulkDownload
### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | 一括取得する対象を定義します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignIds>2000000001</ns1:campaignIds>
        <ns1:campaignIds>2000000002</ns1:campaignIds>
        <ns1:adGroupIds>3000000001</ns1:adGroupIds>
        <ns1:adGroupIds>3000000002</ns1:adGroupIds>
        <ns1:adIds>4000000001</ns1:adIds>
        <ns1:adIds>4000000002</ns1:adIds>
        <ns1:campaignUserStatuses>ACTIVE</ns1:campaignUserStatuses>
        <ns1:adGroupUserStatuses>ACTIVE</ns1:adGroupUserStatuses>
        <ns1:adGroupAdUserStatuses>ACTIVE</ns1:adGroupAdUserStatuses>
        <ns1:adGroupAdApprovalStatuses>REVIEW</ns1:adGroupAdApprovalStatuses>
        <ns1:entityTypes>AD</ns1:entityTypes>
        <ns1:downloadBulkJob>
          <ns1:downloadBulkJobName>サンプルバルクジョブ1</ns1:downloadBulkJobName>
        </ns1:downloadBulkJob>
        <ns1:downloadType>REVIEW_AD</ns1:downloadType>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>ZIPPED_CSV</ns1:output>
        <ns1:encoding>UTF-8</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:entityTypes>ALL</ns1:entityTypes>
        <ns1:downloadBulkJob>
          <ns1:downloadBulkJobName>サンプルバルクジョブ2</ns1:downloadBulkJobName>
        </ns1:downloadBulkJob>
        <ns1:downloadType>CAMPAIGN</ns1:downloadType>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>ZIPPED_CSV</ns1:output>
        <ns1:encoding>UTF-8</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | 結果を格納するコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>BulkService</ns1:service>
      <ns1:remainingQuota>371</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>2.5132</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownloadResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:downloadBulkJobId>100001</ns1:downloadBulkJobId>
            <ns1:downloadBulkJobName>100001</ns1:downloadBulkJobName>
            <ns1:downloadBulkUserName>yahoo</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2012-04-03T12:00:00+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadBulkEndDate>2012-09-03T12:00:00+09:00</ns1:downloadBulkEndDate>
            <ns1:downloadJobStatus>IN_PROGRESS</ns1:downloadJobStatus>
            <ns1:progress>0</ns1:progress>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkDownloadStatus
### リクエスト
一括ダウンロードの処理状況を確認し、ダウンロード元のURLを取得します。downloadJobStatusがCOMPLETEDの場合、レスポンスにダウンロードURLが設定されます。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkDownloadStatusSelector](../data/BulkDownloadStatusSelector.md) | 取得する対象を定義します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkDownloadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:downloadBulkJobIds>100001</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobIds>100002</ns1:downloadBulkJobIds>
                <ns1:downloadBulkJobStatus>IN_PROGRESS</ns1:downloadBulkJobStatus>
                <ns1:downloadBulkJobStatus>COMPLETED</ns1:downloadBulkJobStatus>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>200</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
         </ns1:getBulkDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkDownloadStatus>
            <ns1:selector>
                <ns1:accountId>1111111111</ns1:accountId>
            </ns1:selector>
         </ns1:getBulkDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/BulkDownloadStatusPage.md) | 対象の処理状況を含むコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5"> 
  <SOAP-ENV:Header> 
    <ns1:ResponseHeader> 
      <ns1:service>BulkService</ns1:service> 
      <ns1:remainingQuota>129997</ns1:remainingQuota> 
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest> 
      <ns1:timeTakenMillis>3.995</ns1:timeTakenMillis> 
    </ns1:ResponseHeader> 
  </SOAP-ENV:Header> 
  <SOAP-ENV:Body> 
    <ns1:getBulkDownloadStatusResponse> 
      <ns1:rval> 
        <ns1:totalNumEntries>2</ns1:totalNumEntries> 
        <ns1:Page.Type>BulkDownloadStatusPage</ns1:Page.Type> 
        <ns1:values> 
          <ns1:operationSucceeded>true</ns1:operationSucceeded> 
          <ns1:downloadBulkJob> 
            <ns1:accountId>1000000001</ns1:accountId> 
            <ns1:downloadBulkJobId>100001</ns1:downloadBulkJobId> 
            <ns1:downloadBulkJobName>ダウンロードジョブ名1</ns1:downloadBulkJobName> 
            <ns1:downloadBulkUserName>EXTERNAL_API</ns1:downloadBulkUserName> 
            <ns1:downloadBulkStartDate>2012-04-03T12:52:04+09:00</ns1:downloadBulkStartDate> 
            <ns1:downloadBulkEndDate>2012-04-03T12:52:15+09:00</ns1:downloadBulkEndDate> 
            <ns1:progress>100</ns1:progress> 
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus> 
            <ns1:downloadBulkDownloadUrl>https://sample.api.yahooapis.jp/bulkDownload/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadBulkDownloadUrl> 
          </ns1:downloadBulkJob> 
        </ns1:values> 
        <ns1:values> 
          <ns1:operationSucceeded>true</ns1:operationSucceeded> 
          <ns1:downloadBulkJob> 
            <ns1:accountId>1000000001</ns1:accountId> 
            <ns1:downloadBulkJobId>100002</ns1:downloadBulkJobId> 
            <ns1:downloadBulkJobName>ダウンロードジョブ名2</ns1:downloadBulkJobName> 
            <ns1:downloadBulkUserName>EXTERNAL_API</ns1:downloadBulkUserName> 
            <ns1:downloadBulkStartDate>2012-04-03T12:53:08+09:00</ns1:downloadBulkStartDate> 
            <ns1:downloadBulkEndDate>2012-04-03T12:53:30+09:00</ns1:downloadBulkEndDate> 
            <ns1:progress>100</ns1:progress> 
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus> 
            <ns1:downloadBulkDownloadUrl>https://sample.api.yahooapis.jp/bulkDownload/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadBulkDownloadUrl> 
          </ns1:downloadBulkJob> 
        </ns1:values> 
      </ns1:rval> 
    </ns1:getBulkDownloadStatusResponse> 
  </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```
## getUploadUrl
### リクエスト
アップロード対象になるURLを定義します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getUploadUrl>
            <ns1:accountId>111111111</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getUploadUrl>
            <ns1:accountId>111111111</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [UploadUrlValue](../data/UploadUrlValue.md) | 結果を格納するコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>BulkService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
       <ns1:getUploadUrlResponse> 
           <ns1:rval> 
               <ns1:accountId>1000000001</ns1:accountId> 
               <ns1:acceptableUploadStatus>true</ns1:acceptableUploadStatus> 
               <ns1:uploadUrl>https://sample.api.yahooapis.jp/bulkUpload/V5/upload/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:uploadUrl> 
           </ns1:rval> 
       </ns1:getUploadUrlResponse> 
   </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## getBulkUploadStatus
### リクエスト
アップロード状況を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [BulkUploadStatusSelector](../data/BulkUploadStatusSelector.md) | 一括取得する対象を定義します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>1111111111</ns1:accountId>
                <ns1:uploadBulkJobIds>2222222222</ns1:uploadBulkJobIds>
                <ns1:uploadBulkJobStatus>IN_PROGRESS</ns1:uploadBulkJobStatus>
                <ns1:output>ZIPPED_XML</ns1:output>
                <ns1:encoding>UTF-8</ns1:encoding>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>1111111111</ns1:accountId>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [BulkUploadStatusPage](../data/BulkUploadStatusPage.md)|結果を格納するコンテナです。|error|[Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>BulkService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getBulkUploadStatusResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>BulkUploadStatusPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:uploadBulkJob>
                        <ns1:accountId>1111111111</ns1:accountId>
                        <ns1:uploadBulkJobId>2222222222</ns1:uploadBulkJobId>
                        <ns1:uploadBulkJobName>1</ns1:uploadBulkJobName>
                        <ns1:uploadBulkUserName>EXTERNAL_API</ns1:uploadBulkUserName>
                        <ns1:uploadBulkStartDate>2012-10-18T15:29:11+09:00</ns1:uploadBulkStartDate>
                        <ns1:uploadBulkEndDate>2012-10-18T15:29:20+09:00</ns1:uploadBulkEndDate>
                        <ns1:uploadBulkJobStatus>COMPLETED</ns1:uploadBulkJobStatus>
                        <ns1:processingItemsCount>
                            <ns1:campaignCount>0</ns1:campaignCount>
                            <ns1:adGroupCount>0</ns1:adGroupCount>
                            <ns1:adGroupAdCount>0</ns1:adGroupAdCount>
                            <ns1:adGroupTargetCount>0</ns1:adGroupTargetCount>
                            <ns1:mediaCount>0</ns1:mediaCount>
                            <ns1:campaignErrorCount>18</ns1:campaignErrorCount>
                            <ns1:adGroupErrorCount>0</ns1:adGroupErrorCount>
                            <ns1:adGroupAdErrorCount>0</ns1:adGroupAdErrorCount>
                            <ns1:adGroupTargetErrorCount>0</ns1:adGroupTargetErrorCount>
                            <ns1:mediaErrorCount>0</ns1:mediaErrorCount>
                        </ns1:processingItemsCount>
                        <ns1:progress>100</ns1:progress>
                        <ns1:downloadBulkUploadFileUrl>https://sample.api.yahooapis.jp/bulkUpload/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadBulkUploadFileUrl>
                    </ns1:uploadBulkJob>
                </ns1:values>
            </ns1:rval>
        </ns1:getBulkUploadStatusResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
