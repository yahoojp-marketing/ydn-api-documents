# ReportDefinitionService
Use this service to get or add report definition. <br>
Report defines report type, date range, and fields. <br>
It provides operation to get available report fields for specific report type.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/ReportDefinitionService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/ReportDefinitionService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Retrieves and adds report definitions.<br>
If registered as template: The maximum of setting definition is 30.<br>
If not registered as template: There is no limit in setting definition.<br>
<br>
[Notes]<br>
Report definition can be confirmed only by the same authentic method when report definition is created.<br>
- When created by normal authentication: Cannot confirm by on behalf of access.<br>
- When created by on behalf of access: Cannot confirm by normal authentication.<br>

#### Operation
Describes operations provided by ReportDefinitionService.

## get
### Request
Retrieves the report definition.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| selector | ○ | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | Report definition for the target of the operation. |

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
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:reportIds>9000000001</ns1:reportIds>
                <ns1:reportIds>9000000002</ns1:reportIds>               
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
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
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
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionPage](../data/ReportDefinitionPage.md) | Entry of report definition. | 

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
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>AD</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sortFields>+DAY</ns1:sortFields>
                        <ns1:fields>IO_ID</ns1:fields>
                        <ns1:fields>IO_NAME</ns1:fields>
                        <ns1:fields>CAMPAIGN_ID</ns1:fields>
                        <ns1:fields>CAMPAIGN_NAME</ns1:fields>
                        <ns1:fields>ADGROUP_ID</ns1:fields>
                        <ns1:fields>ADGROUP_NAME</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## getReportFields
### Request
Returns usable report fields by report type.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
|accountId | ○ | xsd:long | Account ID |
|reportCategory | ○ | enum [ReportCategory](../data/ReportCategory.md) | Report format. |
|lang |  | enum [ReportLang](../data/ReportLang.md) | Output language.<br>Japanese or English can be selected. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:reportType>INTEREST_CATEGORY</ns1:reportType>
            <ns1:lang>JA</ns1:lang>
        </ns1:getReportFields>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (On-Behalf-Of Account) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:reportType>INTEREST_CATEGORY</ns1:reportType>
            <ns1:lang>JA</ns1:lang>
        </ns1:getReportFields>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | Usable report entry to be acquired.
| error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFieldsResponse>
            <ns1:rval>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                <ns1:field>
                    <ns1:fieldName>IO_ID</ns1:fieldName>
                    <ns1:displayFieldName>Account ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>accountID</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CAMPAIGN_ID</ns1:fieldName>
                    <ns1:displayFieldName>Campaign ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>campaignID</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CAMPAIGN_NAME</ns1:fieldName>
                    <ns1:displayFieldName>Campaign Name</ns1:displayFieldName>
                    <ns1:xmlAttributeName>campaignName</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADGROUP_ID</ns1:fieldName>
                    <ns1:displayFieldName>Ad Group ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adGroupID</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>ADGROUP_NAME</ns1:fieldName>
                    <ns1:displayFieldName>Ad Group Name</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adGroupName</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>MONTH</ns1:fieldName>
                    <ns1:displayFieldName>Month</ns1:displayFieldName>
                    <ns1:xmlAttributeName>month</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DAY</ns1:fieldName>
                    <ns1:displayFieldName>Daily</ns1:displayFieldName>
                    <ns1:xmlAttributeName>daily</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DELIVER</ns1:fieldName>
                    <ns1:displayFieldName>Ad Distribution</ns1:displayFieldName>
                    <ns1:xmlAttributeName>adDistribution</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>DEVICE</ns1:fieldName>
                    <ns1:displayFieldName>Device</ns1:displayFieldName>
                    <ns1:xmlAttributeName>device</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>INTEREST_CATEGORY</ns1:fieldName>
                    <ns1:displayFieldName>Interest Category</ns1:displayFieldName>
                    <ns1:xmlAttributeName>interestCategory</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CARRIER</ns1:fieldName>
                    <ns1:displayFieldName>Carrier</ns1:displayFieldName>
                    <ns1:xmlAttributeName>carrier</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>IMPS</ns1:fieldName>
                    <ns1:displayFieldName>Impressions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CLICK_RATE</ns1:fieldName>
                    <ns1:displayFieldName>CTR</ns1:displayFieldName>
                    <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COST</ns1:fieldName>
                    <ns1:displayFieldName>Cost</ns1:displayFieldName>
                    <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>CLICK</ns1:fieldName>
                    <ns1:displayFieldName>Clicks</ns1:displayFieldName>
                    <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>AVG_CPC</ns1:fieldName>
                    <ns1:displayFieldName>Avg. CPC</ns1:displayFieldName>
                    <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>AVG_DELIVER_RANK</ns1:fieldName>
                    <ns1:displayFieldName>Avg. Position</ns1:displayFieldName>
                    <ns1:xmlAttributeName>averagePosition</ns1:xmlAttributeName>
                </ns1:field>
            </ns1:rval>
        </ns1:getReportFieldsResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```															

## mutate(ADD)
### Request
Adds report definitions.

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md)|Displays operation target report definitions and operation content. | 

##### Request Sample (For AdHoc Report: Account, Campaign, Ad Group, Ad, Destination URL)
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
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxADReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>AD_ID</ns1:fields>
               <ns1:fields>AD_NAME</ns1:fields>
               <ns1:fields>AD_TYPE</ns1:fields>
               <ns1:fields>KEYWORD_ID</ns1:fields>
               <ns1:fields>KEYWORD_NAME</ns1:fields>
               <ns1:fields>URL_ID</ns1:fields>
               <ns1:fields>URL_NAME</ns1:fields>
               <ns1:fields>PREF_ID</ns1:fields>
               <ns1:fields>PREF_NAME</ns1:fields>
               <ns1:fields>LOCATION_ID</ns1:fields>
               <ns1:fields>LOCATION_NAME</ns1:fields>
               <ns1:fields>CITY_ID</ns1:fields>
               <ns1:fields>CITY_NAME</ns1:fields>
               <ns1:fields>WARD_ID</ns1:fields>
               <ns1:fields>WARD_NAME</ns1:fields>
               <ns1:fields>GENDER</ns1:fields>
               <ns1:fields>AGE</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>HOUR</ns1:fields>
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>AD_STYLE</ns1:fields>
               <ns1:fields>MEDIA_ID</ns1:fields>
               <ns1:fields>MEDIA_NAME</ns1:fields>
               <ns1:fields>MEDIA_FILE_NAME</ns1:fields>
               <ns1:fields>MEDIA_AD_FORMAT</ns1:fields>
               <ns1:fields>AD_TITLE</ns1:fields>
               <ns1:fields>DESCRIPTION1</ns1:fields>
               <ns1:fields>DESCRIPTION2</ns1:fields>
               <ns1:fields>DISPLAY_URL</ns1:fields>
               <ns1:fields>SEARCHKEYWORD_ID</ns1:fields>
               <ns1:fields>SEARCHKEYWORD</ns1:fields>
               <ns1:fields>CONVERSION_LABEL</ns1:fields>
               <ns1:fields>CONVERSION_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>CONVERSION</ns1:fields>
               <ns1:fields>CONVERSION_RATE</ns1:fields>
               <ns1:fields>CPA</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:fields>REVENUE</ns1:fields>
               <ns1:fields>REVENUE_CONVERSION</ns1:fields>
               <ns1:fields>TOTAL_VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>INVIEW_RATE</ns1:fields>
               <ns1:fields>INVIEW_CLICK</ns1:fields>
               <ns1:fields>INVIEW_CLICK_RATE</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:addTemplate>NO</ns1:addTemplate>
            </ns1:operand>
            <ns1:operand>
               <ns1:reportName>SandboxADReport_xml</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>AD_ID</ns1:fields>
               <ns1:fields>AD_NAME</ns1:fields>
               <ns1:fields>AD_TYPE</ns1:fields>
               <ns1:fields>KEYWORD_ID</ns1:fields>
               <ns1:fields>KEYWORD_NAME</ns1:fields>
               <ns1:fields>URL_ID</ns1:fields>
               <ns1:fields>URL_NAME</ns1:fields>
               <ns1:fields>PREF_ID</ns1:fields>
               <ns1:fields>PREF_NAME</ns1:fields>
               <ns1:fields>LOCATION_ID</ns1:fields>
               <ns1:fields>LOCATION_NAME</ns1:fields>
               <ns1:fields>CITY_ID</ns1:fields>
               <ns1:fields>CITY_NAME</ns1:fields>
               <ns1:fields>WARD_ID</ns1:fields>
               <ns1:fields>WARD_NAME</ns1:fields>
               <ns1:fields>GENDER</ns1:fields>
               <ns1:fields>AGE</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>HOUR</ns1:fields>
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>AD_STYLE</ns1:fields>
               <ns1:fields>MEDIA_ID</ns1:fields>
               <ns1:fields>MEDIA_NAME</ns1:fields>
               <ns1:fields>MEDIA_FILE_NAME</ns1:fields>
               <ns1:fields>MEDIA_AD_FORMAT</ns1:fields>
               <ns1:fields>AD_TITLE</ns1:fields>
               <ns1:fields>DESCRIPTION1</ns1:fields>
               <ns1:fields>DESCRIPTION2</ns1:fields>
               <ns1:fields>DISPLAY_URL</ns1:fields>
               <ns1:fields>SEARCHKEYWORD_ID</ns1:fields>
               <ns1:fields>SEARCHKEYWORD</ns1:fields>
               <ns1:fields>CONVERSION_LABEL</ns1:fields>
               <ns1:fields>CONVERSION_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>CONVERSION</ns1:fields>
               <ns1:fields>CONVERSION_RATE</ns1:fields>
               <ns1:fields>CPA</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:fields>REVENUE</ns1:fields>
               <ns1:fields>REVENUE_CONVERSION</ns1:fields>
               <ns1:fields>TOTAL_VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>INVIEW_RATE</ns1:fields>
               <ns1:fields>INVIEW_CLICK</ns1:fields>
               <ns1:fields>INVIEW_CLICK_RATE</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:addTemplate>YES</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For AdHoc Report: Interest Category)
```xml
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
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxINTEREST_CATEGORYReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>DEVICE</ns1:fields>
               <ns1:fields>INTEREST_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:addTemplate>NO</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For AdHoc Report: Site Category)
```xml
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
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxSITE_CATEGORYReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>DEVICE</ns1:fields>
               <ns1:fields>SITE_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:frequency/>
               <ns1:specifyDay/>
               <ns1:addTemplate>NO</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For AdHoc Report: Ad Delivery URL)
```xml
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
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxURLReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>              
               <ns1:fields>URL_ID</ns1:fields>
               <ns1:fields>URL_NAME</ns1:fields>              
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>              
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>DEVICE</ns1:fields>
               <ns1:fields>CONVERSION_LABEL</ns1:fields>
               <ns1:fields>CONVERSION_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>CONVERSION</ns1:fields>
               <ns1:fields>CONVERSION_RATE</ns1:fields>
               <ns1:fields>CPA</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:fields>REVENUE</ns1:fields>
               <ns1:fields>REVENUE_CONVERSION</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:addTemplate>NO</ns1:addTemplate>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For Scheduled Report: Frequency)
```xml
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
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxFREQUENCYReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:frequencyRange>MONTHLY</ns1:frequencyRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>AD_ID</ns1:fields>
               <ns1:fields>AD_NAME</ns1:fields>            
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>           
               <ns1:fields>FREQUENCY</ns1:fields>              
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>              
               <ns1:fields>CONVERSION</ns1:fields>
               <ns1:fields>CONVERSION_RATE</ns1:fields>
               <ns1:fields>CPA</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:frequency/>SPECIFYDAY<ns1:frequency/>
               <ns1:specifyDay/>10<ns1:specifyDay/>
               <ns1:addTemplate>NO</ns1:addTemplate>
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
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:reportName>SandboxADReport_csv</ns1:reportName>
               <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
               <ns1:dateRange>
                  <ns1:startDate>20141103</ns1:startDate>
                  <ns1:endDate>20141202</ns1:endDate>
               </ns1:dateRange>
               <ns1:sortFields>+DAY</ns1:sortFields>
               <ns1:sortFields>+IO_ID</ns1:sortFields>
               <ns1:fields>IO_ID</ns1:fields>
               <ns1:fields>IO_NAME</ns1:fields>
               <ns1:fields>CAMPAIGN_ID</ns1:fields>
               <ns1:fields>CAMPAIGN_NAME</ns1:fields>
               <ns1:fields>ADGROUP_ID</ns1:fields>
               <ns1:fields>ADGROUP_NAME</ns1:fields>
               <ns1:fields>AD_ID</ns1:fields>
               <ns1:fields>AD_NAME</ns1:fields>
               <ns1:fields>AD_TYPE</ns1:fields>
               <ns1:fields>KEYWORD_ID</ns1:fields>
               <ns1:fields>KEYWORD_NAME</ns1:fields>
               <ns1:fields>URL_ID</ns1:fields>
               <ns1:fields>URL_NAME</ns1:fields>
               <ns1:fields>PREF_ID</ns1:fields>
               <ns1:fields>PREF_NAME</ns1:fields>
               <ns1:fields>LOCATION_ID</ns1:fields>
               <ns1:fields>LOCATION_NAME</ns1:fields>
               <ns1:fields>CITY_ID</ns1:fields>
               <ns1:fields>CITY_NAME</ns1:fields>
               <ns1:fields>WARD_ID</ns1:fields>
               <ns1:fields>WARD_NAME</ns1:fields>
               <ns1:fields>GENDER</ns1:fields>
               <ns1:fields>AGE</ns1:fields>
               <ns1:fields>MONTH</ns1:fields>
               <ns1:fields>DAY</ns1:fields>
               <ns1:fields>HOUR</ns1:fields>
               <ns1:fields>DELIVER</ns1:fields>
               <ns1:fields>AD_STYLE</ns1:fields>
               <ns1:fields>MEDIA_ID</ns1:fields>
               <ns1:fields>MEDIA_NAME</ns1:fields>
               <ns1:fields>MEDIA_FILE_NAME</ns1:fields>
               <ns1:fields>MEDIA_AD_FORMAT</ns1:fields>
               <ns1:fields>AD_TITLE</ns1:fields>
               <ns1:fields>DESCRIPTION1</ns1:fields>
               <ns1:fields>DESCRIPTION2</ns1:fields>
               <ns1:fields>DISPLAY_URL</ns1:fields>
               <ns1:fields>SEARCHKEYWORD_ID</ns1:fields>
               <ns1:fields>SEARCHKEYWORD</ns1:fields>
               <ns1:fields>CONVERSION_LABEL</ns1:fields>
               <ns1:fields>CONVERSION_CATEGORY</ns1:fields>
               <ns1:fields>CARRIER</ns1:fields>
               <ns1:fields>IMPS</ns1:fields>
               <ns1:fields>CLICK_RATE</ns1:fields>
               <ns1:fields>COST</ns1:fields>
               <ns1:fields>CLICK</ns1:fields>
               <ns1:fields>AVG_CPC</ns1:fields>
               <ns1:fields>CONVERSION</ns1:fields>
               <ns1:fields>CONVERSION_RATE</ns1:fields>
               <ns1:fields>CPA</ns1:fields>
               <ns1:fields>AVG_DELIVER_RANK</ns1:fields>
               <ns1:fields>REVENUE</ns1:fields>
               <ns1:fields>REVENUE_CONVERSION</ns1:fields>
               <ns1:fields>TOTAL_VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>VIEWABLE_IMPS</ns1:fields>
               <ns1:fields>INVIEW_RATE</ns1:fields>
               <ns1:fields>INVIEW_CLICK</ns1:fields>
               <ns1:fields>INVIEW_CLICK_RATE</ns1:fields>
               <ns1:format>CSV</ns1:format>
               <ns1:encode>UTF-8</ns1:encode>
               <ns1:zip>ON</ns1:zip>
               <ns1:lang>EN</ns1:lang>
               <ns1:addTemplate>NO</ns1:addTemplate>
            </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container holding report definitions, including operation results. |
| error | [Error](../data/Error.md) | An error. | 

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
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>ReportDefinitionPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:ReportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>AD</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sortFields>+DAY</ns1:sortFields>
                        <ns1:fields>IO_ID</ns1:fields>
                        <ns1:fields>IO_NAME</ns1:fields>
                        <ns1:fields>CAMPAIGN_ID</ns1:fields>
                        <ns1:fields>CAMPAIGN_NAME</ns1:fields>
                        <ns1:fields>ADGROUP_ID</ns1:fields>
                        <ns1:fields>ADGROUP_NAME</ns1:fields>
                        <ns1:format>CSV</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>NO</ns1:addTemplate>
                    </ns1:ReportDefinition>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:ReportDefinition>
                        <ns1:reportId>9000000002</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_xml</ns1:reportName>
                        <ns1:reportType>AD</ns1:reportType>
                        <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                        <ns1:sortFields>+DAY</ns1:sortFields>
                        <ns1:fields>IO_ID</ns1:fields>
                        <ns1:fields>IO_NAME</ns1:fields>
                        <ns1:fields>CAMPAIGN_ID</ns1:fields>
                        <ns1:fields>CAMPAIGN_NAME</ns1:fields>
                        <ns1:fields>ADGROUP_ID</ns1:fields>
                        <ns1:fields>ADGROUP_NAME</ns1:fields>
                        <ns1:format>XML</ns1:format>
                        <ns1:encode>UTF-8</ns1:encode>
                        <ns1:zip>ON</ns1:zip>
                        <ns1:lang>EN</ns1:lang>
                        <ns1:frequency>SPECIFYDAY</ns1:frequency>
                        <ns1:specifyDay>10</ns1:specifyDay>
                        <ns1:addTemplate>YES</ns1:addTemplate>
                    </ns1:ReportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Deletes the report definition.。

| Parameter | Req? | Value | Description | 
|---|---|---|---|
| operations | ○ | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) |Report definition or operation elements of target of the operation. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:reportId>1000000002</ns1:reportId>
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
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:reportId>1000000002</ns1:reportId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container of report definition including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportDefinitionService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
           <ns1:rval>
             <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
             <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
             <ns1:values>
                 <ns1:operationSucceeded>true</ns1:operationSucceeded>
                 <ns1:reportDefinition>
                     <ns1:reportId>1000000001</ns1:reportId>
               </ns1:reportDefinition>
             </ns1:values>
             <ns1:values>
                 <ns1:operationSucceeded>true</ns1:operationSucceeded>
                 <ns1:reportDefinition>
                     <ns1:reportId>1000000002</ns1:reportId>
               </ns1:reportDefinition>
             </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
