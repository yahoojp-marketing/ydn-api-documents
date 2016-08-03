# AuditLogService
AuditLogServiceは、操作履歴のダウンロード機能を提供します。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AuditLogService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AuditLogService?wsdl|

#### Namespace
http://im.yahooapis.jp/V5

#### サービス概要
操作履歴のダウンロード機能を提供します。

#### 操作
AuditLogServiceで提供される操作を説明します。

## getDownload
### リクエスト
操作履歴のダウンロード実行情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AuditLogDownloadSelector](../data/AuditLogDownloadSelector.md) | getDownloadメソッドの実行パラメータを保持するオブジェクトです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:auditLogJobId>2000000001</ns1:auditLogJobId>
        <ns1:campaignIds>3000000001</ns1:campaignIds>
        <ns1:campaignIds>3000000002</ns1:campaignIds>
        <ns1:updateSources>CAMPAIGN_MANAGEMENT_TOOL</ns1:updateSources>
        <ns1:updateSources>API</ns1:updateSources>
        <ns1:dateRange>
          <ns1:startDate>20120701</ns1:startDate>
          <ns1:endDate>20120707</ns1:endDate>
        </ns1:dateRange>
        <ns1:auditLogJob>
          <ns1:auditLogJobName>サンプルバルクジョブ1</ns1:auditLogJobName>
        </ns1:auditLogJob>
        <ns1:lang>JA</ns1:lang>
      </ns1:selector>
      </ns1:getDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AuditLogDownloadReturnValue](../data/AuditLogDownloadReturnValue.md) | getDownloadメソッドの実行結果を保持するオブジェクトです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AuditLogService</ns1:service>
      <ns1:remainingQuota>371</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>2.5132</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getDownloadResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditLogJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:auditLogJobId>100001</ns1:auditLogJobId>
            <ns1:auditLogJobName>100001</ns1:auditLogJobName>
            <ns1:auditLogJobUserName>XXXX-XXXX-XXXX-XXXX</ns1:auditLogJobUserName>
            <ns1:auditLogJobStartDate>20160303120000</ns1:auditLogJobStartDate>
            <ns1:auditLogJobStatus>IN_PROGRESS</ns1:auditLogJobStatus>
            <ns1:progress>0</ns1:progress>
          </ns1:auditLogJob>
        </ns1:values>
      </ns1:rval>
    </ns1:GetDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getDownloadStatus
### リクエスト
操作履歴のダウンロード実行結果情報を取得します。<br>
また、ダウンロード完了後は、URLも取得できます。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AuditLogDownloadStatusSelector](../data/AuditLogDownloadStatusSelector.md) | getDownloadStatusメソッドの実行パラメータを保持するオブジェクトです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDownloadStatus>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:auditLogJobIds>100001</ns1:auditLogJobIds>
                <ns1:auditLogJobIds>100002</ns1:auditLogJobIds>
                <ns1:auditLogJobStatuses>IN_PROGRESS</ns1:auditLogJobStatuses>
                <ns1:auditLogJobStatuses>COMPLETED</ns1:auditLogJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>200</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
         </ns1:getDownloadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AuditLogDownloadStatusPage](../data/AuditLogDownloadStatusPage.md) | getDownloadStatusメソッドの実行結果を保持するオブジェクトです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AuditLogService</ns1:service>
      <ns1:remainingQuota>129997</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>3.995</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getDownloadStatusResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>auditLogDownloadStatusPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditLogJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:auditLogJobId>100001</ns1:auditLogJobId>
            <ns1:auditLogJobName>ダウンロードジョブ名1</ns1:auditLogJobName>
            <ns1:auditLogJobUserName>EXTERNAL_API</ns1:auditLogJobUserName>
            <ns1:auditLogJobStartDate>20150403125230</ns1:auditLogJobStartDate>
            <ns1:auditLogJobEndDate>20150403125315</ns1:auditLogJobEndDate>
            <ns1:auditLogJobStatus>COMPLETED</ns1:auditLogJobStatus>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadAuditLogDownloadUrl>https://sample.api.yahooapis.jp/auditLogDownload/V5.3/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadAuditLogDownloadUrl>
          </ns1:auditLogJob>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:auditLogJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:auditLogJobId>100001</ns1:auditLogJobId>
            <ns1:auditLogJobName>ダウンロードジョブ名1</ns1:auditLogJobName>
            <ns1:auditLogJobUserName>EXTERNAL_API</ns1:auditLogJobUserName>
            <ns1:auditLogJobStartDate>20150403125330</ns1:auditLogJobStartDate>
            <ns1:auditLogJobEndDate>20150403125415</ns1:auditLogJobEndDate>
            <ns1:auditLogJobStatus>COMPLETED</ns1:auditLogJobStatus>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadAuditLogDownloadUrl>https://sample.api.yahooapis.jp/auditLogDownload/V5.3/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadAuditLogDownloadUrl>
          </ns1:auditLogJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
