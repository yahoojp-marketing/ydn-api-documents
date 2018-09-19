# BulkService
BulkServiceは、バルクシートを使用した一括アップロードおよびダウンロード機能を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201809/BulkService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201809/BulkService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201809/Bulk
#### サービス概要
バルクシートを使用した一括アップロードおよびダウンロードの機能を提供します。

#### ダウンロード処理の流れ
1. getBulkDownloadで、一括ダウンロードをするデータをリクエストします。<br>
2. レスポンス内に含まれるdownloadBulkJobId（以下バルクID）を取得します。<br>
3. 取得したバルクIDを利用し、getBulkDownloadStatusでステータスを確認します。<br>
4. ステータスが"COMPLETED"ならば、レスポンスにダウンロードURLが戻ります。<br>
5. ステータスが"IN_PROGRESS"ならば、一定時間をおき再度ステータスの確認を実施します。<br>
6. ステータスが"SYSTEM_ERROR"であれば、ダウンロードURLは戻りません。再度一括ダウンロードのリクエストを実施します。<br>
7. ステータスが"TIMEOUT"（タイムアウト）ならば、再度一括ダウンロードのリクエストを実施します。<br>
　問題が解決しない場合は、弊社API担当者まで連絡をして下さい。

#### アップロード処理の流れ
1. getUploadUrlで一括アップロード用のURLをリクエストします。<br>
2. アップロード用のURLがレスポンスとして戻されます。<br>
3. アップロードURLにバルクシートのアップロード処理を実施します。<br>アップロード処理が完了すると、HTTPのレスポンス内に含まれる、uploadBulkJobId（以下バルクID）を取得します。
4. uploadBulkJobIdをもとに、getBulkUploadStatusでアップロードのステータスを取得します。<br>
5. ステータス(uploadBulkJobStatus)が"IN_PROGRESS"ならば、アップロード処理の実行中です。<br>
　ステータスの確認を完了になるまで実施してください。<br>
6. ステータスが"COMPLETED"ならば、アップロード処理が正常に終了しました。<br>
　processingItemsCountで処理した件数を確認できます。<br>
　エラーの詳細を取得したい場合は、downloadBulkUploadFileUrlでバルクシートに処理結果が追記されたファイルをダウンロードできます。

#### 注意事項
・セキュリティ上、ダウンロードURLは15分間のみ有効です。<br>
　URL取得後、15分経過した場合は、再度getBulkDownloadにて新規のダウンロードURLを取得して下さい。<br>
・ダウンロードファイルには、削除されたキャンペーン情報は含まれません。<br>
・getBulkDownloadでURLを作成した、IPアドレスでのみダウンロード処理が可能です。<br>
・1アカウントあたりのダウンロードジョブの制限数はありません。<br>
　ただし、一度に大量のダウンロードジョブを登録した場合は、処理待ちの状態となります。<br>
　一度に大量のバルクダウンロードは実施せず、複数回に分けて実施することをお勧めします。<br>

#### 操作
BulkServiceで提供される操作を説明します。

+ [getBulkDownload](#getbulkdownload)
+ [getBulkDownloadStatus](#getbulkdownloadstatus)
+ [getUploadUrl](#getuploadurl)
+ [getBulkUploadStatus](#getbulkuploadstatus)

#### オブジェクト
[Bulk](../data/Bulk)

## getBulkDownload

### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BulkDownloadSelector](../data/Bulk/BulkDownloadSelector.md) | getBulkDownloadメソッドのダウンロードジョブの実行パラメータを保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkDownload xmlns="http://im.yahooapis.jp/V201809/Bulk">
      <selector>
        <accountId>1111</accountId>
        <campaignIds>2222</campaignIds>
        <adGroupIds>2222</adGroupIds>
        <adIds>2222</adIds>
        <mediaIds>2222</mediaIds>
        <campaignUserStatuses>ACTIVE</campaignUserStatuses>
        <campaignUserStatuses>PAUSED</campaignUserStatuses>
        <adGroupUserStatuses>ACTIVE</adGroupUserStatuses>
        <adGroupUserStatuses>PAUSED</adGroupUserStatuses>
        <adGroupAdUserStatuses>ACTIVE</adGroupAdUserStatuses>
        <adGroupAdUserStatuses>PAUSED</adGroupAdUserStatuses>
        <mediaUserStatuses>ACTIVE</mediaUserStatuses>
        <mediaUserStatuses>PAUSED</mediaUserStatuses>
        <adGroupAdApprovalStatuses>REVIEW</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>PRE_DISAPPROVED</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>POST_DISAPPROVED</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>APPROVED</adGroupAdApprovalStatuses>
        <adGroupAdApprovalStatuses>APPROVED_WITH_REVIEW</adGroupAdApprovalStatuses>
        <mediaApprovalStatuses>REVIEW</mediaApprovalStatuses>
        <mediaApprovalStatuses>PRE_DISAPPROVED</mediaApprovalStatuses>
        <mediaApprovalStatuses>POST_DISAPPROVED</mediaApprovalStatuses>
        <mediaApprovalStatuses>APPROVED</mediaApprovalStatuses>
        <entityTypes>ALL</entityTypes>
        <downloadBulkJob>
          <accountId>1111</accountId>
          <downloadBulkJobName>test</downloadBulkJobName>
          <downloadBulkUserName>1111-2222-3333-4444</downloadBulkUserName>
        </downloadBulkJob>
        <downloadType>CAMPAIGN</downloadType>
        <lang>JA</lang>
        <output>CSV</output>
        <encoding>UTF-8</encoding>
      </selector>
    </getBulkDownload>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/Bulk/BulkDownloadReturnValue.md) | getBulkDownloadメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1536568322206</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkDownloadResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Bulk">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:downloadBulkJob>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:downloadBulkJobId>2222</ns2:downloadBulkJobId>
            <ns2:downloadBulkUserName>1111-2222-3333-4444</ns2:downloadBulkUserName>
            <ns2:downloadBulkStartDate>20180312161410</ns2:downloadBulkStartDate>
            <ns2:progress>1</ns2:progress>
          </ns2:downloadBulkJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getBulkDownloadResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkDownloadStatus

### リクエスト
一括ダウンロードの処理状況を確認し、ダウンロード元のURLを取得します。downloadJobStatusがCOMPLETEDの場合、レスポンスにダウンロードURLが設定されます。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BulkDownloadStatusSelector](../data/Bulk/BulkDownloadStatusSelector.md) | getBulkDownloadStatusメソッドの検索条件（実行パラメータ）を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkDownloadStatus xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <selector>
        <accountId>1111</accountId>
        <downloadBulkJobIds>2222</downloadBulkJobIds>
        <downloadBulkJobStatus>IN_PROGRESS</downloadBulkJobStatus>
        <downloadBulkJobStatus>TIMEOUT</downloadBulkJobStatus>
        <downloadBulkJobStatus>SYSTEM_ERROR</downloadBulkJobStatus>
        <downloadBulkJobStatus>COMPLETED</downloadBulkJobStatus>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </getBulkDownloadStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/Bulk/BulkDownloadStatusPage.md) | getBulkDownloadStatusメソッドの実行結果（1Entity）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1536568322164</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkDownloadStatusResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Bulk">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>BulkDownloadStatusPage</Page.Type>
        <ns2:values>
          <ns2:downloadBulkJob>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:downloadBulkJobId>2222</ns2:downloadBulkJobId>
            <ns2:downloadBulkUserName>1111-2222-3333-4444</ns2:downloadBulkUserName>
            <ns2:downloadBulkStartDate>20180312161410</ns2:downloadBulkStartDate>
            <ns2:downloadBulkEndDate>20180312161535</ns2:downloadBulkEndDate>
            <ns2:progress>100</ns2:progress>
            <ns2:downloadBulkDownloadUrl>https://colo01.im.yahooapis.jp/bulkDownload/V201809/download/WrtMjzl0WuCSgxe908KOwHOqEaZTLIBYFVVPiO9dP0bTRWLs5IV.bit7A.y5nViF8l0NjSpqZJO0Ys_WZO7lW6JfT2vaLZESBAyYbdvZyy2aQapy84FcpyJ2PWq2ReJHsaeYOy49QjFg6MOjMYc5cW.xIAp6H5mPGu6Q6_hJpIrHWdv6UH4gclQ05ySod1O1xqNUePM7dvilxI5VTR4y0hKJsXY.PifHjg99LmMQXzLKyx.G6YUEf5M_KkE4Vwo0IJPdcAAx1HnSsy6mYvebogYhGYd5RiuLoq4aZqECLa2IYggY5Zt.FShCDPhMCQgqfjFjR_YrTzeuGU4n1CwRNa0FeO5qUgwA27c5gKENJ..ZIZTUPiQ-</ns2:downloadBulkDownloadUrl>
          </ns2:downloadBulkJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getBulkDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadUrl

### リクエスト
アップロード対象になるURLを定義します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 |
| uploadBulkJobName | - | xsd:string | バルクジョブ名です。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201809/Bulk">
      <accountId>1111</accountId>
      <uploadBulkJobName>test job</uploadBulkJobName>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [UploadUrlValue](../data/Bulk/UploadUrlValue.md) | アップロードURLの情報を保持します。 | error | [Error](../data/Bulk/Error.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1536568322148</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <rval>
        <accountId>1111</accountId>
        <acceptableUploadStatus>true</acceptableUploadStatus>
        <uploadUrl>https://im.yahooapis.jp/bulkUpload/V201809/upload/zetNmzUcUeAX120zCqfuzh_EusRxEGqXKPTjnLEqxolCwB7MfznLUU5QIp9.Gc_Th4vHkAnvp_yPqnZeCSL9rVo7mcOM7W8uxlNqC96bludvti0cnw--</uploadUrl>
      </rval>
    </getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkUploadStatus

### リクエスト
アップロード状況を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [BulkUploadStatusSelector](../data/Bulk/BulkUploadStatusSelector.md) | getBulkUploadStatusメソッドの検索条件（実行パラメータ）を保持します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkUploadStatus xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <selector>
        <accountId>1111</accountId>
        <uploadBulkJobIds>22222</uploadBulkJobIds>
        <uploadBulkJobStatus>COMPLETED</uploadBulkJobStatus>
        <uploadBulkJobStatus>IN_PROGRESS</uploadBulkJobStatus>
        <uploadBulkJobStatus>FILE_FORMAT_ERROR</uploadBulkJobStatus>
        <uploadBulkJobStatus>SYSTEM_ERROR</uploadBulkJobStatus>
        <uploadBulkJobStatus>TIMEOUT</uploadBulkJobStatus>
      </selector>
    </getBulkUploadStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [BulkUploadStatusPage](../data/Bulk/BulkUploadStatusPage.md)|　etBulkUploadStatusメソッドの実行結果（全Entityのリスト）を保持します。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201809/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201809">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1536568322119</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkUploadStatusResponse xmlns="http://im.yahooapis.jp/V201809" xmlns:ns2="http://im.yahooapis.jp/V201809/Bulk">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:uploadBulkJob>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:uploadBulkJobId>3387</ns2:uploadBulkJobId>
            <ns2:uploadBulkJobName>bulk_test_name</ns2:uploadBulkJobName>
            <ns2:uploadBulkUserName>1111-2222-3333-4444</ns2:uploadBulkUserName>
            <ns2:uploadBulkStartDate>20180312153802</ns2:uploadBulkStartDate>
            <ns2:uploadBulkJobStatus>IN_PROGRESS</ns2:uploadBulkJobStatus>
            <ns2:processingItemsCount>
              <ns2:campaignCount>0</ns2:campaignCount>
              <ns2:adGroupCount>0</ns2:adGroupCount>
              <ns2:adGroupAdCount>0</ns2:adGroupAdCount>
              <ns2:adGroupTargetCount>0</ns2:adGroupTargetCount>
              <ns2:mediaCount>0</ns2:mediaCount>
              <ns2:videoCount>0</ns2:videoCount>
              <ns2:campaignErrorCount>7</ns2:campaignErrorCount>
              <ns2:adGroupErrorCount>0</ns2:adGroupErrorCount>
              <ns2:adGroupAdErrorCount>0</ns2:adGroupAdErrorCount>
              <ns2:adGroupTargetErrorCount>0</ns2:adGroupTargetErrorCount>
              <ns2:mediaErrorCount>0</ns2:mediaErrorCount>
              <ns2:videoErrorCount>0</ns2:videoErrorCount>
            </ns2:processingItemsCount>
            <ns2:progress>100</ns2:progress>
          </ns2:uploadBulkJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getBulkUploadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
