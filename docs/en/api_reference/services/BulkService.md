# BulkService
Use this service for bulk downloading/uploading by using bulk sheet.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/BulkService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/BulkService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Offers a bulk download function that uses bulk sheets.

#### Operation
[Download process]<br>
1. Use getBulkDownload to request data for bulk downloading.<br>
2. Acquire downloadBulkJobId (bulk ID) included in response.<br>
3. Check status with getBulkDownloadStatus by using the acquired bulk ID.<br>
4. Download URL returns in the response if status is "COMPLETED".<br>
5. Check status for each determined period if status is “IN_PROGRESS".<br>
6. Download URL will not return if status is stated as "SYSTEM_ERROR".<br>
　Make another bulk download request.<br>
7. Request another bulk download if status is stated as "TIMEOUT". <br>
　If the problem is not resolved, please contact from Inquiry page.<br>
<br>
[Upload Process]<br>
1. Request URL for bulk uploading by using getUploadUrl.<br>
2. The URL for uploading is responded.<br>
3. Process bulk uploading to upload URL.<br>
4. Acquire uploadBulkJobId(bulk ID) in the HTTP response when the upload processis completed.<br>
5. Acquire upload status by using getBulkUploadStatus based on uploadBulkJobId. <br>
6. If the status (uploadBulkJobStatus) is "IN_PROGRESS", the upload is in progress, not completed. <br>
　Retry retrieving the upload satus until you confirm the status "COMPLETED".<br>
7. If the status is "COMPLETED", the upload is completed. <br>
　Confirm the number of cases succeeded by using<br> processingItemsCount. <br>
　If there are errors, please download the file to aquire the error details by using downloadBulkUploadFileUrl (Process results is added into the bulk sheet).<br>
<br>
[Notes]<br>
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
| selector | ○ | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | Defines a bulk acquisition target. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignIds>2000000001</ns1:campaignIds>
        <ns1:adGroupIds>3000000001</ns1:adGroupIds>
        <ns1:downloadType>REVIEW_AD</ns1:downloadType>
        <ns1:dateRange>
          <ns1:startDate>20120303</ns1:startDate>
          <ns1:endDate>20120402</ns1:endDate>
        </ns1:dateRange>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml	
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
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

### Response 
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | A container that stores results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
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
### Request
Checks the bulk download process status and acquires download source URL.<br>
If downloadJobStatus is COMPLETED, the download URL is set to response.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [BulkDownloadStatusSelector](../data/BulkDownloadStatusSelector.md) | Defines a target for acquisition. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
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

##### Request Sample (On-Behalf-Of Account) 
```xml
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/BulkDownloadStatusPage.md) | The container including process status of target. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
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
### Request
Defines URL for upload target.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | Defines a bulk acquisition target. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignIds>2000000001</ns1:campaignIds>
        <ns1:adGroupIds>3000000001</ns1:adGroupIds>
        <ns1:downloadType>REVIEW_AD</ns1:downloadType>
        <ns1:dateRange>
          <ns1:startDate>20120303</ns1:startDate>
          <ns1:endDate>20120402</ns1:endDate>
        </ns1:dateRange>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | A container that stores results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
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
### Request
Acquires upload status.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [BulkDownloadSelector](../data/BulkDownloadSelector.md) | Defines a bulk acquisition target. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getBulkDownload>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:campaignIds>2000000001</ns1:campaignIds>
        <ns1:adGroupIds>3000000001</ns1:adGroupIds>
        <ns1:downloadType>REVIEW_AD</ns1:downloadType>
        <ns1:dateRange>
          <ns1:startDate>20120303</ns1:startDate>
          <ns1:endDate>20120402</ns1:endDate>
        </ns1:dateRange>
        <ns1:output>CSV</ns1:output>
        <ns1:encoding>SJIS</ns1:encoding>
      </ns1:selector>
      </ns1:getBulkDownload>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
            <ns1:apiAccountId>xxxxxxxxxxxxxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
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

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/BulkDownloadReturnValue.md) | A container that stores results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
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
                        <ns1:downloadBulkUploadFileUrl>https://sample.api.yahooapis.jp/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadBulkUploadFileUrl>
                    </ns1:uploadBulkJob>
                </ns1:values>
            </ns1:rval>
        </ns1:getBulkUploadStatusResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
