# BulkService
Use this service for bulk downloading/uploading by using bulk sheet.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201812/BulkService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201812/BulkService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201812/Bulk
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

#### Operation
Describes operations provided by BulkService.

+ [getBulkDownload](#getbulkdownload)
+ [getBulkDownloadStatus](#getbulkdownloadstatus)
+ [getUploadUrl](#getuploadurl)
+ [getBulkUploadStatus](#getbulkuploadstatus)

#### Object
[Bulk](../data/Bulk)

## getBulkDownload

### Request
| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [BulkDownloadSelector](../data/Bulk/BulkDownloadSelector.md) | Contains the parameters of download job for getBulkDownload method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkDownload xmlns="http://im.yahooapis.jp/V201903/Bulk">
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

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [BulkDownloadReturnValue](../data/Bulk/BulkDownloadReturnValue.md) | Contains the results (a list of all entities) for getBulkDownload method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1551686145041</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkDownloadResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Bulk">
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

### Request
Checks the bulk download process status and acquires download source URL. If downloadJobStatus is COMPLETED, the download URL is set to response.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [BulkDownloadStatusSelector](../data/Bulk/BulkDownloadStatusSelector.md) | Contains a set of criteria (parameters) for getBulkDownloadStatus method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkDownloadStatus xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
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

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [BulkDownloadStatusPage](../data/Bulk/BulkDownloadStatusPage.md) | Contains the result (one entity) for getBulkDownloadStatus method.
 |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1551686145024</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkDownloadStatusResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Bulk">
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
            <ns2:downloadBulkDownloadUrl>https://colo01.im.yahooapis.jp/bulkDownload/V201903/download/WrtMjzl0WuCSgxe908KOwHOqEaZTLIBYFVVPiO9dP0bTRWLs5IV.bit7A.y5nViF8l0NjSpqZJO0Ys_WZO7lW6JfT2vaLZESBAyYbdvZyy2aQapy84FcpyJ2PWq2ReJHsaeYOy49QjFg6MOjMYc5cW.xIAp6H5mPGu6Q6_hJpIrHWdv6UH4gclQ05ySod1O1xqNUePM7dvilxI5VTR4y0hKJsXY.PifHjg99LmMQXzLKyx.G6YUEf5M_KkE4Vwo0IJPdcAAx1HnSsy6mYvebogYhGYd5RiuLoq4aZqECLa2IYggY5Zt.FShCDPhMCQgqfjFjR_YrTzeuGU4n1CwRNa0FeO5qUgwA27c5gKENJ..ZIZTUPiQ-</ns2:downloadBulkDownloadUrl>
          </ns2:downloadBulkJob>
        </ns2:values>
      </ns2:rval>
    </ns2:getBulkDownloadStatusResponse>
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
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrl xmlns="http://im.yahooapis.jp/V201903/Bulk">
      <accountId>1111</accountId>
      <uploadBulkJobName>test job</uploadBulkJobName>
    </getUploadUrl>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [UploadUrlValue](../data/Bulk/UploadUrlValue.md) | Contains the information of upload URL. | error | [Error](../data/Bulk/Error.md) |  |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1551686145017</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getUploadUrlResponse xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <rval>
        <accountId>1111</accountId>
        <acceptableUploadStatus>true</acceptableUploadStatus>
        <uploadUrl>https://im.yahooapis.jp/bulkUpload/V201903/upload/zetNmzUcUeAX120zCqfuzh_EusRxEGqXKPTjnLEqxolCwB7MfznLUU5QIp9.Gc_Th4vHkAnvp_yPqnZeCSL9rVo7mcOM7W8uxlNqC96bludvti0cnw--</uploadUrl>
      </rval>
    </getUploadUrlResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getBulkUploadStatus

### Request
Acquires upload status.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [BulkUploadStatusSelector](../data/Bulk/BulkDownloadSelector.md) | Contains a set of criteria (parameters) for getBulkUploadStatus method. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getBulkUploadStatus xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
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

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [BulkUploadStatusPage](../data/Bulk/BulkUploadStatusPage.md)| Contains the results (a list of all entities) for GetBulkUploadStatus method. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Bulk" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Bulk</ns2:service>
      <ns2:requestTime>1551686145005</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getBulkUploadStatusResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Bulk">
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
