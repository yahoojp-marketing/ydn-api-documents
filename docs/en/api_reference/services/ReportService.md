# ReportService
ReportService acquires, creates, and deletes reports. <br>
It also includes an operation that acquires report download URLs.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/ReportService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/ReportService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Acquires, creates, and deletes reports. <br>
It also includes an operation that acquires report download URLs. <br>
<br>
[Notes]<br>
・Reports are downloaded using URLs created with getDownloadUtl. <br>
　URLs are valid for 5 minutes. <br>
　Requests can only be made with the IP used to create the URL. <br>
・Up to 30 download jobs can be done per account for reports that can be simultaneously registered. <br>
　If more than 30 are done, the following error will occur. <br>
　Add the downlaod job again after deleting the unnecessary download jobs.<br>
　"240001：Over limit of uncompleted report download job."<br>
・Up to 20,000 report download jobs can be registered per account, including completed ones. <br>
　If more than 20,000 are registered, the following error will occur. <br>
　Add the downlaod job again after deleting the unnecessary download jobs.<br>
　"240002：Over limit of report download job."<br>
・Report download jobs will be automatically deleted in one week.<br>

#### Operation
Describes operations provided by ReportService.
## get
### Request
Acquires report related information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [ReportSelector](../data/ReportSelector.md) | Operation target report. | 

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
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:reportIds>9000000001</ns1:reportIds>
        <ns1:reportIds>9000000002</ns1:reportIds>
        <ns1:reportJobIds>8000000001</ns1:reportJobIds>
        <ns1:reportJobIds>8000000002</ns1:reportJobIds>
        <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
        <ns1:reportJobStatuses>FAILED</ns1:reportJobStatuses>
        <ns1:paging>
          <ns1:startIndex>1</ns1:startIndex>
          <ns1:numberResults>20</ns1:numberResults>
        </ns1:paging>
      </ns1:selector>
    </ns1:get>
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
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>
                <ns1:reportIds>9000000003</ns1:reportIds>
                <ns1:reportJobIds>8000000001</ns1:reportJobIds>
                <ns1:reportJobIds>8000000002</ns1:reportJobIds>
                <ns1:reportJobIds>8000000003</ns1:reportJobIds>
                <ns1:reportJobStatuses>COMPLETED</ns1:reportJobStatuses>
                <ns1:reportJobStatuses>FAILED</ns1:reportJobStatuses>
                <ns1:paging>
                    <ns1:startIndex>1</ns1:startIndex>
                    <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [ReportPage](../data/ReportPage.md) | Container of report definitions to be acquired. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>3</ns1:totalNumEntries>
                <ns1:Page.Type>ReportPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000001</ns1:reportJobId>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175909</ns1:requestTime>
                        <ns1:completeTime>20120403175910</ns1:completeTime>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:dateRange>
                            <ns1:startDate>20120303</ns1:startDate>
                            <ns1:endDate>20120402</ns1:endDate>
                        </ns1:dateRange>
                        <ns1:status>COMPLETED</ns1:status>
                    </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000002</ns1:reportJobId>
                        <ns1:reportId>9000000002</ns1:reportId>
                        <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175908</ns1:requestTime>
                        <ns1:completeTime>20120403175909</ns1:completeTime>
                        <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType>
                        <ns1:status>COMPLETED</ns1:status>
                     </ns1:reportRecord>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportRecord>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportJobId>8000000003</ns1:reportJobId>
                        <ns1:reportId>9000000003</ns1:reportId>
                        <ns1:reportName>SandboxAdgroupReport_csv</ns1:reportName>
                        <ns1:requestTime>20120403175911</ns1:requestTime>
                        <ns1:completeTime>20120403175912</ns1:completeTime>
                        <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType>
                        <ns1:status>FAILED</ns1:status>
                        <ns1:jobErrorDetail>Over limit of file size.</ns1:jobErrorDetail>
                    </ns1:reportRecord>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Creates a report.

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/ReportOperation.md) | Displays operation target reports and operation content. | 
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
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportId>9000000001</ns1:reportId>
        </ns1:operand>
        <ns1:operand>
          <ns1:reportId>9000000002</ns1:reportId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
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
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>ADD</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId> 
                <ns1:operand> 
                    <ns1:reportId>9000000001</ns1:reportId> 
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportId>9000000002</ns1:reportId> 
                </ns1:operand> 
            </ns1:operations> 
         </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | Container of reports, including operation results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutateResponse> 
            <ns1:rval> 
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type> 
                <ns1:Operation.Type>ADD</ns1:Operation.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:accountId>1000000001</ns1:accountId> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                        <ns1:reportId>9000000001</ns1:reportId> 
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName> 
                        <ns1:requestTime>20120403175909</ns1:requestTime> 
                        <ns1:completeTime /> 
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                        <ns1:dateRange> 
                            <ns1:startDate>20120303</ns1:startDate> 
                            <ns1:endDate>20120402</ns1:endDate> 
                        </ns1:dateRange> 
                        <ns1:status>IN_PROGRESS</ns1:status> 
                     </ns1:reportRecord> 
                     <ns1:reportRecord> 
                         <ns1:accountId>1000000001</ns1:accountId> 
                         <ns1:reportJobId>8000000002</ns1:reportJobId> 
                         <ns1:reportId>9000000002</ns1:reportId> 
                         <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName> 
                         <ns1:requestTime>20120403175908</ns1:requestTime> 
                         <ns1:completeTime /> 
                         <ns1:dateRangeType>YESTERDAY</ns1:dateRangeType> 
                         <ns1:status>IN_PROGRESS</ns1:status> 
                    </ns1:reportRecord> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:mutateResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Deletes a report

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportOperation](../data/ReportOperation.md) | Displays operation target reports and operation content. | 
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
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:operand>
          <ns1:reportJobId>8000000001</ns1:reportJobId>
        </ns1:operand>
        <ns1:operand>
          <ns1:reportJobId>8000000002</ns1:reportJobId>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
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
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
                <ns1:operator>REMOVE</ns1:operator> 
                <ns1:accountId>1000000001</ns1:accountId>                
                <ns1:operand> 
                    <ns1:reportJobId>8000000001</ns1:reportJobId>                     
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:reportJobId>8000000002</ns1:reportJobId>                     
                </ns1:operand> 
            </ns1:operations> 
        </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportReturnValue](../data/ReportReturnValue.md) | Container of reports, including operation results. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutateResponse> 
            <ns1:rval> 
                <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type> 
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                    </ns1:reportRecord> 
                </ns1:values> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportRecord> 
                        <ns1:reportJobId>8000000002</ns1:reportJobId> 
                    </ns1:reportRecord> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:mutateResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## getDownloadUrl
### Request
Acquires URLs for downloading reports.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [ReportDownloadUrlSelector](../data/ReportDownloadUrlSelector.md) | Operation target report information. | 

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
    <ns1:getDownloadUrl>
      <ns1:selector>
        <ns1:accountId>1000000001</ns1:accountId>
        <ns1:reportJobIds>8000000001</ns1:reportJobIds>
        <ns1:reportJobIds>8000000002</ns1:reportJobIds>
      </ns1:selector>
    </ns1:getDownloadUrl>
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
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>100000001</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getDownloadUrl> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId>    
                <ns1:reportJobIds>8000000001</ns1:reportJobIds> 
                <ns1:reportJobIds>8000000002</ns1:reportJobIds> 
                <ns1:paging> 
                    <ns1:startIndex>1</ns1:startIndex> 
                    <ns1:numberResults>20</ns1:numberResults> 
                </ns1:paging>  
            </ns1:selector> 
        </ns1:getDownloadUrl> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [ReportDownloadUrlPage](../data/ReportDownloadUrlPage.md) | Download URL entry to be acquired. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"> 
    <SOAP-ENV:Header> 
        <ns1:ResponseHeader> 
            <ns1:service>ReportService</ns1:service> 
            <ns1:remainingQuota>100</ns1:remainingQuota> 
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest> 
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis> 
        </ns1:ResponseHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getDownloadUrlResponse> 
            <ns1:rval> 
                <ns1:totalNumEntries>2</ns1:totalNumEntries> 
                <ns1:Page.Type>ReportPage</ns1:Page.Type> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportDownloadUrl> 
                        <ns1:accountId>1000000001</ns1:accountId> 
                        <ns1:reportJobId>8000000001</ns1:reportJobId> 
                        <ns1:reportId>9000000001</ns1:reportId> 
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName> 
                        <ns1:requestTime>20120403164910</ns1:requestTime> 
                        <ns1:completeTime>20120403165126</ns1:completeTime> 
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                        <ns1:dateRange> 
                            <ns1:startDate>20120303</ns1:startDate> 
                            <ns1:endDate>20120402</ns1:endDate> 
                        </ns1:dateRange> 
                        <ns1:status>COMPLETED</ns1:status> 
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                    </ns1:reportDownloadUrl> 
                </ns1:values> 
                <ns1:values> 
                    <ns1:operationSucceeded>true</ns1:operationSucceeded> 
                    <ns1:reportDownloadUrl> 
                    <ns1:accountId>1000000001</ns1:accountId> 
                    <ns1:reportJobId>8000000002</ns1:reportJobId> 
                    <ns1:reportId>9000000002</ns1:reportId> 
                    <ns1:reportName>SandboxCampaignReport_csv</ns1:reportName> 
                    <ns1:requestTime>20120403175908</ns1:requestTime> 
                    <ns1:completeTime>20120403175952</ns1:completeTime> 
                    <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType> 
                    <ns1:dateRange> 
                    <ns1:startDate>20120303</ns1:startDate> 
                    <ns1:endDate>20120402</ns1:endDate> 
                    </ns1:dateRange> 
                    <ns1:status>COMPLETED</ns1:status> 
                    <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX</ns1:downloadUrl> 
                    </ns1:reportDownloadUrl> 
                </ns1:values> 
            </ns1:rval> 
        </ns1:getDownloadUrlResponse> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

## getClosedDate
### Request
Acquires date of report completion.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [ReportClosedDateSelector](../data/ReportClosedDateSelector.md) | Assigns operation target reports. | 

##### Request Sample
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
        <ns1:getClosedDate> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId> 
            </ns1:selector> 
        </ns1:getClosedDate> 
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
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:getClosedDate> 
            <ns1:selector> 
                <ns1:accountId>1000000001</ns1:accountId> 
            </ns1:selector> 
        </ns1:getClosedDate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### Response
Response Fields

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [ReportClosedDateValue](../data/ReportClosedDateValue.md) | Container of information to be acquired. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getClosedDateResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:closedDate>20120303</ns1:closedDate>
            </ns1:rval>
        </ns1:getClosedDateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
