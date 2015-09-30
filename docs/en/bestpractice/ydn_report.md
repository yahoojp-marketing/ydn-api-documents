# Yahoo! JAPAN Display AD Network Report (Ver.4.6 - Ver.5.0)
## What is “Performance Report”?
Performance Report is a function of confirming performance in Campaign, Ad Group, Ad, Keyword, etc.   
To display report, creation of report and report template will be required.  
Customizing report is possible, like setting hierarchy of performance, item display, summary period, etc.  
Creating report will be more easier by using the recommended report setting.    
  
## How to operate from YDN API
To display the performance report, use the two services below from YDN API.    

##### 1.	ReportDefinitionService 
ReportDefinitionService can retrieve and add/update/delete the report definition.   
Report definition will designate the report type, period or field.  
Also for the special report type, retrieval of report field will be distributed.    
  
##### 2.	ReportService
ReportService can retrieve and add/delete the report.  
It also can retrieve the Download URL of report.  

# Scenerio Sample
This is a process of create and delete of report template and actual report, to retrieve Performance Report, using YDN API.  

#### 1.	Retrieve Field of Template
Use getReportFields of ReportDefinitionService.  
Retrieve list of available report fields by designated ReportType.  
Each report fields encapsulate the field name, field data type, and enumerations.    
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportType>ACCOUNT</ns1:reportType>
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>1111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getReportFields>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:reportType>ACCOUNT</ns1:reportType>
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
                    <ns1:fieldName>ACCOUNTID</ns1:fieldName>
                    <ns1:displayFieldName>Account ID</ns1:displayFieldName>
                    <ns1:xmlAttributeName>accountID</ns1:xmlAttributeName>
                </ns1:field>
                <ns1:field>
                    <ns1:fieldName>COSTTOTALCONVERSIONS</ns1:fieldName>
                    <ns1:displayFieldName>Cost / Total Conversions</ns1:displayFieldName>
                    <ns1:xmlAttributeName>costTotalConversions</ns1:xmlAttributeName>
                </ns1:field>
            </ns1:rval>
        </ns1:getReportFieldsResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
#### 2.	Create Template
Use mutat:add of ReportDefinitionService.  
Creates the report template.  
It requires the following:  
・Name of report definition  
・Designating the type of PERFORMANCE_REPORT  
・Designating segment  
・Designating summary period  
・Designating creation time (Frequency)  
・Japanese/English selection  
・Designating output format   

##### Request Sample [AdHoc Report]  
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                    <ns1:dateRange>
                        <ns1:startDate>20120303</ns1:startDate>
                        <ns1:endDate>20120402</ns1:endDate>
                    </ns1:dateRange>
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
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
##### Request Sample [Schedule Report]  
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                    <ns1:format>CSV</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>
                    <ns1:addTemplate>YES</ns1:addTemplate>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
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
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                    <ns1:reportType>ACCOUNT</ns1:reportType>
                    <ns1:dateRangeType>THIS_MONTH</ns1:dateRangeType>                   
                    <ns1:sort>+DAY</ns1:sort>
                    <ns1:segments>DAY</ns1:segments>
                    <ns1:segments>DELIVER</ns1:segments>
                    <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                    <ns1:fields>ACCOUNTNAME</ns1:fields>
                    <ns1:fields>ACCOUNTID</ns1:fields>
                    <ns1:fields>DAY</ns1:fields>
                    <ns1:fields>DELIVER</ns1:fields>
                    <ns1:fields>DEVICE</ns1:fields>
                    <ns1:fields>IMPRESSIONS</ns1:fields>
                    <ns1:fields>CLICKS</ns1:fields>
                    <ns1:fields>CTR</ns1:fields>
                    <ns1:fields>AVERAGEPOSITION</ns1:fields>
                    <ns1:fields>COST</ns1:fields>
                    <ns1:fields>AVERAGECPC</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                    <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                    <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
                    <ns1:format>CSV</ns1:format>
                    <ns1:encode>UTF-8</ns1:encode>
                    <ns1:zip>ON</ns1:zip>
                    <ns1:lang>EN</ns1:lang>
                    <ns1:frequency>SPECIFYDAY</ns1:frequency>
                    <ns1:specifyDay>10</ns1:specifyDay>
                    <ns1:addTemplate>YES</ns1:addTemplate>
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:reportDefinition>
                        <ns1:reportId>9000000001</ns1:reportId>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:reportName>SandboxAccountReport_csv</ns1:reportName>
                        <ns1:reportType>ACCOUNT</ns1:reportType>
                        <ns1:dateRangeType>CUSTOM_DATE</ns1:dateRangeType>
                        <ns1:sort>+DAY</ns1:sort>
                        <ns1:segments>DAY</ns1:segments>
                        <ns1:segments>DELIVER</ns1:segments>
                        <ns1:segments>DEVICE_AND_CARRIER</ns1:segments>
                        <ns1:fields>ACCOUNTNAME</ns1:fields>
                        <ns1:fields>ACCOUNTID</ns1:fields>
                        <ns1:fields>DAY</ns1:fields>
                        <ns1:fields>DELIVER</ns1:fields>
                        <ns1:fields>DEVICE</ns1:fields>
                        <ns1:fields>IMPRESSIONS</ns1:fields>
                        <ns1:fields>CLICKS</ns1:fields>
                        <ns1:fields>CTR</ns1:fields>
                        <ns1:fields>AVERAGEPOSITION</ns1:fields>
                        <ns1:fields>COST</ns1:fields>
                        <ns1:fields>AVERAGECPC</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONS</ns1:fields>
                        <ns1:fields>TOTALCONVERSIONRATE</ns1:fields>
                        <ns1:fields>COSTTOTALCONVERSIONS</ns1:fields>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
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
##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
Retrieves report files by designating accountID and/or reportJobID.  
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
                        <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V3/download/dqy0_L5Oa9vS5z2BzN9dBOrL.f.4oSOB1O81JI_UmMa98_SXxeo8eQ21TfimDDSuizf990IRIVDf3YPqW8u5Jw--</ns1:downloadUrl>
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
                    <ns1:downloadUrl>https://sample.api.yahooapis.jp/report/V3/download/ikrR_BxdrsD2DE5Rd5ref4DRxt.rxBNB5r2sR5_D5Rs85_rbdss9XK98Dfimsdyjefx522245Dde2XaeR4x8Ic--</ns1:downloadUrl>
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
xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
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
xmlns:ns1="http://im.yahooapis.jp/V4">
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
xmlns:ns1="http://im.yahooapis.jp/V4">
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
#### 7.	Delete Report Template
Uses mutate:remove of ReportDefinitionService.  
Deletes the unnecessary defined report.  
##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V4">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
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
 xmlns:ns1="http://im.yahooapis.jp/V4">
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
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:operand>
                    <ns1:reportId>1000000001</ns1:reportId>
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
 xmlns:ns1="http://im.yahooapis.jp/V4"
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
                        <ns1:reportId>9000000001</ns1:reportId>
                    </ns1:reportDefinition>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
