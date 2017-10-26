# BulkService
Use this service for bulk downloading/uploading by using bulk sheet.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/BulkService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/BulkService?wsdl |
#### Namespace
http://im.yahooapis.jp/V6
#### Service Overview
Offers a bulk download function that uses bulk sheets.

#### Download process
1. Use getBulkDownload to request data for bulk downloading.<br>
2. Acquire downloadBulkJobId (bulk ID) included in response.<br>
3. Check status with getBulkDownloadStatus by using the acquired bulk ID.<br>
4. Download URL returns in the response if status is "COMPLETED".<br>
5. Check status for each determined period if status is “IN_PROGRESS".<br>
6. Download URL will not return if status is stated as "SYSTEM_ERROR".　Make another bulk download request.<br>
7. Request another bulk download if status is stated as "TIMEOUT". <br>
　If the problem is not resolved, please contact from Inquiry page.

#### Upload Process
1. Request URL for bulk uploading by using getUploadUrl.<br>
2. The URL for uploading is responded.<br>
3. Process bulk uploading to upload URL.<br>When the upload processis is completed, uploadBulkJobId(bulk ID) should be obtained in the HTTP response.
4. Acquire upload status by using getBulkUploadStatus based on uploadBulkJobId. <br>
5. If the status (uploadBulkJobStatus) is "IN_PROGRESS", the upload is in progress, not completed. <br>
　Retry retrieving the upload satus until you confirm the status "COMPLETED".<br>
6. If the status is "COMPLETED", the upload is completed. <br>
　Confirm the number of cases succeeded by using<br> processingItemsCount. <br>
　If there are errors, please download the file to aquire the error details by using downloadBulkUploadFileUrl (Process results is added into the bulk sheet).

#### Notes
・For security reasons, the download URL is only valid for 15 minutes. <br>
　If 15 minutes passes after the URL is acquired, please use getBulkDownload to acquire a new download URL.<br>
・Deleted campaign information is not included in the download file.<br>
・Download processing can only be done with the IP address that created the URL with getBulkDownload.<br>
・There is no limit to the number of download jobs that can be performed per account. <br>
　However, when a large download job is registered, it will take time to process. <br>
　We recommend dividing a bulk download job into smaller sections instead of performing it at one time.

## getBulkDownload
### Request
| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | Contains the parameters of download job for getBulkDownload method. | 

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
        <ns1:downloadType>CAMPAIGN</ns1:downloadType>
        <ns1:lang>JA</ns1:lang>
        <ns1:output>ZIPPED_CSV</ns1:output>
        <ns1:encoding>UTF-8</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response 
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | Contains the results (a list of all entities) for getBulkDownload method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
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
### Request
Checks the bulk download process status and acquires download source URL. If downloadJobStatus is COMPLETED, the download URL is set to response.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [BulkDownloadStatusSelector](../data/BulkDownloadStatusSelector.md) | Contains a set of criteria (parameters) for getBulkDownloadStatus method. | 

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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/BulkDownloadStatusPage.md) | Contains the result (one entity) for getBulkDownloadStatus method.
 | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1=http://im.yahooapis.jp/V6>
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
            <ns1:downloadBulkJobName>Download Job Name 1</ns1:downloadBulkJobName>
            <ns1:downloadBulkUserName>EXTERNAL_API</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2012-04-03T12:52:04+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadBulkEndDate>2012-04-03T12:52:15+09:00</ns1:downloadBulkEndDate>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus>
            <ns1:downloadBulkDownloadUrl>https ://sample.api.yahooapis.jp/bulkDownload/V6.1/download/iBXYtsbwryBRGfYACzEAyGSuORCilbjw5OSqHmCXL.n4ngB_NhxJ2XfmdscmSBHBnXpaw.hHf1Xxv.g0CBr4uaUeXA--</ns1:downloadBulkDownloadUrl>
          </ns1:downloadBulkJob>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:downloadBulkJob>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:downloadBulkJobId>100002</ns1:downloadBulkJobId>
            <ns1:downloadBulkJobName>Download Job Name 2</ns1:downloadBulkJobName>
            <ns1:downloadBulkUserName>EXTERNAL_API</ns1:downloadBulkUserName>
            <ns1:downloadBulkStartDate>2012-04-03T12:53:08+09:00</ns1:downloadBulkStartDate>
            <ns1:downloadBulkEndDate>2012-04-03T12:53:30+09:00</ns1:downloadBulkEndDate>
            <ns1:progress>100</ns1:progress>
            <ns1:downloadJobStatus>COMPLETED</ns1:downloadJobStatus>
            <ns1:downloadBulkDownloadUrl>https://sample.api.yahooapis.jp/bulkDownload/V6.1/download/qCYSrtswpqAPGaYAXcQycgsGRaIBekaQp3BN1JaHPL.s0s8B_ApxJ3lrislgkBKBSeo4l.dik3Xio.e9B8aloaQ7oC--</ns1:downloadBulkDownloadUrl>
          </ns1:downloadBulkJob>
        </ns1:values>
      </ns1:rval>
    </ns1:getBulkDownloadStatusResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getUploadUrl
### Request
Defines URL for upload target.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| accountId | required | xsd:long | account id | 
| uploadBulkJobName | - | xsd:sting | bulk job name | 

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
        <ns1:getUploadUrl>
            <ns1:accountId>111111111</ns1:accountId>
        </ns1:getUploadUrl>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [UploadUrlValue](../data/UploadUrlValue.md) | Contains the information of upload URL. | error | [Error](../data/Error.md) |  | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
               <ns1:uploadUrl>https://sample.api.yahooapis.jp/bulkUpload/V4/upload/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B </ns1:uploadUrl>
           </ns1:rval>
       </ns1:getUploadUrlResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkUploadStatus
### Request
Acquires upload status.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [BulkUploadStatusSelector](../data/BulkDownloadSelector.md) | Contains a set of criteria (parameters) for getBulkUploadStatus method. | 

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
        <ns1:getBulkUploadStatus>
            <ns1:selector>
                <ns1:accountId>1111111111</ns1:accountId>
                <ns1:uploadBulkJobIds>2222222222</ns1:uploadBulkJobIds>
                <ns1:uploadBulkJobStatus>IN_PROGRESS</ns1:uploadBulkJobStatus>
                <ns1:output>ZIPPED_CSV</ns1:output>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:getBulkUploadStatus>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkUploadStatusPage](../data/BulkUploadStatusPage.md)| Contains the results (a list of all entities) for GetBulkUploadStatus method. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
                            <ns1:videoCount>0</ns1:videoCount>
                            <ns1:campaignErrorCount>18</ns1:campaignErrorCount>
                            <ns1:adGroupErrorCount>0</ns1:adGroupErrorCount>
                            <ns1:adGroupAdErrorCount>0</ns1:adGroupAdErrorCount>
                            <ns1:adGroupTargetErrorCount>0</ns1:adGroupTargetErrorCount>
                            <ns1:mediaErrorCount>0</ns1:mediaErrorCount>
                            <ns1:videoErrorCount>0</ns1:videoErrorCount>
                        </ns1:processingItemsCount>
                        <ns1:progress>100</ns1:progress>
                        <ns1:downloadBulkUploadFileUrl>https://sample.api.yahooapis.jp/bulkUpload/V6/download/3CRAGObSahcIylBoDZS5ftx7qS4VM5jSHqs77QZqmpBFnJFP2jvKe3Dy72UEX3InsUoShWXa3YcX3AmbtqxGco6B</ns1:downloadBulkUploadFileUrl>
                    </ns1:uploadBulkJob>
                </ns1:values>
            </ns1:rval>
        </ns1:getBulkUploadStatusResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
