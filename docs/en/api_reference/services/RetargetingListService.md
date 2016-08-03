# RetargetingListService
RetargetingListService retrives, add, update, and delete the target list for site retargeting.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/RetargetingListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/RetargetingListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Use this service to retrieve , add, update, and delete the target list for site retargeting.<br>
<br>
[About "Target List"]<br>
Target List can distribute and group the users' browsing history to specified conditions.<br>
This can narrow down and deliver more appropriate ads to each user's interest.<br>
It has three types of lists: <br>
・Default list: Automatically made from the creation of site retargeting tag<br>
・Target list: Made from specified conditions (URL or label)<br>
・Combination list: Made by both Default list and Target list<br>
<br>
[Notes]<br>
Can create "one tag" per account for site retargeting tag<br>
Can set up to 300 target lists per account<br>
Can set up to 10 conditions per target list<br>
Can set up to 10 combination of target lists per target list<br>

#### Operation
Explains the operatons provided by RetargetingListService.

## get
### Request
Retrieve target list information for site retargeting.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [RetargetingListSelector](../data/RetargetingListSelector.md) | Retrieve target list information for site retargeting. | 

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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListIds>9000000001</ns1:targetListIds>
                <ns1:targetListIds>9000000002</ns1:targetListIds>
                <ns1:targetListIds>9000000003</ns1:targetListIds>
                <ns1:targetListTypes>RULE</ns1:targetListTypes>
                <ns1:targetListTypes>COMBINATION</ns1:targetListTypes>
                <ns1:targetListTypes>DEFAULT_LIST</ns1:targetListTypes>
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
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListIds>9000000001</ns1:targetListIds>
                <ns1:targetListIds>9000000002</ns1:targetListIds>
                <ns1:targetListIds>9000000003</ns1:targetListIds>
                <ns1:targetListTypes>RULE</ns1:targetListTypes>
                <ns1:targetListTypes>COMBINATION</ns1:targetListTypes>
                <ns1:targetListTypes>DEFAULT_LIST</ns1:targetListTypes>
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
| rval | [RetargetingListPage](../data/RetargetingListPage.md) | Container holding the operation result. | 

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
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>RetargetingListPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000003</ns1:targetListId>
                        <ns1:targetListName>Rule_Target</ns1:targetListName>
                        <ns1:description>example for Rule</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:reach>1000</ns1:reach>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>TRUE</ns1:isOpen>
                            <ns1:reachPeriod>100</ns1:reachPeriod>
                            <ns1:rules>
                                <ns1:ruleConditions>
                                    <ns1:type>URL</ns1:type>
                                    <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                    <ns1:value>aaaaa.com</ns1:value>
                                </ns1:ruleConditions>
                                <ns1:ruleConditions>
                                    <ns1:type>LABEL</ns1:type>
                                    <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                    <ns1:value>label1</ns1:value>
                                </ns1:ruleConditions>
                            </ns1:rules>
                            <ns1:rules>
                                <ns1:ruleConditions>
                                    <ns1:type>URL</ns1:type>
                                    <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                    <ns1:value>bbbbbbb.com</ns1:value>
                                </ns1:ruleConditions>
                                <ns1:ruleConditions>
                                    <ns1:type>LABEL</ns1:type>
                                    <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                    <ns1:value>label2</ns1:value>
                                </ns1:ruleConditions>
                            </ns1:rules>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000002</ns1:targetListId>
                        <ns1:targetListName>Combination_Target</ns1:targetListName>
                        <ns1:description>example for Combination</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:reach>500</ns1:reach>
                        <ns1:targetList xsi:type="ns1:CombinationTargetList">
                            <ns1:targetListType>COMBINATION</ns1:targetListType>
                            <ns1:combinations>
                                <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000001</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_1</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000003</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_3</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                            <ns1:combinations>
                                <ns1:logicalOperator>AND</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000004</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_4</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000005</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_5</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000001</ns1:targetListId>
                        <ns1:targetListName>Default_List</ns1:targetListName>
                        <ns1:description>example for Default_List</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:reach>1000</ns1:reach>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>DEFAULT_LIST</ns1:targetListType>
                            <ns1:retargetingTagId>05HG3F81S9</ns1:retargetingTagId>
                            <ns1:isPreset>FALSE</ns1:isPreset>
                            <ns1:isOpen>TRUE</ns1:isOpen>
                            <ns1:reachPeriod>540</ns1:reachPeriod>
                        </ns1:targetList>                        
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Create the target list for site retargeting.

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingListOperation.md) | Creates the target list for site retargeting. | 

##### Request Sample (For rule setting) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:targetListType>RULE</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListName>Rule_Target</ns1:targetListName>
                    <ns1:description>example for Rule</ns1:description>
                    <ns1:targetList xsi:type="ns1:RuleTargetList">
                        <ns1:targetListType>RULE</ns1:targetListType>
                        <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                        <ns1:isPreset>TRUE</ns1:isPreset>
                        <ns1:isOpen>TRUE</ns1:isOpen>
                        <ns1:reachPeriod>540</ns1:reachPeriod>
                        <ns1:rules>
                            <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>aaaaa.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label1</ns1:value>
                            </ns1:ruleConditions>
                        </ns1:rules>
                        <ns1:rules>
                            <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>bbbbbbb.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label2</ns1:value>
                            </ns1:ruleConditions>
                        </ns1:rules>
                    </ns1:targetList>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListName>All Reach</ns1:targetListName>
                    <ns1:description>example for All Reach</ns1:description>
                    <ns1:targetList xsi:type="ns1:RuleTargetList">
                        <ns1:targetListType>RULE</ns1:targetListType>
                        <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                        <ns1:isPreset>TRUE</ns1:isPreset>
                        <ns1:isOpen>TRUE</ns1:isOpen>
                        <ns1:reachPeriod>540</ns1:reachPeriod>
                        <ns1:rules></ns1:rules>
                    </ns1:targetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For combination setting) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
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
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListType>COMBINATION</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListName>TargetListName_2</ns1:targetListName>
                    <ns1:description>TargetListDescription_2</ns1:description>
                    <ns1:targetList xsi:type="ns1:CombinationTargetList">
                        <ns1:targetListType>COMBINATION</ns1:targetListType>
                        <ns1:combinations>
                            <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000001</ns1:targetListId>
                            </ns1:targetLists>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000003</ns1:targetListId>
                            </ns1:targetLists>
                        </ns1:combinations>
                        <ns1:combinations>
                            <ns1:logicalOperator>AND</ns1:logicalOperator>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000004</ns1:targetListId>
                            </ns1:targetLists>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000005</ns1:targetListId>
                            </ns1:targetLists>
                        </ns1:combinations>
                    </ns1:targetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For similar user) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:targetListType>SIMILARITY</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListName>Similarity_Target</ns1:targetListName>
                    <ns1:description>example for Similarity</ns1:description>
                    <ns1:targetList xsi:type="ns1:SimilarityTargetList">
                        <ns1:targetListType>SIMILARITY</ns1:targetListType>
                        <ns1:targetListId>9000000000</ns1:targetListId>
                    </ns1:targetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Field | Data Type | Description | 
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingListReturnValue.md) | Container holding the operation result | 

##### Response Sample (For rule setting)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000003</ns1:targetListId>
                        <ns1:targetListName>Rull_Target</ns1:targetListName>
                        <ns1:description>example for Rull</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>TRUE</ns1:isOpen>
                            <ns1:reachPeriod>540</ns1:reachPeriod>
                            <ns1:rules>
                             <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>aaaaa.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label1</ns1:value>
                            </ns1:ruleConditions>
                         </ns1:rules>
                         <ns1:rules>
                             <ns1:ruleConditions>
                                 <ns1:type>URL</ns1:type>
                                 <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                 <ns1:value>bbbbbbb.com</ns1:value>
                              </ns1:ruleConditions>
                              <ns1:ruleConditions>
                                 <ns1:type>LABEL</ns1:type>
                                 <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                 <ns1:value>label2</ns1:value>
                             </ns1:ruleConditions>
                         </ns1:rules>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000004</ns1:targetListId>
                        <ns1:targetListName>All_Reach</ns1:targetListName>
                        <ns1:description>example for All Reach</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>TRUE</ns1:isOpen>
                            <ns1:reachPeriod>540</ns1:reachPeriod>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For combination setting)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000002</ns1:targetListId>
                        <ns1:targetListName>TargetListName_2</ns1:targetListName>
                        <ns1:description>TargetListDescription_2</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:CombinationTargetList">
                            <ns1:targetListType>COMBINATION</ns1:targetListType>
                            <ns1:combinations>
                                <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000001</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_1</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000003</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_3</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                            <ns1:combinations>
                                <ns1:logicalOperator>AND</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000004</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_4</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000005</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_5</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For similar user) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000004</ns1:targetListId>
                        <ns1:targetListName>Similarity_Target</ns1:targetListName>
                        <ns1:description>example for Similarity</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:SimilarityTargetList">
                            <ns1:targetListType>SIMILARITY</ns1:targetListType>
                            <ns1:targetListId>9000000000</ns1:targetListId>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### Request

| Parameter | Requirement | Value | Description | 
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingListOperation.md) | Updates target list for site retargeting. | 

##### Request Sample (For rule setting)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListType>RULE</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000001</ns1:targetListId>
                    <ns1:targetListName>Rull_Target</ns1:targetListName>
                    <ns1:description>example for Rull</ns1:description>
                    <ns1:targetList xsi:type="ns1:RuleTargetList">
                        <ns1:targetListType>RULE</ns1:targetListType>
                        <ns1:isOpen>FALSE</ns1:isOpen>
                        <ns1:reachPeriod>530</ns1:reachPeriod>
                        <ns1:rules>
                            <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>bbbbb.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label2</ns1:value>
                            </ns1:ruleConditions>
                        </ns1:rules>
                        <ns1:rules>
                            <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>ccccc.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label3</ns1:value>
                            </ns1:ruleConditions>
                        </ns1:rules>
                    </ns1:targetList>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000002</ns1:targetListId>
                    <ns1:targetListName>All Reach</ns1:targetListName>
                    <ns1:description>example for All Reach</ns1:description>
                    <ns1:targetList xsi:type="ns1:RuleTargetList">
                        <ns1:targetListType>RULE</ns1:targetListType>
                        <ns1:isOpen>FALSE</ns1:isOpen>
                        <ns1:reachPeriod>530</ns1:reachPeriod>
                        <ns1:rules></ns1:rules>
                    </ns1:targetList>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000003</ns1:targetListId>
                    <ns1:targetListName>Rull_Target_No_Change</ns1:targetListName>
                    <ns1:description>example for Rull Target No Change</ns1:description>
                    <ns1:targetList xsi:type="ns1:RuleTargetList">
                        <ns1:targetListType>RULE</ns1:targetListType>
                        <ns1:isOpen>FALSE</ns1:isOpen>
                        <ns1:reachPeriod>530</ns1:reachPeriod>
                    </ns1:targetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For combination setting) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
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
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListType>COMBINATION</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000002</ns1:targetListId>
                    <ns1:targetListName>TargetListName_2</ns1:targetListName>
                    <ns1:description>TargetListDescription_2</ns1:description>
                    <ns1:targetList xsi:type="ns1:CombinationTargetList">
                        <ns1:targetListType>COMBINATION</ns1:targetListType>
                        <ns1:combinations>
                            <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000001</ns1:targetListId>
                            </ns1:targetLists>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000003</ns1:targetListId>
                            </ns1:targetLists>
                        </ns1:combinations>
                        <ns1:combinations>
                            <ns1:logicalOperator>AND</ns1:logicalOperator>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000004</ns1:targetListId>
                            </ns1:targetLists>
                            <ns1:targetLists>
                                <ns1:targetListId>9000000005</ns1:targetListId>
                            </ns1:targetLists>
                        </ns1:combinations>
                    </ns1:targetList>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For similar user) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:targetListType>SIMILARITY</ns1:targetListType>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000001</ns1:targetListId>
                    <ns1:targetListName>Similarity_Target</ns1:targetListName>
                    <ns1:description>example for Similarity</ns1:description>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Field | Data Type | Description | 
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingListReturnValue.md) | Container holding the operation result. | 

##### Response Sample (For rule setting)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000001</ns1:targetListId>
                        <ns1:targetListName>Rull_Target</ns1:targetListName>
                        <ns1:description>example for Rull</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>FALSE</ns1:isOpen>
                            <ns1:reachPeriod>530</ns1:reachPeriod>
                            <ns1:rules>
                             <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                 <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                 <ns1:value>bbbbb.com</ns1:value>
                             </ns1:ruleConditions>
                             <ns1:ruleConditions>
                                 <ns1:type>LABEL</ns1:type>
                                 <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                 <ns1:value>label2</ns1:value>
                             </ns1:ruleConditions>
                         </ns1:rules>
                         <ns1:rules>
                             <ns1:ruleConditions>
                                 <ns1:type>URL</ns1:type>
                                 <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                 <ns1:value>ccccc.com</ns1:value>
                              </ns1:ruleConditions>
                              <ns1:ruleConditions>
                                 <ns1:type>LABEL</ns1:type>
                                 <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                 <ns1:value>label3</ns1:value>
                             </ns1:ruleConditions>
                         </ns1:rules>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000002</ns1:targetListId>
                        <ns1:targetListName>All Reach</ns1:targetListName>
                        <ns1:description>example for All Reach</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>FALSE</ns1:isOpen>
                            <ns1:reachPeriod>530</ns1:reachPeriod>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000003</ns1:targetListId>
                        <ns1:targetListName>Rull_Target_No_Change</ns1:targetListName>
                        <ns1:description>example for Rull Target No Change</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>FALSE</ns1:isOpen>
                            <ns1:reachPeriod>530</ns1:reachPeriod>
                            <ns1:rules>
                                <ns1:ruleConditions>
                                    <ns1:type>URL</ns1:type>
                                    <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                    <ns1:value>ddddd.com</ns1:value>
                                </ns1:ruleConditions>
                                <ns1:ruleConditions>
                                    <ns1:type>LABEL</ns1:type>
                                    <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                    <ns1:value>label4</ns1:value>
                                </ns1:ruleConditions>
                            </ns1:rules>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For combination setting)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000002</ns1:targetListId>
                        <ns1:targetListName>TargetListName_2</ns1:targetListName>
                        <ns1:description>TargetListDescription_2</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:CombinationTargetList">
                            <ns1:targetListType>COMBINATION</ns1:targetListType>
                            <ns1:combinations>
                                <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000001</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_1</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000003</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_3</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                            <ns1:combinations>
                                <ns1:logicalOperator>AND</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000004</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_4</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000005</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_5</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Response Sample (For similar user) 
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000001</ns1:targetListId>
                        <ns1:targetListName>Similarity_Target</ns1:targetListName>
                        <ns1:description>example for Similarity</ns1:description>
                        <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:SimilarityTargetList">
                            <ns1:targetListType>SIMILARITY</ns1:targetListType>
                            <ns1:targetListId>9000000000</ns1:targetListId>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | ○ | [RetargetingListOperation](../data/RetargetingListOperation.md) | Deletes target list for site retargeting. | 

##### <Request Sample>
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000001</ns1:targetListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000002</ns1:targetListId>
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
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000001</ns1:targetListId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:targetListId>9000000002</ns1:targetListId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [RetargetingListReturnValue](../data/RetargetingListReturnValue.md) | Container holding the operation result. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>RetargetingListService</ns1:service>
            <ns1:remainingQuota>4997</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>RetargetingListReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000001</ns1:targetListId>
                        <ns1:targetListName>Rule_Target</ns1:targetListName>
                        <ns1:description>example for Rule</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:RuleTargetList">
                            <ns1:targetListType>RULE</ns1:targetListType>
                            <ns1:retargetingTagId>TAG0000001</ns1:retargetingTagId>
                            <ns1:isPreset>TRUE</ns1:isPreset>
                            <ns1:isOpen>TRUE</ns1:isOpen>
                            <ns1:reachPeriod>540</ns1:reachPeriod>
                            <ns1:rules>
                                <ns1:ruleConditions>
                                <ns1:type>URL</ns1:type>
                                <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                <ns1:value>aaaaa.com</ns1:value>
                            </ns1:ruleConditions>
                            <ns1:ruleConditions>
                                <ns1:type>LABEL</ns1:type>
                                <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                <ns1:value>label1</ns1:value>
                            </ns1:ruleConditions>
                            </ns1:rules>
                            <ns1:rules>
                                <ns1:ruleConditions>
                                    <ns1:type>URL</ns1:type>
                                    <ns1:compareOperator>EQUAL</ns1:compareOperator>
                                    <ns1:value>bbbbbbb.com</ns1:value>
                                </ns1:ruleConditions>
                                <ns1:ruleConditions>
                                    <ns1:type>LABEL</ns1:type>
                                    <ns1:compareOperator>INCLUDED</ns1:compareOperator>
                                    <ns1:value>label2</ns1:value>
                                </ns1:ruleConditions>
                            </ns1:rules>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:retargetingList>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:targetListId>9000000002</ns1:targetListId>
                        <ns1:targetListName>Combination_Target</ns1:targetListName>
                        <ns1:description>example for Combination</ns1:description>
                        <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                        <ns1:targetList xsi:type="ns1:CombinationTargetList">
                            <ns1:targetListType>COMBINATION</ns1:targetListType>
                            <ns1:combinations>
                                <ns1:logicalOperator>NOTIN</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000001</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_1</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000003</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_3</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                            <ns1:combinations>
                                <ns1:logicalOperator>AND</ns1:logicalOperator>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000004</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_4</ns1:targetListName>
                                </ns1:targetLists>
                                <ns1:targetLists>
                                    <ns1:targetListId>9000000005</ns1:targetListId>
                                    <ns1:targetListName>TargetListName_5</ns1:targetListName>
                                </ns1:targetLists>
                            </ns1:combinations>
                        </ns1:targetList>
                    </ns1:retargetingList>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
