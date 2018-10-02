# ReportService
ReportService acquires, creates, and deletes reports. <br>
It also includes an operation that acquires report download URLs.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/ReportService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/ReportService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201806/Report

#### Service Overview
The following operations are provided:
- Get reports
- Add reports
- Delete reports
- Get the date of report completion

[Maximum number of report download job]
- Up to 60 report download jobs can be added for each regular or proxy authentications combined.<br>
*If you wish to add more jobs though the upper saving limit is reached, delete some of the download jobs you already saved.<br>

[Notes]<br>
- Reports can be downloaded from the URL created with 'get' method.<br>
The URL is valid in the first 5 minutes after the status becomes COMPLETED.
- Any ad data without actual performance is not output for all report types.
- Report download jobs will be automatically deleted after a week (7 days) from requested.

#### Operation
Describes operations provided by ReportService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)
+ [getClosedDate](#getcloseddate)

#### Object
[Report](../data/Report)

## get

### Request
Acquires report related information. Download URL of reports can also be acquired by get method.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [ReportSelector](../data/Report/ReportSelector.md) | Operation target report. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <selector>
        <accountId>12345</accountId>
        <reportIds>1</reportIds>
        <reportIds>2</reportIds>
        <reportJobIds>100</reportJobIds>
        <reportJobIds>1000</reportJobIds>
        <reportJobStatuses>ACCEPTED</reportJobStatuses>
        <reportJobStatuses>COMPLETED</reportJobStatuses>
        <paging>
          <ns2:startIndex>10</ns2:startIndex>
          <ns2:numberResults>1340</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [ReportPage](../data/Report/ReportPage.md) | Container of report definitions to be acquired. | error | [Error](../data/Report/Error.md) | An error. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1528278915428</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Report">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>ReportPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>12345</ns2:accountId>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportId>1</ns2:reportId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:status>COMPLETED</ns2:status>
            <ns2:reportDownloadUrl>https://colo01.im.yahooapis.jp/ReportService/V201806/XXXXXXXX</ns2:reportDownloadUrl>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request
Creates a report.

| Parameter | Requirement | Value | Description |
|---|---|---|---|
| operations | required | [ReportJobOperation](../data/Report/ReportJobOperation.md) | Displays operation target reports and operation content. |


### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | Container of reports, including operation results. | error | [Error](../data/Report/Error.md) | An error. |


## mutate(REMOVE)

### Request
Deletes a report

| Parameter | Requirement | Value | Description |
|---|---|---|---|
| operations | required | [ReportJobOperation](../data/Report/ReportJobOperation.md) | Displays operation target reports and operation content. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201806/Report">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>1111</accountId>
          <reportId>2222</reportId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [ReportReturnValue](../data/Report/ReportReturnValue.md) | Container of reports, including operation results. | error | [Error](../data/Report/Error.md) | An error. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1528278915456</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Report">
      <ns2:rval>
        <ListReturnValue.Type>ReportReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportRecord>
            <ns2:accountId>12345</ns2:accountId>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportId>1</ns2:reportId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:status>COMPLETED</ns2:status>
            <ns2:reportDownloadUrl>https://colo01.im.yahooapis.jp/ReportService/V201806/XXXXXXXX</ns2:reportDownloadUrl>
          </ns2:reportRecord>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getClosedDate

### Request
Acquires date of report completion.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [ReportClosedDateSelector](../data/Report/ReportClosedDateSelector.md) | Assigns operation target reports. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getClosedDate xmlns="http://im.yahooapis.jp/V201806/Report">
      <selector>
        <accountId>12345</accountId>
      </selector>
    </getClosedDate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description |
|---|---|---|
| rval | [ReportClosedDateValue](../data/Report/ReportClosedDateValue.md) | Container of information to be acquired. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/Report" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>Report</ns2:service>
      <ns2:requestTime>1528278915475</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getClosedDateResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Report">
      <ns2:rval>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:key>FREQ_REPORT_CLOSED_DATE</ns2:key>
          <ns2:closedDate>20180101</ns2:closedDate>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:key>REPORT_CLOSED_DATE</ns2:key>
          <ns2:closedDate>20180101</ns2:closedDate>
        </ns2:values>
      </ns2:rval>
    </ns2:getClosedDateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
