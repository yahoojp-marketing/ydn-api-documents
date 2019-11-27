# AuditLogService
AuditLogServiceは、操作履歴のダウンロード機能を提供します。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201911/AuditLogService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201911/AuditLogService?wsdl|

#### Namespace
http://im.yahooapis.jp/V201911/AuditLog

#### サービス概要
操作履歴のダウンロード機能を提供します。

【注意事項】<br>
・操作履歴のダウンロードは、getDownloadStatusで返されるURLから取得できます。<br>
  URLの有効期限は15分です。

#### 操作
AuditLogServiceで提供される操作を説明します。

+ [getDownload](#getdownload)
+ [getDownloadStatus](#getdownloadstatus)

#### オブジェクト
[AuditLog](../data/AuditLog)

## getDownload

### リクエスト
操作履歴のダウンロード実行情報を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AuditLogDownloadSelector](../data/AuditLog/AuditLogDownloadSelector.md) | getDownloadメソッドの実行パラメータを保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AuditLog" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getDownload xmlns="http://im.yahooapis.jp/V201911/AuditLog">
      <selector>
        <accountId>100000001</accountId>
        <dateRange>
          <startDate>20180305</startDate>
          <endDate>20180306</endDate>
        </dateRange>
        <auditLogJob>
          <auditLogJobName>test job</auditLogJobName>
        </auditLogJob>
        <lang>JA</lang>
      </selector>
    </getDownload>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [AuditLogDownloadReturnValue](../data/AuditLog/AuditLogDownloadReturnValue.md) | getDownloadメソッドの実行結果を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AuditLog" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AuditLog</ns2:service>
      <ns2:requestTime>1574406675123</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getDownloadResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AuditLog">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:auditLogJob>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:auditLogJobId>19771824</ns2:auditLogJobId>
            <ns2:auditLogJobName>test job</ns2:auditLogJobName>
            <ns2:auditLogJobUserName>1111-2222-3333-4444</ns2:auditLogJobUserName>
            <ns2:auditLogJobStartDate>20180306171824</ns2:auditLogJobStartDate>
            <ns2:auditLogJobStatus>IN_PROGRESS</ns2:auditLogJobStatus>
            <ns2:progress>0</ns2:progress>
          </ns2:auditLogJob>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:auditLogJob>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:auditLogJobId>19771825</ns2:auditLogJobId>
            <ns2:auditLogJobName>test job completed</ns2:auditLogJobName>
            <ns2:auditLogJobUserName>1111-2222-3333-4444</ns2:auditLogJobUserName>
            <ns2:auditLogJobStartDate>20180306171824</ns2:auditLogJobStartDate>
            <ns2:auditLogJobEndDate>20180306171924</ns2:auditLogJobEndDate>
            <ns2:auditLogJobStatus>COMPLETED</ns2:auditLogJobStatus>
            <ns2:progress>100</ns2:progress>
            <ns2:downloadAuditLogDownloadUrl>https://location.im.yahooapis.jp/auditLogDownload/V201911/download/fOFrjyw7I</ns2:downloadAuditLogDownloadUrl>
          </ns2:auditLogJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getDownloadResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getDownloadStatus

### リクエスト
操作履歴のダウンロード実行結果情報を取得します。<br>
また、ダウンロード完了後は、URLも取得できます。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [AuditLogDownloadStatusSelector](../data/AuditLog/AuditLogDownloadStatusSelector.md) | getDownloadStatusメソッドの実行パラメータを保持するオブジェクトです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AuditLog" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getDownloadStatus xmlns="http://im.yahooapis.jp/V201911/AuditLog" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>100000001</accountId>
        <auditLogJobIds>1111</auditLogJobIds>
        <auditLogJobIds>2222</auditLogJobIds>
        <auditLogJobStatuses>IN_PROGRESS</auditLogJobStatuses>
        <auditLogJobStatuses>COMPLETED</auditLogJobStatuses>
        <auditLogJobStatuses>SYSTEM_ERROR</auditLogJobStatuses>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </getDownloadStatus>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [AuditLogDownloadStatusPage](../data/AuditLog/AuditLogDownloadStatusPage.md) | getDownloadStatusメソッドの実行結果を保持するオブジェクトです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AuditLog" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AuditLog</ns2:service>
      <ns2:requestTime>1574406675155</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getDownloadStatusResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AuditLog">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>AuditLogPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:auditLogJob>
            <ns2:accountId>100000001</ns2:accountId>
            <ns2:auditLogJobId>19771824</ns2:auditLogJobId>
            <ns2:auditLogJobName>test job</ns2:auditLogJobName>
            <ns2:auditLogJobUserName>1111-2222-3333-4444</ns2:auditLogJobUserName>
            <ns2:auditLogJobStartDate>20180306171824</ns2:auditLogJobStartDate>
            <ns2:auditLogJobStatus>IN_PROGRESS</ns2:auditLogJobStatus>
            <ns2:progress>10</ns2:progress>
          </ns2:auditLogJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
