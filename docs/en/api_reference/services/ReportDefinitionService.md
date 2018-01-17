# ReportDefinitionService
Use this service to get or add report definition. <br>
Report defines report type, date range, and fields. <br>
It provides operation to get available report fields for specific report type.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/ReportDefinitionService?wsdl |

#### Namespace
http://im.yahooapis.jp/V6

#### Service Overview
The following operations are provided:
- Get report definitions
- Add report definitions
- Delete report definitions
- Get report fields' information

[Maximum number of report definitions to be saved]
- Up to 30 definitions for a scheduled report can be added as a template for regular and proxy authentications combined.
- There is no upper limits to the number of report definitions for one-time report that is not saved as a template.<br>
Example：<br>
If you have already saved 20 report definitions as a report template for regular authentication, you can add a maximum of 10 definitions for proxy authentication.<br> 
　*If you wish to add more definitions though the upper saving limit is reached, delete some of the definitions you already saved.
 
[Note]
- All of the report definitions created using the same API account ID can be confirmed regardless of authentication method.

#### Operation
Describes operations provided by ReportDefinitionService.

## get
### Request
Retrieves the report definition.

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| selector | required | [ReportDefinitionSelector](../data/ReportDefinitionSelector.md) | Report definition for the target of the operation. |

##### Request Sample (Standard Authentification)
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
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>ReportService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
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
                       <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                       <ns1:filters>
                           <ns1:field>CAMPAIGN_ID</ns1:field>
                           <ns1:operator>EQUALS</ns1:operator>
                           <ns1:values>10001</ns1:values>
                       </ns1:filters>
                        <ns1:filters>
                           <ns1:field>ADGROUP_ID</ns1:field>
                           <ns1:operator>IN</ns1:operator>
                           <ns1:values>20000</ns1:values>
                           <ns1:values>20001</ns1:values>
                       </ns1:filters>                      
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
                        <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
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

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| accountId | required | xsd:long | Account ID. |
|reportCategory | ○ | enum [ReportCategory](../data/ReportCategory.md) | Report format. |
|lang |  | enum [ReportLang](../data/ReportLang.md) | Output language.
Japanese or English can be selected. | 

##### Request Sample (Standard Authentification)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
            <ns1:reportType>AD</ns1:reportType>
            <ns1:lang>EN</ns1:lang>
        </ns1:getReportFields>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Field | Data Type | Deescription | 
|---|---|---|
| rval | [ReportDefinitionFieldValue](../data/ReportDefinitionFieldValue.md) | Usable report entry to be acquired. | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>ReportDefinitionService</ns1:service>
         <ns1:remainingQuota>-1</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.3515</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getReportFieldsResponse>
         <ns1:rval>
            <ns1:operationSucceeded>true</ns1:operationSucceeded>
            <ns1:field>
               <ns1:fieldName>ACCOUNT_ID</ns1:fieldName>
               <ns1:displayFieldName>Account ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>accountID</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ACCOUNT_NAME</ns1:fieldName>
               <ns1:displayFieldName>Account Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>accountName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CAMPAIGN_ID</ns1:fieldName>
               <ns1:displayFieldName>Campaign ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>campaignID</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CAMPAIGN_NAME</ns1:fieldName>
               <ns1:displayFieldName>Campaign Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>campaignName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADGROUP_ID</ns1:fieldName>
               <ns1:displayFieldName>Ad Group ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>adgroupID</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>ADGROUP_NAME</ns1:fieldName>
               <ns1:displayFieldName>Ad Group Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>adgroupName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_ID</ns1:fieldName>
               <ns1:displayFieldName>Ad ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>adID</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_NAME</ns1:fieldName>
               <ns1:displayFieldName>Ad Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>adName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_TYPE</ns1:fieldName>
               <ns1:displayFieldName>Ad Type</ns1:displayFieldName>
               <ns1:xmlAttributeName>adType</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>URL_ID</ns1:fieldName>
               <ns1:displayFieldName>Destination URL ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>destinationURLID</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>URL_NAME</ns1:fieldName>
               <ns1:displayFieldName>Destination URL</ns1:displayFieldName>
               <ns1:xmlAttributeName>destinationURL</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>PREF_ID</ns1:fieldName>
               <ns1:displayFieldName>Prefecture ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>prefectureID</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>PREF_NAME</ns1:fieldName>
               <ns1:displayFieldName>Prefectures</ns1:displayFieldName>
               <ns1:xmlAttributeName>prefecture</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CITY_ID</ns1:fieldName>
               <ns1:displayFieldName>City ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>cityID</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CITY_NAME</ns1:fieldName>
               <ns1:displayFieldName>City</ns1:displayFieldName>
               <ns1:xmlAttributeName>city</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>WARD_ID</ns1:fieldName>
               <ns1:displayFieldName>Ward ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>wardID</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>WARD_NAME</ns1:fieldName>
               <ns1:displayFieldName>Ward</ns1:displayFieldName>
               <ns1:xmlAttributeName>ward</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>GENDER</ns1:fieldName>
               <ns1:displayFieldName>Gender</ns1:displayFieldName>
               <ns1:xmlAttributeName>gender</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AGE</ns1:fieldName>
               <ns1:displayFieldName>Age</ns1:displayFieldName>
               <ns1:xmlAttributeName>age</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>MONTH</ns1:fieldName>
               <ns1:displayFieldName>Month</ns1:displayFieldName>
               <ns1:xmlAttributeName>month</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DAY</ns1:fieldName>
               <ns1:displayFieldName>Daily</ns1:displayFieldName>
               <ns1:xmlAttributeName>day</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>HOUR</ns1:fieldName>
               <ns1:displayFieldName>Hourly</ns1:displayFieldName>
               <ns1:xmlAttributeName>hourofday</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DELIVER</ns1:fieldName>
               <ns1:displayFieldName>Ad Distribution</ns1:displayFieldName>
               <ns1:xmlAttributeName>deliverName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DEVICE</ns1:fieldName>
               <ns1:displayFieldName>Device</ns1:displayFieldName>
               <ns1:xmlAttributeName>device</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_STYLE</ns1:fieldName>
               <ns1:displayFieldName>Ad Style (Image Type)</ns1:displayFieldName>
               <ns1:xmlAttributeName>adStyle</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>MEDIA_ID</ns1:fieldName>
               <ns1:displayFieldName>Image ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>imageID</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>MEDIA_NAME</ns1:fieldName>
               <ns1:displayFieldName>Image Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>imageName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>MEDIA_FILE_NAME</ns1:fieldName>
               <ns1:displayFieldName>File Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>fileName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>MEDIA_AD_FORMAT</ns1:fieldName>
               <ns1:displayFieldName>Pixel Size</ns1:displayFieldName>
               <ns1:xmlAttributeName>pixelSize</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_TITLE</ns1:fieldName>
               <ns1:displayFieldName>Title</ns1:displayFieldName>
               <ns1:xmlAttributeName>title</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DESCRIPTION1</ns1:fieldName>
               <ns1:displayFieldName>Description 1</ns1:displayFieldName>
               <ns1:xmlAttributeName>description1</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DESCRIPTION2</ns1:fieldName>
               <ns1:displayFieldName>Description 2</ns1:displayFieldName>
               <ns1:xmlAttributeName>description2</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>DISPLAY_URL</ns1:fieldName>
               <ns1:displayFieldName>Display URL</ns1:displayFieldName>
               <ns1:xmlAttributeName>displayURL</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>SEARCHKEYWORD_ID</ns1:fieldName>
               <ns1:displayFieldName>Search Keyword ID</ns1:displayFieldName>
               <ns1:xmlAttributeName>searchKeywordID</ns1:xmlAttributeName>
               <ns1:filterable>false</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>SEARCHKEYWORD</ns1:fieldName>
               <ns1:displayFieldName>Search Keyword</ns1:displayFieldName>
               <ns1:xmlAttributeName>searchKeyword</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CONVERSION_LABEL</ns1:fieldName>
               <ns1:displayFieldName>Conversion Name</ns1:displayFieldName>
               <ns1:xmlAttributeName>conversionName</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CONVERSION_CATEGORY</ns1:fieldName>
               <ns1:displayFieldName>Objective of Conversion Tracking</ns1:displayFieldName>
               <ns1:xmlAttributeName>objectiveOfConversionTracking</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CARRIER</ns1:fieldName>
               <ns1:displayFieldName>Carrier</ns1:displayFieldName>
               <ns1:xmlAttributeName>carrier</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AD_LAYOUT</ns1:fieldName>
               <ns1:displayFieldName>Layout</ns1:displayFieldName>
               <ns1:xmlAttributeName>adLayout</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>IMAGE_OPTION</ns1:fieldName>
               <ns1:displayFieldName>Dynamic Image Extensions</ns1:displayFieldName>
               <ns1:xmlAttributeName>imageOption</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>OS</ns1:fieldName>
               <ns1:displayFieldName>OS</ns1:displayFieldName>
               <ns1:xmlAttributeName>os</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>APPLI</ns1:fieldName>
               <ns1:displayFieldName>Web/App</ns1:displayFieldName>
               <ns1:xmlAttributeName>appli</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>IMPS</ns1:fieldName>
               <ns1:displayFieldName>Impressions</ns1:displayFieldName>
               <ns1:xmlAttributeName>impressions</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CLICK_RATE</ns1:fieldName>
               <ns1:displayFieldName>CTR</ns1:displayFieldName>
               <ns1:xmlAttributeName>ctr</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>COST</ns1:fieldName>
               <ns1:displayFieldName>Cost</ns1:displayFieldName>
               <ns1:xmlAttributeName>cost</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CLICK</ns1:fieldName>
               <ns1:displayFieldName>Clicks</ns1:displayFieldName>
               <ns1:xmlAttributeName>clicks</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVG_CPC</ns1:fieldName>
               <ns1:displayFieldName>Avg. CPC</ns1:displayFieldName>
               <ns1:xmlAttributeName>averageCpc</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CONVERSION</ns1:fieldName>
               <ns1:displayFieldName>Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalConversions</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CONVERSION_RATE</ns1:fieldName>
               <ns1:displayFieldName>Total Conversion Rate</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalConversionRate</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CPA</ns1:fieldName>
               <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVG_DELIVER_RANK</ns1:fieldName>
               <ns1:displayFieldName>Avg. Position</ns1:displayFieldName>
               <ns1:xmlAttributeName>averagePosition</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>REVENUE</ns1:fieldName>
               <ns1:displayFieldName>Total Revenue</ns1:displayFieldName>
               <ns1:xmlAttributeName>totalRevenue</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>REVENUE_CONVERSION</ns1:fieldName>
               <ns1:displayFieldName>Rev. / Total Conversions</ns1:displayFieldName>
               <ns1:xmlAttributeName>revenueTotalConversion</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>TOTAL_VIEWABLE_IMPS</ns1:fieldName>
               <ns1:displayFieldName>Impressions on the measurement object</ns1:displayFieldName>
               <ns1:xmlAttributeName>measurableImpressions</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIEWABLE_IMPS</ns1:fieldName>
               <ns1:displayFieldName>Viewable Impressions</ns1:displayFieldName>
               <ns1:xmlAttributeName>viewableImpressions</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>INVIEW_RATE</ns1:fieldName>
               <ns1:displayFieldName>Viewable Impression Rate</ns1:displayFieldName>
               <ns1:xmlAttributeName>viewableImpressionRate</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>INVIEW_CLICK</ns1:fieldName>
               <ns1:displayFieldName>Viewable Clicks</ns1:displayFieldName>
               <ns1:xmlAttributeName>viewableClicks</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>INVIEW_CLICK_RATE</ns1:fieldName>
               <ns1:displayFieldName>Viewable CTR</ns1:displayFieldName>
               <ns1:xmlAttributeName>viewableCtr</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AUTO_VIDEO_PLAYS</ns1:fieldName>
               <ns1:displayFieldName>Auto Video Plays</ns1:displayFieldName>
               <ns1:xmlAttributeName>autoVideoPlays</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>CLICK_VIDEO_PLAYS</ns1:fieldName>
               <ns1:displayFieldName>Click Video Plays</ns1:displayFieldName>
               <ns1:xmlAttributeName>clickVideoPlays</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWED_RATE</ns1:fieldName>
               <ns1:displayFieldName>Video Viewed Rate</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewedRate</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVG_CPV</ns1:fieldName>
               <ns1:displayFieldName>Average CPV</ns1:displayFieldName>
               <ns1:xmlAttributeName>avgCpv</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_PLAYS</ns1:fieldName>
               <ns1:displayFieldName>Video Plays</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoPlays</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWS_TO_25</ns1:fieldName>
               <ns1:displayFieldName>Video Views to 25%</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewsTo25</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWS_TO_50</ns1:fieldName>
               <ns1:displayFieldName>Video Views to 50%</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewsTo50</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWS_TO_75</ns1:fieldName>
               <ns1:displayFieldName>Video Views to 75%</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewsTo75</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWS_TO_95</ns1:fieldName>
               <ns1:displayFieldName>Video Views to 95%</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewsTo95</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>VIDEO_VIEWS_TO_100</ns1:fieldName>
               <ns1:displayFieldName>Video Views to 100%</ns1:displayFieldName>
               <ns1:xmlAttributeName>videoViewsTo100</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVG_PERCENT_VIDEO_VIEWED</ns1:fieldName>
               <ns1:displayFieldName>Average % of Video Viewed</ns1:displayFieldName>
               <ns1:xmlAttributeName>avgPercentVideoViewed</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
            <ns1:field>
               <ns1:fieldName>AVG_DURATION_VIDEO_VIEWED</ns1:fieldName>
               <ns1:displayFieldName>Average Duration of Video Viewed</ns1:displayFieldName>
               <ns1:xmlAttributeName>avgDurationVideoViewed</ns1:xmlAttributeName>
               <ns1:filterable>true</ns1:filterable>
            </ns1:field>
         </ns1:rval>
      </ns1:getReportFieldsResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | required | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | Displays operation target report definitions and operation content. | 

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
               <ns1:filters>
                  <ns1:field>CAMPAIGN_ID</ns1:field>
                  <ns1:operator>IN</ns1:operator>
                  <ns1:values>1000</ns1:values>
                  <ns1:values>1001</ns1:values>
                  <ns1:values>1002</ns1:values>
               </ns1:filters>
               <ns1:filters>
                  <ns1:field>IMPS</ns1:field>
                  <ns1:operator>GREATER_THAN</ns1:operator>
                  <ns1:values>1500</ns1:values>
              </ns1:filters>
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

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container holding report definitions, including operation results. | | error | [Error](../data/Error.md) | An error. | 

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
            <ns1:ListReturnValue.Type>ReportDefinitionReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>9000000001</ns1:reportId>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                  <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                  <ns1:dateRange>
                     <ns1:startDate>20141103</ns1:startDate>
                     <ns1:endDate>20141202</ns1:endDate>
                  </ns1:dateRange>
                  <ns1:filters>
                     <ns1:field>CAMPAIGN_ID</ns1:field>
                     <ns1:operator>IN</ns1:operator>
                     <ns1:values>1000</ns1:values>
                     <ns1:values>1001</ns1:values>
                     <ns1:values>1002</ns1:values>
                  </ns1:filters>
                  <ns1:filters>
                     <ns1:field>IMPS</ns1:field>
                     <ns1:operator>GREATER_THAN</ns1:operator>
                     <ns1:values>1500</ns1:values>
                  </ns1:filters>
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
                  <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
                  <ns1:specifyDay>10</ns1:specifyDay>
                  <ns1:addTemplate>NO</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:reportDefinition>
                  <ns1:reportId>9000000002</ns1:reportId>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:reportName>SandboxAccountReport_xml</ns1:reportName>
                  <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
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
                  <ns1:format>XML</ns1:format>
                  <ns1:encode>UTF-8</ns1:encode>
                  <ns1:zip>ON</ns1:zip>
                  <ns1:lang>EN</ns1:lang>
                  <ns1:intervalType>SPECIFYDAY</ns1:intervalType>
                  <ns1:specifyDay>10</ns1:specifyDay>
                  <ns1:addTemplate>YES</ns1:addTemplate>
               </ns1:reportDefinition>
            </ns1:values>
         </ns1:rval>
      </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Removes the report definition.

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | required | [ReportDefinitionOperation](../data/ReportDefinitionOperation.md) | Report definition or operation elements of target of the operation. | 

##### Request Sample (Standard Authentification)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V6">
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

### Response
| Field | Data Type | Description | 
|---|---|---|
| rval | [ReportDefinitionReturnValue](../data/ReportDefinitionReturnValue.md) | Container of report definition including operation results. | 
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
