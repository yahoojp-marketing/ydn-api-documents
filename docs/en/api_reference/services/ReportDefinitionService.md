# ReportDefinitionService

ReportDefinitionService acquires, creates, and deletes reports. <br>
Report defines report type, date range, and fields. <br>
It also includes an operation that acquires report download URLs.


#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/ReportDefinitionService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/ReportDefinitionService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/ReportDefinition

#### Service Overview

The following operations are provided:

 - Get reports
 - Add reports
 - Delete reports
 - Get the date of report completion
 - Get report fields' information

[Maximum number of report download job]

 - Up to 60 report download jobs can be added for each regular or proxy authentications combined.
 - *If you wish to add more jobs though the upper saving limit is reached, delete some of the download jobs you already saved.

[Notes]

 - Reports can be downloaded from the URL created with 'get' method.
 - The URL is valid in the first 5 minutes after the status becomes COMPLETED.
 - Any ad data without actual performance is not output for all report types.
 - Report download jobs will be automatically deleted after a week (7 days) from requested.

  

#### Operation

Explains operations provided by ReportDefinitionService.

+ [get](#get)
+ [mutate(ADD)](#mutateadd)
+ [mutate(REMOVE)](#mutateremove)
+ [getClosedDate](#getcloseddate)
+ [getReportFields](#getreportfields)

## get

### Request

Retrieves the report.

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [ReportDefinitionSelector](../data/ReportDefinition/ReportDefinitionSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <selector>
        <accountId>100000001</accountId>
        <reportJobIds>1111</reportJobIds>
        <reportJobIds>1111</reportJobIds>
        <reportJobStatuses>IN_PROGRESS</reportJobStatuses>
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

| Parameter | Data Type |
| -------- | ------- |
| rval | [ReportDefinitionPage](../data/ReportDefinition/ReportDefinitionPage.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1574394452707</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/ReportDefinition">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <Page.Type>ReportDefinitionPage</Page.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>1111</ns2:reportJobId>
            <ns2:reportJobStatus>IN_PROGRESS</ns2:reportJobStatus>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
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



| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [ReportDefinitionOperation](../data/ReportDefinition/ReportDefinitionOperation.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/ReportDefinition">
      <operations>
        <operator>ADD</operator>
        <accountId>11111</accountId>
        <operand>
          <accountId>11111</accountId>
          <reportName>Test Report </reportName>
          <dateRangeType>LAST_7_DAYS</dateRangeType>
          <dateRange>
            <startDate>20191230</startDate>
            <endDate>20191231</endDate>
          </dateRange>
          <frequencyRange>WEEKLY</frequencyRange>
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
          <compress>OFF</compress>
          <language>JA</language>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [ReportDefinitionReturnValue](../data/ReportDefinition/ReportDefinitionReturnValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1574394452801</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>1111</ns2:reportJobId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
            <ns2:dateRangeType>CUSTOM_DATE</ns2:dateRangeType>
            <ns2:dateRange>
              <ns2:startDate>20160101</ns2:startDate>
              <ns2:endDate>20161231</ns2:endDate>
            </ns2:dateRange>
            <ns2:frequencyRange>WEEKLY</ns2:frequencyRange>
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
            <ns2:language>JA</ns2:language>
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

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| operations | Yes | [ReportDefinitionOperation](../data/ReportDefinition/ReportDefinitionOperation.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/ReportDefinition">
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

| Parameter | Data Type |
| -------- | ------- |
| rval | [ReportDefinitionReturnValue](../data/ReportDefinition/ReportDefinitionReturnValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1574394452850</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/ReportDefinition">
      <ns2:rval>
        <ListReturnValue.Type>ReportDefinitionReturnValue</ListReturnValue.Type>
        <Operation.Type>REMOVE</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:reportDefinition>
            <ns2:reportJobId>1111</ns2:reportJobId>
            <ns2:reportName>Sample LANDING_PAGE_URL Report</ns2:reportName>
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

| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| selector | Yes | [ReportClosedDateSelector](../data/ReportDefinition/ReportClosedDateSelector.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getClosedDate xmlns="http://im.yahooapis.jp/V201911/ReportDefinition">
      <selector>
        <accountId>12345</accountId>
      </selector>
    </getClosedDate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [ReportClosedDateValue](../data/ReportDefinition/ReportClosedDateValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1574394452880</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getClosedDateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/ReportDefinition">
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
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:key>REACH_REPORT_CLOSED_DATE</ns2:key>
          <ns2:closedDate>20180101</ns2:closedDate>
        </ns2:values>
      </ns2:rval>
    </ns2:getClosedDateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields

### Request



| Parameter | Required | Data Type |
| --------- | -------- | --------- |
| reportCategory | Yes | [ReportType](../data/ReportDefinition/ReportType.md) |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <getReportFields xmlns="http://im.yahooapis.jp/V201911/ReportDefinition">
      <reportCategory>AD</reportCategory>
    </getReportFields>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type |
| -------- | ------- |
| rval | [ReportDefinitionFieldValue](../data/ReportDefinition/ReportDefinitionFieldValue.md) |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/ReportDefinition" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>ReportDefinition</ns2:service>
      <ns2:requestTime>1574394452757</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getReportFieldsResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/ReportDefinition">
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
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PREF_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>都道府県</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Prefectures</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>prefecture</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CITY_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>市区郡ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>City ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>cityID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CITY_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>市区郡</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>City</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>city</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>WARD_ID</ns2:fieldName>
          <ns2:displayFieldNameJA>行政区ID</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ward ID</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>wardID</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>WARD_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>行政区</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ward</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ward</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>GENDER</ns2:fieldName>
          <ns2:displayFieldNameJA>性別</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Gender</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>gender</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AGE</ns2:fieldName>
          <ns2:displayFieldNameJA>年齢</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Age</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>age</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
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
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_25</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_50</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_75</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_95</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_100</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_PERCENT_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DURATION_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_ALL_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PAID_VIDEO_VIEWS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PAID_VIDEO_VIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_3_SEC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_RATE_VIA_AD_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV_VIA_AD_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_VALUE_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_VALUE_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_VALUE_VIA_AD_CLICK_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>IMPS_PREV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE_PREV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPM</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_VCPM</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>MEASURED_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>MEASURED_IMPS_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_10_SEC</ns2:impossibleCombinationFields>
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
          <ns2:fieldName>CAMPAIGN_LABEL_IDS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンラベルIDリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign label IDs (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignLabelIDs(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;LONG&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_LABELS</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンラベルリスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign labels</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignLabels</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CAMPAIGN_LABELS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーンラベルリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign labels (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignLabels(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_LABEL_IDS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループラベルIDリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad group label IDs (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adGroupLabelIDs(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;LONG&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_LABELS</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループラベルリスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad group labels</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adGroupLabels</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ADGROUP_LABELS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>広告グループラベルリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad group labels (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adGroupLabels(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_LABEL_IDS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>広告ラベルIDリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad label IDs (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adLabelIDs(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;LONG&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_LABELS</ns2:fieldName>
          <ns2:displayFieldNameJA>広告ラベルリスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad labels</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adLabels</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AD_LABELS_JSON</ns2:fieldName>
          <ns2:displayFieldNameJA>広告ラベルリスト（JSON）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Ad labels (JSON)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>adLabels(JSON)</ns2:xmlAttributeName>
          <ns2:fieldType>LIST&lt;STRING&gt;</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_NAME</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン名</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversion Name</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversionName</ns2:xmlAttributeName>
          <ns2:fieldType>STRING</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DELIVER_RANK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>TOTAL_VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>INVIEW_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_25</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_50</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_75</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_95</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_100</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_PERCENT_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_DURATION_VIDEO_VIEWED</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_ALL_CONV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PAID_VIDEO_VIEWS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>PAID_VIDEO_VIEW_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_3_SEC</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_RATE_VIA_AD_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>COST_PER_CONV_VIA_AD_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_VALUE_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>ALL_CONV_VALUE_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONV_VALUE_VIA_AD_CLICK_PER_COST</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>IMPS_PREV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CLICK_RATE_PREV</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_CPM</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>AVG_VCPM</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>MEASURED_IMPS</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_CLICK</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>MEASURED_IMPS_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_IMPS_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIEWABLE_CLICK_RATE</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>VIDEO_VIEWS_TO_10_SEC</ns2:impossibleCombinationFields>
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
          <ns2:fieldName>CAMPAIGN_GOALS</ns2:fieldName>
          <ns2:displayFieldNameJA>キャンペーン目的</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Campaign goals</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>campaignGoals</ns2:xmlAttributeName>
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
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>CTR</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ctr</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>cost</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Clicks</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>clicks</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPC</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPC</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. CPC</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgCpc</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_DELIVER_RANK</ns2:fieldName>
          <ns2:displayFieldNameJA>平均掲載順位</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. position</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgPosition</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>TOTAL_VIEWABLE_IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>メジャードインプレッション数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Measured impressions (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>measurableImpressionsPrevious</ns2:xmlAttributeName>
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
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIEWABLE_IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルインプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable impressions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableImpressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルインプレッション率（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable impression rate (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableImpressionRatePrevious</ns2:xmlAttributeName>
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
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルクリック数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable clicks (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableClicksPrevious</ns2:xmlAttributeName>
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
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>INVIEW_CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルクリック率（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable CTR (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableCtrPrevious</ns2:xmlAttributeName>
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
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPV</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPV</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. CPV</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgCpv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_25</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の25%再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>25% video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo25</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_50</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の50%再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>50% video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo50</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_75</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の75%再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>75% video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo75</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_95</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の95%再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>95% video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo95</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_100</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の100%再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>100% video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo100</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_PERCENT_VIDEO_VIEWED</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の平均再生開始率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. video view rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgVideoViewRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_DURATION_VIDEO_VIEWED</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の平均再生時間（秒）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. duration of video viewed</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgDurationOfVideoViewed</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の再生開始数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViews</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PAID_VIDEO_VIEWS</ns2:fieldName>
          <ns2:displayFieldNameJA>課金が発生した動画再生数（CPV課金キャンペーンのみ）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Paid video views (CPV)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>paidVideoViewsCPV</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>PAID_VIDEO_VIEW_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>課金が発生した動画再生率（CPV課金キャンペーンのみ）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Paid video view rate (CPV)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>paidVideoViewRateCPV</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_3_SEC</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の3秒再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>3 sec video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo3sec</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
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
          <ns2:displayFieldNameEN>Conv. rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost/conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_VALUE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValue</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VALUE_PER_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値/コンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value/conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValuePerConv</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン数（全て）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions (all)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ConversionsAll</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン率（全て）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. rate (all)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convRateAll</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数（全て）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost/conv. (all)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerConvAll</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV_VALUE</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（全て）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (all)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueAll</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VALUE_PER_ALL_CONV</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（全て）/コンバージョン数（全て）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (all)/conv. (all)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueAllPerConvAll</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSIONS_VIA_AD_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン数（クリック経由）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conversions (via click)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>conversionsViaClick</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONVERSION_RATE_VIA_AD_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョン率（クリック経由）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. rate (via click)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convRateViaClick</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>COST_PER_CONV_VIA_AD_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>コスト/コンバージョン数（クリック経由）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cost/conv. (via click)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>costPerConvViaClick</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_VALUE_VIA_AD_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（クリック経由）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (via click)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueViaClick</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VALUE_PER_CONV_VIA_AD_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（クリック経由）/コンバージョン数（クリック経由）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (via click)/conv. (via click)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueViaClickPerConvViaClick</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CROSS_DEVICE_CONVERSIONS</ns2:fieldName>
          <ns2:displayFieldNameJA>クロスデバイスコンバージョン数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Cross-device conv.</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>crossDeviceConv</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_VALUE_PER_COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値/コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value/cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValuePerCost</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>ALL_CONV_VALUE_PER_COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（全て）/コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (all)/cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueAllPerCost</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CONV_VALUE_VIA_AD_CLICK_PER_COST</ns2:fieldName>
          <ns2:displayFieldNameJA>コンバージョンの価値（クリック経由）/コスト</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Conv. value (via click)/cost</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>convValueViaClickPerCost</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>IMPS_PREV</ns2:fieldName>
          <ns2:displayFieldNameJA>インプレッション数（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Impressions (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>impressionsPrevious</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>CLICK_RATE_PREV</ns2:fieldName>
          <ns2:displayFieldNameJA>クリック率（旧）</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>CTR (previous)</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>ctrPrevious</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_CPM</ns2:fieldName>
          <ns2:displayFieldNameJA>平均CPM</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. CPM</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgCpm</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>AVG_VCPM</ns2:fieldName>
          <ns2:displayFieldNameJA>平均vCPM</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Avg. vCPM</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>avgVCpm</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEASURED_IMPS</ns2:fieldName>
          <ns2:displayFieldNameJA>メジャードインプレッション数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Measured impressions</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>measuredImpressions</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIEWABLE_CLICK</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルクリック数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable clicks</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableClicks</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>MEASURED_IMPS_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>メジャードインプレッション測定率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Measured impression rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>measuredImpressionRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIEWABLE_IMPS_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルインプレッション率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable impression rate</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableImpressionRate</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIEWABLE_CLICK_RATE</ns2:fieldName>
          <ns2:displayFieldNameJA>ビューアブルクリック率</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>Viewable CTR</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>viewableCtr</ns2:xmlAttributeName>
          <ns2:fieldType>DOUBLE</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
        <ns2:fields>
          <ns2:fieldName>VIDEO_VIEWS_TO_10_SEC</ns2:fieldName>
          <ns2:displayFieldNameJA>動画の10秒再生数</ns2:displayFieldNameJA>
          <ns2:displayFieldNameEN>10 sec video views</ns2:displayFieldNameEN>
          <ns2:xmlAttributeName>videoViewsTo10sec</ns2:xmlAttributeName>
          <ns2:fieldType>LONG</ns2:fieldType>
          <ns2:filterable>true</ns2:filterable>
          <ns2:impossibleCombinationFields>CONVERSION_NAME</ns2:impossibleCombinationFields>
          <ns2:impossibleCombinationFields>CONVERSION_CATEGORY</ns2:impossibleCombinationFields>
        </ns2:fields>
      </ns2:rval>
    </ns2:getReportFieldsResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
