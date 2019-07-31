# ReportDefinitionService
ReportDefinitionService acquires, creates, and deletes reports. <br>
Report defines report type, date range, and fields. <br>
It also includes an operation that acquires report download URLs.


#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201907/ReportDefinitionService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201907/ReportDefinitionService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201907/ReportDefinition

#### Service Overview
The following operations are provided:
- Get reports
- Add reports
- Delete reports
- Get the date of report completion
- Get report fields' information

[Maximum number of report download job]
- Up to 60 report download jobs can be added for each regular or proxy authentications combined.<br>
*If you wish to add more jobs though the upper saving limit is reached, delete some of the download jobs you already saved.<br>

[Notes]<br>
- Reports can be downloaded from the URL created with 'get' method.<br>
The URL is valid in the first 5 minutes after the status becomes COMPLETED.
- Any ad data without actual performance is not output for all report types.
- Report download jobs will be automatically deleted after a week (7 days) from requested.

#### Operation
Describes operations provided by ReportDefinitionService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)
+ [getClosedDate](#getcloseddate)
+ [getReportFields](#getreportfields)

#### Object
[ReportDefinition](../data/ReportDefinition)

## get

### Request
Retrieves the report.

| Parameter | Requirement | Value | Description |
|---|---|---|---|
| selector | required | [ReportDefinitionSelector](../data/ReportDefinition/ReportDefinitionSelector.md) | Operation target report. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <selector>
        <accountId>100000001</accountId>
        <reportJobIds>1111</reportJobIds>
        <reportJobIds>1111</reportJobIds>
        <paging>
          <ns2:startIndex>1</ns2:startIndex>
          <ns2:numberResults>10</ns2:numberResults>
        </paging>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription |
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinition/ReportDefinitionPage.md) | Container of report definitions to be acquired. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1551686141084</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ReportDefinition">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>ReportDefinitionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:reportDownloadUrl>https://location.im.yahooapis.jp/ReportService/V201907/XXXXXXXX</ns2:reportDownloadUrl>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>20160101</ns2:startDate>
              <ns2:endDate>20161231</ns2:endDate>
            </ns2:dateRange>
            <ns2:filters>
              <ns2:field>TRACKING_URL</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>http://yahoo.co.jp</ns2:values>
              <ns2:values>http://marketing.yahoo.co.jp</ns2:values>
              <ns2:values>http://promotionalads.yahoo.co.jp</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>IMPS</ns2:field>
              <ns2:operator>GREATER_THAN</ns2:operator>
              <ns2:values>0</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>CAMPAIGN_ID</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>200000001</ns2:values>
              <ns2:values>200000002</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000004</ns2:values>
              <ns2:values>200000005</ns2:values>
            </ns2:filters>
            <ns2:sortFields>+ACCOUNT_ID</ns2:sortFields>
            <ns2:fields>ACCOUNT_ID</ns2:fields>
            <ns2:fields>ACCOUNT_NAME</ns2:fields>
            <ns2:fields>CAMPAIGN_ID</ns2:fields>
            <ns2:fields>CAMPAIGN_NAME</ns2:fields>
            <ns2:fields>ADGROUP_ID</ns2:fields>
            <ns2:fields>ADGROUP_NAME</ns2:fields>
            <ns2:fields>AD_ID</ns2:fields>
            <ns2:fields>AD_NAME</ns2:fields>
            <ns2:fields>AD_TYPE</ns2:fields>
            <ns2:fields>URL_ID</ns2:fields>
            <ns2:fields>URL_NAME</ns2:fields>
            <ns2:fields>PREF_ID</ns2:fields>
            <ns2:fields>PREF_NAME</ns2:fields>
            <ns2:fields>CITY_ID</ns2:fields>
            <ns2:fields>CITY_NAME</ns2:fields>
            <ns2:fields>WARD_ID</ns2:fields>
            <ns2:fields>WARD_NAME</ns2:fields>
            <ns2:fields>GENDER</ns2:fields>
            <ns2:fields>AGE</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:compress>OFF</ns2:compress>
            <ns2:language>EN</ns2:language>
          </ns2:reportDefinition>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)

### Request

| Parameter | Requirement | Value | Description |
|---|---|---|---|
| operations | required | [ReportDefinitionOperation](../data/ReportDefinition/ReportDefinitionOperation.md) | Displays operation target reports and operation content. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/ReportDefinition">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
          <reportName>Test Report </reportName>
          <dateRangeType>LAST_7_DAYS</dateRangeType>
          <filters>
            <field>ACCOUNT_ID</field>
            <operator>NOT_EQUALS</operator>
            <values>100</values>
          </filters>
          <sortFields>+ACCOUNT_ID</sortFields>
          <fields>ACCOUNT_ID</fields>
          <fields>ACCOUNT_NAME</fields>
          <fields>CAMPAIGN_ID</fields>
          <fields>CAMPAIGN_NAME</fields>
          <fields>ADGROUP_ID</fields>
          <fields>ADGROUP_NAME</fields>
          <fields>AD_ID</fields>
          <fields>AD_NAME</fields>
          <fields>AD_TYPE</fields>
          <fields>URL_ID</fields>
          <fields>URL_NAME</fields>
          <fields>PREF_ID</fields>
          <fields>PREF_NAME</fields>
          <fields>CITY_ID</fields>
          <fields>CITY_NAME</fields>
          <fields>WARD_ID</fields>
          <fields>WARD_NAME</fields>
          <fields>GENDER</fields>
          <fields>AGE</fields>
          <fields>MONTH</fields>
          <fields>DAY</fields>
          <format>CSV</format>
          <encode>UTF-8</encode>
          <zip>OFF</zip>
          <lang>JA</lang>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinition/ReportDefinitionReturnValue.md) | Container holding report, including operation results. | | error | [Error](../data/ReportDefinition/Error.md) | An error. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1551686141120</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:reportDownloadUrl>https://location.im.yahooapis.jp/ReportService/V201907/XXXXXXXX</ns2:reportDownloadUrl>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>20160101</ns2:startDate>
              <ns2:endDate>20161231</ns2:endDate>
            </ns2:dateRange>
            <ns2:filters>
              <ns2:field>TRACKING_URL</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>http://yahoo.co.jp</ns2:values>
              <ns2:values>http://marketing.yahoo.co.jp</ns2:values>
              <ns2:values>http://promotionalads.yahoo.co.jp</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>IMPS</ns2:field>
              <ns2:operator>GREATER_THAN</ns2:operator>
              <ns2:values>0</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>CAMPAIGN_ID</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>200000001</ns2:values>
              <ns2:values>200000002</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000004</ns2:values>
              <ns2:values>200000005</ns2:values>
            </ns2:filters>
            <ns2:sortFields>+ACCOUNT_ID</ns2:sortFields>
            <ns2:fields>ACCOUNT_ID</ns2:fields>
            <ns2:fields>ACCOUNT_NAME</ns2:fields>
            <ns2:fields>CAMPAIGN_ID</ns2:fields>
            <ns2:fields>CAMPAIGN_NAME</ns2:fields>
            <ns2:fields>ADGROUP_ID</ns2:fields>
            <ns2:fields>ADGROUP_NAME</ns2:fields>
            <ns2:fields>AD_ID</ns2:fields>
            <ns2:fields>AD_NAME</ns2:fields>
            <ns2:fields>AD_TYPE</ns2:fields>
            <ns2:fields>URL_ID</ns2:fields>
            <ns2:fields>URL_NAME</ns2:fields>
            <ns2:fields>PREF_ID</ns2:fields>
            <ns2:fields>PREF_NAME</ns2:fields>
            <ns2:fields>CITY_ID</ns2:fields>
            <ns2:fields>CITY_NAME</ns2:fields>
            <ns2:fields>WARD_ID</ns2:fields>
            <ns2:fields>WARD_NAME</ns2:fields>
            <ns2:fields>GENDER</ns2:fields>
            <ns2:fields>AGE</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:compress>OFF</ns2:compress>
            <ns2:language>EN</ns2:language>
          </ns2:reportDefinition>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)

### Request
Removes the report definition.

| Parameter | Requirement | Value | Description |
|---|---|---|---|
| operations | required | [ReportDefinitionOperation](../data/ReportDefinition/ReportDefinitionOperation.md) | Report or operation elements of target of the operation. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201907/ReportDefinition">
      <operations>
        <operator>REMOVE</operator>
        <accountId>11111</accountId>
        <operand>
          <reportJobId>22222</reportJobId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Description |
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinition/ReportDefinitionReturnValue.md) | Container of report including operation results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1551686141143</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>100</ns2:reportJobId>
            <ns2:reportName>sample Report</ns2:reportName>
            <ns2:reportJobStatus>COMPLETED</ns2:reportJobStatus>
            <ns2:reportDownloadUrl>https://location.im.yahooapis.jp/ReportService/V201907/XXXXXXXX</ns2:reportDownloadUrl>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>20160101</ns2:startDate>
              <ns2:endDate>20161231</ns2:endDate>
            </ns2:dateRange>
            <ns2:filters>
              <ns2:field>TRACKING_URL</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>http://yahoo.co.jp</ns2:values>
              <ns2:values>http://marketing.yahoo.co.jp</ns2:values>
              <ns2:values>http://promotionalads.yahoo.co.jp</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>IMPS</ns2:field>
              <ns2:operator>GREATER_THAN</ns2:operator>
              <ns2:values>0</ns2:values>
            </ns2:filters>
            <ns2:filters>
              <ns2:field>CAMPAIGN_ID</ns2:field>
              <ns2:operator>IN</ns2:operator>
              <ns2:values>200000001</ns2:values>
              <ns2:values>200000002</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000003</ns2:values>
              <ns2:values>200000004</ns2:values>
              <ns2:values>200000005</ns2:values>
            </ns2:filters>
            <ns2:sortFields>+ACCOUNT_ID</ns2:sortFields>
            <ns2:fields>ACCOUNT_ID</ns2:fields>
            <ns2:fields>ACCOUNT_NAME</ns2:fields>
            <ns2:fields>CAMPAIGN_ID</ns2:fields>
            <ns2:fields>CAMPAIGN_NAME</ns2:fields>
            <ns2:fields>ADGROUP_ID</ns2:fields>
            <ns2:fields>ADGROUP_NAME</ns2:fields>
            <ns2:fields>AD_ID</ns2:fields>
            <ns2:fields>AD_NAME</ns2:fields>
            <ns2:fields>AD_TYPE</ns2:fields>
            <ns2:fields>URL_ID</ns2:fields>
            <ns2:fields>URL_NAME</ns2:fields>
            <ns2:fields>PREF_ID</ns2:fields>
            <ns2:fields>PREF_NAME</ns2:fields>
            <ns2:fields>CITY_ID</ns2:fields>
            <ns2:fields>CITY_NAME</ns2:fields>
            <ns2:fields>WARD_ID</ns2:fields>
            <ns2:fields>WARD_NAME</ns2:fields>
            <ns2:fields>GENDER</ns2:fields>
            <ns2:fields>AGE</ns2:fields>
            <ns2:fields>MONTH</ns2:fields>
            <ns2:fields>DAY</ns2:fields>
            <ns2:format>CSV</ns2:format>
            <ns2:encode>UTF-8</ns2:encode>
            <ns2:compress>OFF</ns2:compress>
            <ns2:language>EN</ns2:language>
          </ns2:reportDefinition>
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
| selector | required | [ReportClosedDateSelector](../data/ReportDefinition/ReportClosedDateSelector.md) | Assigns operation target reports. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getClosedDate xmlns="http://im.yahooapis.jp/V201907/ReportDefinition">
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
| rval | [ReportClosedDateValue](../data/ReportDefinition/ReportClosedDateValue.md) | Container of information to be acquired. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1551686141454</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getClosedDateResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ReportDefinition">
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

## getReportFields

### Request

| Parameter | Requirement | Value | Description |
|---|---|---|---|
|reportCategory | ○ | enum [ReportCategory](../data/ReportDefinition/ReportCategory.md) | Report format. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReportFields xmlns="http://im.yahooapis.jp/V201907/ReportDefinition">
      <reportCategory>AD</reportCategory>
    </getReportFields>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription |
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinition/ReportDefinitionFieldValue.md) | Usable report entry to be acquired. | error | [Error](../data/ReportDefinition/Error.md) | An error. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1551686141101</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getReportFieldsResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/ReportDefinition">
      <ns2:rval>
        <ns2:fields>
          <ns2:fieldName>ACCOUNT_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>アカウントID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Account ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>accountID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ACCOUNT_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>アカウント名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Account Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>accountName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adgroupID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループ名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Group Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adgroupName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>広告ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>広告名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_TYPE</ns2:fieldName>
          <ns2:displayFieldNameJA>広告タイプ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Type</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adType</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>URL_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>リンク先URLID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Destination URL ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>destinationURLID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>URL_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>リンク先URL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Destination URL</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>destinationURL</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PREF_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>都道府県ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Prefecture ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>prefectureID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PREF_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>都道府県</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Prefectures</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>prefecture</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CITY_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>市区郡ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>City ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>cityID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CITY_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>市区郡</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>City</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>city</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>WARD_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>行政区ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ward ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>wardID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>WARD_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>行政区</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ward</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ward</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>GENDER</ns2:fieldName>
          <ns2:displayFieldNameJA>性別</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Gender</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>gender</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AGE</ns2:fieldName>
          <ns2:displayFieldNameJA>年齢</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Age</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>age</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MONTH</ns2:fieldName>
          <ns2:displayFieldNameJA>月</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Month</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>month</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DAY</ns2:fieldName>
          <ns2:displayFieldNameJA>日</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Daily</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>day</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>HOUR</ns2:fieldName>
          <ns2:displayFieldNameJA>時間</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Hourly</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>hourofday</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DELIVER</ns2:fieldName>
          <ns2:displayFieldNameJA>広告掲載方式</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Distribution</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>deliverName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DEVICE</ns2:fieldName>
          <ns2:displayFieldNameJA>デバイス</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Device</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>device</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_STYLE</ns2:fieldName>
          <ns2:displayFieldNameJA>掲載フォーマット（画像タイプ）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad Style (Image Type)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adStyle</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEDIA_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>メディアID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Media ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>mediaID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEDIA_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>メディア名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Media Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>mediaName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEDIA_FILE_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>ファイル名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>File Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>fileName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEDIA_AD_FORMAT</ns2:fieldName>
          <ns2:displayFieldNameJA>ピクセルサイズ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Pixel Size</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>pixelSize</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_TITLE</ns2:fieldName>
          <ns2:displayFieldNameJA>タイトル</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Title</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>title</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DESCRIPTION1</ns2:fieldName>
          <ns2:displayFieldNameJA>説明文1</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Description 1</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>description1</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DESCRIPTION2</ns2:fieldName>
          <ns2:displayFieldNameJA>説明文2</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Description 2</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>description2</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>DISPLAY_URL</ns2:fieldName>
          <ns2:displayFieldNameJA>表示URL</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Display URL</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>displayURL</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>SEARCHKEYWORD_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>サーチキーワードID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Search Keyword ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>searchKeywordID</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>SEARCHKEYWORD</ns2:fieldName>
          <ns2:displayFieldNameJA>サーチキーワード</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Search Keyword</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>searchKeyword</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_LABEL</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンラベル名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversion Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversionName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_RATE_OLD</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CPA_OLD</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AUTO_VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWED_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_25</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_50</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_75</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_95</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_100</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_PERCENT_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DURATION_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_CATEGORY</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン測定の目的</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Objective of Conversion Tracking</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>objectiveOfConversionTracking</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_RATE_OLD</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CPA_OLD</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AUTO_VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWED_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_PLAYS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_25</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_50</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_75</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_95</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_100</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_PERCENT_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DURATION_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CARRIER</ns2:fieldName>
          <ns2:displayFieldNameJA>キャリア</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Carrier</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>carrier</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_LAYOUT</ns2:fieldName>
          <ns2:displayFieldNameJA>レイアウト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Layout</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adLayout</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>IMAGE_OPTION</ns2:fieldName>
          <ns2:displayFieldNameJA>画像自動付与</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Dynamic Image Extensions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>imageOption</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>OS</ns2:fieldName>
          <ns2:displayFieldNameJA>OS</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>OS</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>os</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>APPLI</ns2:fieldName>
          <ns2:displayFieldNameJA>ウェブ/アプリ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Web/App</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>appli</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_TYPE</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンタイプ</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign Type</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignType</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>APP_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>アプリID/パッケージ名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>App ID/Package name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>appID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>APP_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>アプリ名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>App Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>appName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>APP_OS</ns2:fieldName>
          <ns2:displayFieldNameJA>アプリOS</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>App OS</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>appOS</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>インプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Impressions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>impressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>CTR</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ctr</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>cost</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Clicks</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>clicks</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPC</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPC</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. CPC</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>averageCpc</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_OLD</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions (old)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>totalConversionsOld</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_RATE_OLD</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン率（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversion Rate (old)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>totalConversionRateOld</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CPA_OLD</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost per Conversions (old)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costTotalConversionsOld</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_DELIVER_RANK</ns2:fieldName>
          <ns2:displayFieldNameJA>平均掲載順位</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. Position</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>averagePosition</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>REVENUE_OLD</ns2:fieldName>
          <ns2:displayFieldNameJA>合計売上金額（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Revenue (old)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>totalRevenueOld</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>REVENUE_CONVERSION_OLD</ns2:fieldName>
          <ns2:displayFieldNameJA>売上/コンバージョン数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Revenue per Conversions (old)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>revenueTotalConversionOld</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>TOTAL_VIEWABLE_IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>ビュー計測対象インプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Impressions on the measurement object</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>measurableImpressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>PREF_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PREF_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>GENDER</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AGE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIEWABLE_IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューインプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable Impressions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableImpressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>PREF_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PREF_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>GENDER</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AGE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューインプレッション率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable Impression Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableImpressionRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>PREF_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PREF_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>GENDER</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AGE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>ビュークリック数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable Clicks</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableClicks</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>PREF_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PREF_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>GENDER</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AGE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビュークリック率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable CTR</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableCtr</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>PREF_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PREF_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CITY_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_ID</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>WARD_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>GENDER</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AGE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AUTO_VIDEO_PLAYS</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の自動再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Auto Video Plays</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>autoVideoPlays</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK_VIDEO_PLAYS</ns2:fieldName>
          <ns2:displayFieldNameJA>クリックによる動画再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Click Video Plays</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>clickVideoPlays</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWED_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の再生率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Viewed Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewedRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPV</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPV</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Average CPV</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgCpv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_PLAYS</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が再生開始された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Plays</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoPlays</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_25</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が25%まで再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views to 25%</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo25</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_50</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が50%まで再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views to 50%</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo50</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_75</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が75%まで再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views to 75%</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo75</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_95</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が95%まで再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views to 95%</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo95</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_100</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が100%まで再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views to 100%</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo100</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_PERCENT_VIDEO_VIEWED</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の平均再生率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Average % of Video Viewed</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgPercentVideoViewed</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_DURATION_VIDEO_VIEWED</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の平均再生時間（秒）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Average Duration of Video Viewed</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgDurationVideoViewed</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS</ns2:fieldName>
          <ns2:displayFieldNameJA>動画再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video Views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViews</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PAID_VIDEO_VIEWS</ns2:fieldName>
          <ns2:displayFieldNameJA>課金が発生した動画再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Paid Video Views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>paidVideoViews</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PAID_VIDEO_VIEW_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>課金が発生した動画再生率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Paid Video View Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>paidVideoViewRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_3_SEC</ns2:fieldName>
          <ns2:displayFieldNameJA>動画が3秒以上再生された回数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>3-second Video Views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo3sec</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSIONS</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversion Rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost per Conversions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_LABEL</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>REVENUE</ns2:fieldName>
          <ns2:displayFieldNameJA>合計売上金額</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Revenue</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>revenue</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>REVENUE_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>売上/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Revenue per Conversions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>revenuePerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
      </ns2:rval>
    </ns2:getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
