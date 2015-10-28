# SearchKeywordListService
SearchKeywordListService retrieves, add, update, and delete the search keyword list. <br>
It can set up to 500 keywords per list. <br>
It can set up to 100 lists per account.<br>
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.1/SearchKeywordListService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.1/SearchKeywordListService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Use this service for operation of search keyword list.
#### Operation
Explains operations provided by SearchKeywordListService.

## get
### Request
Retrieces the search keyeord list.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [SearchKeywordListSelector](../data/SearchKeywordListSelector.md) | Retrives the search keyword list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:searchKeywordListIds>2000000001</ns1:searchKeywordListIds>
            <ns1:searchKeywordListIds>2000000002</ns1:searchKeywordListIds>
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
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
     </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:searchKeywordListIds>2000000001</ns1:searchKeywordListIds>
            <ns1:searchKeywordListIds>2000000002</ns1:searchKeywordListIds>
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
| rval | [SearchKeywordListPage](../data/SearchKeywordListPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>2</ns1:totalNumEntries>
            <ns1:Page.Type>SearchKeywordListPage</ns1:Page.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                     <ns1:searchKeyword>旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>20</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>20</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                     <ns1:searchKeyword>観光</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>5</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>10</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>10</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
             <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                     <ns1:searchKeyword>海外旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>30</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>30</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>             
               </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### Request
Add the search keyword list.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | required | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | Add the search keyword list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?> 
  <SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
              <ns1:accountId>1000000001</ns1:accountId>
              <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
              <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
              <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
              </ns1:searchKeyword>
              <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
              </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
            <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                 </ns1:searchKeyword>
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
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
       <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
     </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>ADD</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
            <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:searchKeywordListActiveFlg>ACTIVE</ns1:searchKeywordListActiveFlg>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                 </ns1:searchKeyword>
           </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>  
 <SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>ADD</ns1:Operation.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                     <ns1:searchKeyword>旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>20</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>20</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                 <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                     <ns1:searchKeyword>観光</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>5</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>10</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>10</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                     <ns1:searchKeyword>海外旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>30</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>30</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                  </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate (SET)
### Request
Updates the search keyword list.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | required | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | Updates the search keyword list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
               <ns1:searchKeywordListName>Sample01 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test update</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample02 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test No2 update</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
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
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
　　　　 <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutate>
         <ns1:operations>
            <ns1:operator>SET</ns1:operator>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
               <ns1:searchKeywordListName>Sample01 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test update</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
               </ns1:searchKeyword>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListName>Sample02 update</ns1:searchKeywordListName>
               <ns1:searchKeywordListDescription>for Test No2 update</ns1:searchKeywordListDescription>
               <ns1:searchKeyword>
                  <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
               </ns1:searchKeyword>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
 <SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>SET</ns1:Operation.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01 Updae</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test Update</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                     <ns1:searchKeyword>旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>20</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>20</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                 <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                     <ns1:searchKeyword>観光</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>5</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>10</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>10</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                     <ns1:searchKeyword>海外旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>30</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>30</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02 Update</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2 Update</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                     <ns1:searchKeyword>旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>20</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>20</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                  </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### Request
Deletes the search keyword list.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| operations | required | [SearchKeywordListOperation](../data/SearchKeywordListOperation.md) | Deletes the search keyword list. | 

##### Request Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
 <SOAP-ENV:Envelope 
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
           </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
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
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:RequestHeader>
         <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
         <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>100000001</ns1:accountId>
         <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
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
               <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
           </ns1:operand>
            <ns1:operand>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
            </ns1:operand>
         </ns1:operations>
      </ns1:mutate>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response

| Parameter | Data Type | Description | 
|---|---|---|
| rval | [SearchKeywordListReturnValue](../data/SearchKeywordListReturnValue.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
 <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>SearchKeywordListService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:mutateResponse>
         <ns1:rval>
            <ns1:ListReturnValue.Type>SearchKeywordListReturnValue</ns1:ListReturnValue.Type>
            <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000001</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample01</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>PAUSED</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000001</ns1:searchKeywordId>
                     <ns1:searchKeyword>旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>20</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>20</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                 <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000002</ns1:searchKeywordId>
                     <ns1:searchKeyword>観光</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>5</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>10</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>10</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
               </ns1:searchKeywordList>
            </ns1:values>
            <ns1:values>
              <ns1:operationSucceeded>true</ns1:operationSucceeded>
              <ns1:searchKeywordList>
                  <ns1:accountId>1000000001</ns1:accountId>
                  <ns1:searchKeywordListId>2000000002</ns1:searchKeywordListId>
                  <ns1:searchKeywordListName>Sample02</ns1:searchKeywordListName>
                  <ns1:searchKeywordListDescription>for Test No2</ns1:searchKeywordListDescription>
                  <ns1:deliveryStatus>ACTIVE</ns1:deliveryStatus>
                  <ns1:searchKeyword>
                     <ns1:searchKeywordId>3000000003</ns1:searchKeywordId>
                     <ns1:searchKeyword>海外旅行</ns1:searchKeyword>
                     <ns1:desktopSearchVolume>30</ns1:desktopSearchVolume>
                     <ns1:smartPhoneSearchVolume>30</ns1:smartPhoneSearchVolume>
                     <ns1:tabletSearchVolume>30</ns1:tabletSearchVolume>
                  </ns1:searchKeyword>
                  </ns1:searchKeywordList>
            </ns1:values>
         </ns1:rval>
     </ns1:mutateResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
