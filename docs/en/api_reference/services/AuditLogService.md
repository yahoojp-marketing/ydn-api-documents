# AuditLogService
AuditLogService retrieves the data of user operation history.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AuditLogService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AuditLogService?wsdl |
#### Namespace
http://im.yahooapis.jp/V6
#### Service Overview
Offers download operation history data.
#### Operation
Describes operations provided by AuditLogService.
## getDownload
### Request
Retrieves information of download operation history data.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [AuditLogDownloadSelector](../data/AuditLogDownloadSelector.md) | Object which acquire the exec parameter of getDownload method | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6">
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
          <ns1:auditLogJobName>SampleBulkJob1</ns1:auditLogJobName>
        </ns1:auditLogJob>
        <ns1:lang>JA</ns1:lang>
      </ns1:selector>
      </ns1:getDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AuditLogDownloadReturnValue](../data/AuditLogDownloadReturnValue.md) | Object which acquire the exec parameter of getDownload method | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V6">
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
### Request
Retrieves the download result information of operation history

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [AuditLogDownloadStatusSelector](../data/AuditLogDownloadStatusSelector.md) | Object which acquire the exec parameter of getDownloadStatus method | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6">
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
### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AuditLogDownloadStatusPage](../data/AuditLogDownloadStatusPage.md) | Object which acquire the result of getDownloadStatus method | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V6">
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
            <ns1:auditLogJobName>DownloadJobName1</ns1:auditLogJobName>
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
            <ns1:auditLogJobName>DownloadJobName1</ns1:auditLogJobName>
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
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
