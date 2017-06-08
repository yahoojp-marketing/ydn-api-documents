# Yahoo! JAPAN Display AD Network Report (From Ver.5.1)
## What is “Performance Report”?
Performance Report is a function of confirming performance of Campaign, Ad Group, Ad, Keyword, etc. 
To display report, creation of report and report template will be required.
Customizing is possible when creating report, like setting item display, performance period, etc.
Creating report will be more easier by using the recommended report setting.
*This process is valid for YDN API Ver.5.1 or later.

Report functions supported in Campaign Management Tool are also available from API.   
  
## How to operate from YDN API
To display the performance report, use the two services below from YDN API.    

##### 1.	ReportDefinitionService 
ReportDefinitionService can retrieve and add/delete the report definition. 
Report definition can be created from designating the report field.   
  
##### 2.	ReportService
ReportService can retrieve and add/delete the report.
It also can retrieve the Download URL of report.

# Scenerio Sample
This is introducing the process from creating to deleting the report template and actual report, to retrieve Performance Report, using YDN API. 

#### 1.	Retrieve Field of Template
Use getReportFields of ReportDefinitionService.
Retrieving list of available report fields by designating ReportCategory.
Each report fields encapsulate the Field Name, Display Name (English), and XML Attribute

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

#### 2.	Create Template
Use mutat:add of ReportDefinitionService.  
Creates the report template.  

##### Request Sample [AdHoc Report: For Account, Campaign, Ad Group, Ad, Destination URL]  
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
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample [Schedule Report: For Frequency]  
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

#### 3.	Create Report 
Use mutate:add of ReportService.  
Creates report from designated ReportID.  
*This process is not necessary for Scheduled Report.  

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
#### 4.	Confirm the Report Status
Use get of ReportService.  
Can confirm the report creation status. 

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

#### 5.	Download Report
Uses getDownloadUrl of ReportService.  
Retrieves report files by designating Account ID and/or Report Job ID.  

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
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
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
                    <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V5/download/XXXXXXXXXXXXXXXXXXX</ns1:downloadUrl>
                    </ns1:reportDownloadUrl>
                </ns1:values>
            </ns1:rval>
        </ns1:getDownloadUrlResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### 6.	Delete Report
Use mutate:remove of ReportService.  
Deletes downloaded report from ReportList.    

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

#### 7.	Delete Report Template
Uses mutate:remove of ReportDefinitionService.  
Deletes the unnecessary defined report.  

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
