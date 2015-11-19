# AdGroupTargetService
Retrieves and updates information related to target settings.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/AdGroupTargetService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/AdGroupTargetService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Performs ad group target settings.
#### Operation
Explains operations provided by AdGroupTargetService.

## get
### Request
Describes operations provided by AdGroupTargetService.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [AdGroupTargetSelector](../data/AdGroupTargetSelector.md) | Assigns targeting information.  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignIds>2222222</ns1:campaignIds>
                <ns1:adGroupIds>3333333</ns1:adGroupIds>
                <ns1:targetTypes>AD_SCHEDULE_TARGET</ns1:targetTypes>
                <ns1:targetTypes>GEO_TARGET</ns1:targetTypes>
                <ns1:targetTypes>AGE_TARGET</ns1:targetTypes>
                <ns1:targetTypes>INTEREST_CATEGORY</ns1:targetTypes>
                <ns1:targetTypes>SITE_CATEGORY</ns1:targetTypes>
                <ns1:targetTypes>SITE_RETARGETING</ns1:targetTypes>
                <ns1:targetTypes>SEARCH_TARGET</ns1:targetTypes>
                <ns1:targetTypes>PLACEMENT_TARGET</ns1:targetTypes>
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
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignIds>2222222</ns1:campaignIds>
                <ns1:adGroupIds>3333333</ns1:adGroupIds>
                <ns1:targetTypes>AD_SCHEDULE_TARGET</ns1:targetTypes>
                <ns1:targetTypes>GEO_TARGET</ns1:targetTypes>
                <ns1:targetTypes>AGE_TARGET</ns1:targetTypes>
                <ns1:targetTypes>INTEREST_CATEGORY</ns1:targetTypes>
                <ns1:targetTypes>SITE_CATEGORY</ns1:targetTypes>
                <ns1:targetTypes>SITE_RETARGETING</ns1:targetTypes>
                <ns1:targetTypes>SEARCH_TARGET</ns1:targetTypes>
                <ns1:targetTypes>PLACEMENT_TARGET</ns1:targetTypes>
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
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AdGroupTargetPage](../data/AdGroupTargetPage.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupTargetPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:targetList>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:targets xsi:type="ns1:AdScheduleTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>10</ns1:startHour>
                                <ns1:endHour>20</ns1:endHour>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>TUESDAY</ns1:dayOfWeek>
                                <ns1:startHour>10</ns1:startHour>
                                <ns1:endHour>20</ns1:endHour>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                                <ns1:startHour>2</ns1:startHour>
                                <ns1:endHour>22</ns1:endHour>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:GeoTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>GEO_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>GEO_TARGET</ns1:type>
                                <ns1:geo>TC-CI-00000102</ns1:geo>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:InterestCategoryTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>INTEREST_CATEGORY</ns1:type>
                            <ns1:targets>
                                <ns1:type>INTEREST_CATEGORY</ns1:type>
                                <ns1:category>TC-IC-20110160100</ns1:category>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SiteCategoryTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SITE_CATEGORY</ns1:type>
                            <ns1:targets>
                                <ns1:type>SITE_CATEGORY</ns1:type>
                                <ns1:category>TC-SC-10110110100100</ns1:category>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SiteRetargetingTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SITE_RETARGETING</ns1:type>
                            <ns1:targets>
                                <ns1:type>SITE_RETARGETING</ns1:type>
                                <ns1:targetListId>444444444</ns1:targetListId>
                                <ns1:targetListName>targetListName_1</ns1:targetListName>
                                <ns1:targetListStatus>EXISTS</ns1:targetListStatus>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SearchTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SEARCH_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>SEARCH_TARGET</ns1:type>
                                <ns1:searchKeywordListId>444444444</ns1:searchKeywordListId>
                                <ns1:searchKeywordListName>TEST SearchKeywordList</ns1:searchKeywordListName>
                                <ns1:searchKeywordListStatus>DELETED</ns1:searchKeywordListStatus>
                           </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:GenderTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>GENDER_TARGET</ns1:type>
                                <ns1:gender>ST_MALE</ns1:gender>
                                <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
                           </ns1:targets>
                            <ns1:targets>
                                <ns1:type>GENDER_TARGET</ns1:type>
                                <ns1:gender>ST_UNKNOWN</ns1:gender>
                           </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:AgeTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>AGE_TARGET</ns1:type>
                                <ns1:age>GT_RANGE22_29</ns1:age>
                                <ns1:estimateFlg>PAUSED</ns1:estimateFlg>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AGE_TARGET</ns1:type>
                                <ns1:age>GT_RANGE30_39</ns1:age>
                                <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AGE_TARGET</ns1:type>
                                <ns1:age>GT_UNKNOWN</ns1:age>
                            </ns1:targets>
                        </ns1:targets>
                    </ns1:targetList>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## mutate(SET)
### Request
Sets target information.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [AdGroupTargetOperation](../data/AdGroupTargetOperation.md) | Sets target information.  | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:targets xsi:type="ns1:AdScheduleTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                            <ns1:startHour>1</ns1:startHour>
                            <ns1:endHour>2</ns1:endHour>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                            <ns1:startHour>3</ns1:startHour>
                            <ns1:endHour>4</ns1:endHour>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:GeoTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>GEO_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>GEO_TARGET</ns1:type>
                            <ns1:geo>TC-CI-00000102</ns1:geo>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:InterestCategoryTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>INTEREST_CATEGORY</ns1:type>
                        <ns1:targets>
                            <ns1:type>INTEREST_CATEGORY</ns1:type>
                            <ns1:category>TC-IC-40150150100</ns1:category>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SiteCategoryTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>SITE_CATEGORY</ns1:type>
                        <ns1:targets>
                            <ns1:type>SITE_CATEGORY</ns1:type>
                            <ns1:category>TC-SC-10110140100100</ns1:category>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SiteRetargetingTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>SITE_RETARGETING</ns1:type>
                        <ns1:targets>
                            <ns1:type>SITE_RETARGETING</ns1:type>
                            <ns1:targetListId>1100000001</ns1:targetListId>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SearchTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>SEARCH_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>SEARCH_TARGET</ns1:type>
                            <ns1:searchKeywordListId>4444444444</ns1:searchKeywordListId>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:GenderTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>GENDER_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:gender>ST_MALE</ns1:gender>
                            <ns1:estimateFlg>PAUSED</ns1:estimateFlg>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:gender>ST_UNKNOWN</ns1:gender>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:AgeTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>AGE_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:age>GT_RANGE22_29</ns1:age>
                            <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:age>GT_UNKNOWN</ns1:age>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:PlacementTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>PLACEMENT_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>PLACEMENT_TARGET</ns1:type>
                            <ns1:urlListId>555555555</ns1:urlListId>
                            <ns1:urlListType>WHITE_LIST</ns1:urlListType>
                        </ns1:targets>
                    </ns1:targets>
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
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:targets xsi:type="ns1:AdScheduleTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                            <ns1:startHour>1</ns1:startHour>
                            <ns1:endHour>2</ns1:endHour>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                            <ns1:startHour>3</ns1:startHour>
                            <ns1:endHour>4</ns1:endHour>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:GeoTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>GEO_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>GEO_TARGET</ns1:type>
                            <ns1:geo>TC-CI-00000102</ns1:geo>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:InterestCategoryTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>INTEREST_CATEGORY</ns1:type>
                        <ns1:targets>
                            <ns1:type>INTEREST_CATEGORY</ns1:type>
                            <ns1:category>TC-IC-40150150100</ns1:category>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SiteCategoryTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>SITE_CATEGORY</ns1:type>
                        <ns1:targets>
                            <ns1:type>SITE_CATEGORY</ns1:type>
                            <ns1:category>TC-SC-10110140100100</ns1:category>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SiteRetargetingTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>SITE_RETARGETING</ns1:type>
                        <ns1:targets>
                            <ns1:type>SITE_RETARGETING</ns1:type>
                            <ns1:targetListId>1100000001</ns1:targetListId>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:SearchTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SEARCH_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>SEARCH_TARGET</ns1:type>
                                <ns1:searchKeywordListId>444444444</ns1:searchKeywordListId>
                                <ns1:searchKeywordListName>TEST SearchKeywordList</ns1:searchKeywordListName>
                                <ns1:searchKeywordListStatus>EXISTS</ns1:searchKeywordListStatus>
                           </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:GenderTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>GENDER_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:gender>ST_MALE</ns1:gender>
                            <ns1:estimateFlg>PAUSED</ns1:estimateFlg>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:gender>ST_UNKNOWN</ns1:gender>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:AgeTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>AGE_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:age>GT_RANGE22_29</ns1:age>
                            <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
                        </ns1:targets>
                        <ns1:targets>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:age>GT_UNKNOWN</ns1:age>
                        </ns1:targets>
                    </ns1:targets>
                    <ns1:targets xsi:type="ns1:PlacementTargetList">
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:type>PLACEMENT_TARGET</ns1:type>
                        <ns1:targets>
                            <ns1:type>PLACEMENT_TARGET</ns1:type>
                            <ns1:urlListId>555555555</ns1:urlListId>
                            <ns1:urlListType>WHITE_LIST</ns1:urlListType>
                        </ns1:targets>
                    </ns1:targets>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTargetReturnValue.md) | Container including operation results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupTargetService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupTargetReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:targetList>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:targets xsi:type="ns1:AdScheduleTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
                                <ns1:startHour>10</ns1:startHour>
                                <ns1:endHour>20</ns1:endHour>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>TUESDAY</ns1:dayOfWeek>
                                <ns1:startHour>10</ns1:startHour>
                                <ns1:endHour>20</ns1:endHour>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
                                <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
                                <ns1:startHour>2</ns1:startHour>
                                <ns1:endHour>22</ns1:endHour>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:GeoTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>GEO_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>GEO_TARGET</ns1:type>
                                <ns1:geo>TC-CI-00000102</ns1:geo>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:InterestCategoryTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>INTEREST_CATEGORY</ns1:type>
                            <ns1:targets>
                                <ns1:type>INTEREST_CATEGORY</ns1:type>
                                <ns1:category>TC-IC-40150150100</ns1:category>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SiteCategoryTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SITE_CATEGORY</ns1:type>
                            <ns1:targets>
                                <ns1:type>SITE_CATEGORY</ns1:type>
                                <ns1:category>TC-SC-10110140100100</ns1:category>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SiteRetargetingTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SITE_RETARGETING</ns1:type>
                            <ns1:targets>
                                <ns1:type>SITE_RETARGETING</ns1:type>
                                <ns1:targetListId>1100000001</ns1:targetListId>
                                <ns1:targetListName>targetListName_1</ns1:targetListName>
                                <ns1:targetListStatus>EXISTS</ns1:targetListStatus>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:SearchTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>SEARCH_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>SEARCH_TARGET</ns1:type>
                                <ns1:searchKeywordListId>444444444</ns1:searchKeywordListId>
                                <ns1:searchKeywordListName>TEST SearchKeywordList</ns1:searchKeywordListName>
                                <ns1:searchKeywordListStatus>EXISTS</ns1:searchKeywordListStatus>
                           </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:GenderTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>GENDER_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>GENDER_TARGET</ns1:type>
                                <ns1:gender>ST_MALE</ns1:gender>
                                <ns1:estimateFlg>PAUSED</ns1:estimateFlg>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>GENDER_TARGET</ns1:type>
                                <ns1:gender>ST_UNKNOWN</ns1:gender>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:AgeTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>AGE_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>AGE_TARGET</ns1:type>
                                <ns1:age>GT_RANGE22_29</ns1:age>
                                <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
                            </ns1:targets>
                            <ns1:targets>
                                <ns1:type>AGE_TARGET</ns1:type>
                                <ns1:age>GT_UNKNOWN</ns1:age>
                            </ns1:targets>
                        </ns1:targets>
                        <ns1:targets xsi:type="ns1:PlacementTargetList">
                            <ns1:accountId>111111111</ns1:accountId>
                            <ns1:campaignId>2222222</ns1:campaignId>
                            <ns1:adGroupId>3333333</ns1:adGroupId>
                            <ns1:type>PLACEMENT_TARGET</ns1:type>
                            <ns1:targets>
                                <ns1:type>PLACEMENT_TARGET</ns1:type>
                                <ns1:urlListId>555555555</ns1:urlListId>
                                <ns1:urlListName>Sample</ns1:urlListName>
                                <ns1:urlListType>WHITE_LIST</ns1:urlListType>
                            </ns1:targets>
                        </ns1:targets>
                    </ns1:targetList>
                </ns1:values>
           </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
