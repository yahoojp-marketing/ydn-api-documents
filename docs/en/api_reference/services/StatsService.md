# StatsService
StatsService retrieves the stats data of each campaign, ad group, ad and media.
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.3/StatsService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.3/StatsService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
StatsService retrieves the stats data of each campaign, ad group, ad and media.
#### Operation
Describes operations provided by StatsService.
## get
### Request
Retrieves the stats information of each campaign, ad group, ad and media.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | ○ | [StatsSelector](../data/StatsSelector.md) |Acquires stats information| 

##### Request Sample (Campaign Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:campaignIds>2222222</ns1:campaignIds>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:statsType>CAMPAIGN</ns1:statsType>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (Ad group Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:campaignIds>2222222</ns1:campaignIds>
            <ns1:adGroupIds>3333333</ns1:adGroupIds>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:statsType>ADGROUP</ns1:statsType>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


##### Request Sample (Ad Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
            <ns1:campaignIds>2222222</ns1:campaignIds>
            <ns1:adGroupIds>3333333</ns1:adGroupIds>
            <ns1:adIds>4444444</ns1:adIds>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:statsType>AD</ns1:statsType>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


##### Request Sample (Media Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
   <soapenv:Header>
      <ns1:RequestHeader>
         <ns1:license>1111-1111-1111-1111</ns1:license>
         <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
         <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
         <ns1:accountId>1111-1111-1111-1111</ns1:accountId>
         <ns1:onBehalfOfAccountId>2222-2222-2222-2222</ns1:onBehalfOfAccountId>
         <ns1:onBehalfOfPassword>password</ns1:onBehalfOfPassword>
      </ns1:RequestHeader>
   </soapenv:Header>
   <soapenv:Body>
      <ns1:get>
         <ns1:selector>
            <ns1:accountId>111111</ns1:accountId>
            <ns1:campaignIds>222222</ns1:campaignIds>
            <ns1:adGroupIds>333333</ns1:adGroupIds>
            <ns1:adIds>444444</ns1:adIds>
            <ns1:mediaIds>444444</ns1:mediaIds>
            <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
            <ns1:statsType>MEDIA</ns1:statsType>
            <ns1:paging>
               <ns1:startIndex>1</ns1:startIndex>
               <ns1:numberResults>20</ns1:numberResults>
            </ns1:paging>
         </ns1:selector>
      </ns1:get>
   </soapenv:Body>
</soapenv:Envelope>
```


### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [StatsPage](../data/StatsPage.md) | Container storing the operation result | 

##### Response Sample (Campaign Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5”>
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>StatsService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>StatsPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:campaignId>2222222</ns1:campaignId>
               <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
               <ns1:statsType>CAMPAIGN</ns1:statsType>
               <ns1:stats>
                  <ns1:imps>10000</ns1:imps>
                  <ns1:clickRate>95</ns1:clickRate>
                  <ns1:clickRateComparisionResult>UP</ns1:clickRateComparisionResult>
                  <ns1:totalClickCost>3000</ns1:totalClickCost>
                  <ns1:clickCnt>5000</ns1:clickCnt>
                  <ns1:avgClickCost>3000</ns1:avgClickCost>
                  <ns1:avgClickCostComparisionResult>UP</ns1:avgClickCostComparisionResult>
                  <ns1:convCnt>30</ns1:convCnt>
                  <ns1:convRate>12</ns1:convRate>
                  <ns1:convRateComparisionResult>UP</ns1:convRateComparisionResult>
                  <ns1:cpa>3</ns1:cpa>
                  <ns1:cpaComparisionResult>UP</ns1:cpaComparisionResult>
                  <ns1:avgDeliverRank>3</ns1:avgDeliverRank>
                  <ns1:totalVimps>300</ns1:totalVimps>
                  <ns1:vImps>200</ns1:vImps>
                  <ns1:inViewClickCnt>30</ns1:inViewClickCnt>
                  <ns1:inViewRate>30</ns1:inViewRate>
                  <ns1:inViewClickRate>40</ns1:inViewClickRate>
               </ns1:stats>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


##### Response Sample (Ad group Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5”>
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>StatsService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>StatsPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:campaignId>2222222</ns1:campaignId>
               <ns1:adGroupId>3333333</ns1:adGroupId>
               <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
               <ns1:statsType>ADGROUP</ns1:statsType>
               <ns1:stats>
                  <ns1:imps>10000</ns1:imps>
                  <ns1:clickRate>95</ns1:clickRate>
                  <ns1:clickRateComparisionResult>UP</ns1:clickRateComparisionResult>
                  <ns1:totalClickCost>3000</ns1:totalClickCost>
                  <ns1:clickCnt>5000</ns1:clickCnt>
                  <ns1:avgClickCost>3000</ns1:avgClickCost>
                  <ns1:avgClickCostComparisionResult>UP</ns1:avgClickCostComparisionResult>
                  <ns1:convCnt>30</ns1:convCnt>
                  <ns1:convRate>12</ns1:convRate>
                  <ns1:convRateComparisionResult>UP</ns1:convRateComparisionResult>
                  <ns1:cpa>3</ns1:cpa>
                  <ns1:cpaComparisionResult>UP</ns1:cpaComparisionResult>
                  <ns1:avgDeliverRank>3</ns1:avgDeliverRank>
                  <ns1:totalVimps>300</ns1:totalVimps>
                  <ns1:vImps>200</ns1:vImps>
                  <ns1:inViewClickCnt>30</ns1:inViewClickCnt>
                  <ns1:inViewRate>30</ns1:inViewRate>
                  <ns1:inViewClickRate>40</ns1:inViewClickRate>
               </ns1:stats>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


##### Response Sample (Ad Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5”>
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>StatsService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>StatsPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:campaignId>2222222</ns1:campaignId>
               <ns1:adGroupId>3333333</ns1:adGroupId>
               <ns1:adId>4444444</ns1:adId>
               <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
               <ns1:statsType>AD</ns1:statsType>
               <ns1:stats>
                  <ns1:imps>10000</ns1:imps>
                  <ns1:clickRate>95</ns1:clickRate>
                  <ns1:clickRateComparisionResult>UP</ns1:clickRateComparisionResult>
                  <ns1:totalClickCost>3000</ns1:totalClickCost>
                  <ns1:clickCnt>5000</ns1:clickCnt>
                  <ns1:avgClickCost>3000</ns1:avgClickCost>
                  <ns1:avgClickCostComparisionResult>UP</ns1:avgClickCostComparisionResult>
                  <ns1:convCnt>30</ns1:convCnt>
                  <ns1:convRate>12</ns1:convRate>
                  <ns1:convRateComparisionResult>UP</ns1:convRateComparisionResult>
                  <ns1:cpa>3</ns1:cpa>
                  <ns1:cpaComparisionResult>UP</ns1:cpaComparisionResult>
                  <ns1:avgDeliverRank>3</ns1:avgDeliverRank>
                  <ns1:totalVimps>300</ns1:totalVimps>
                  <ns1:vImps>200</ns1:vImps>
                  <ns1:inViewClickCnt>30</ns1:inViewClickCnt>
                  <ns1:inViewRate>30</ns1:inViewRate>
                  <ns1:inViewClickRate>40</ns1:inViewClickRate>
               </ns1:stats>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


##### Response Sample (Media Stats Information)
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5”>
   <SOAP-ENV:Header>
      <ns1:ResponseHeader>
         <ns1:service>StatsService</ns1:service>
         <ns1:remainingQuota>100</ns1:remainingQuota>
         <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
         <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
      </ns1:ResponseHeader>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getResponse>
         <ns1:rval>
            <ns1:totalNumEntries>1</ns1:totalNumEntries>
            <ns1:Page.Type>StatsPage</ns1:Page.Type>
            <ns1:values>
               <ns1:operationSucceeded>true</ns1:operationSucceeded>
               <ns1:accountId>1000000001</ns1:accountId>
               <ns1:mediaId>555555</ns1:mediaId>
               <ns1:statsPeriod>REALTIME_TODAY</ns1:statsPeriod>
               <ns1:statsType>MEDIA</ns1:statsType>
               <ns1:stats>
                  <ns1:imps>10000</ns1:imps>
                  <ns1:clickRate>95</ns1:clickRate>
                  <ns1:clickRateComparisionResult>UP</ns1:clickRateComparisionResult>
                  <ns1:totalClickCost>3000</ns1:totalClickCost>
                  <ns1:clickCnt>5000</ns1:clickCnt>
                  <ns1:avgClickCost>3000</ns1:avgClickCost>
                  <ns1:avgClickCostComparisionResult>UP</ns1:avgClickCostComparisionResult>
                  <ns1:convCnt>30</ns1:convCnt>
                  <ns1:convRate>12</ns1:convRate>
                  <ns1:convRateComparisionResult>UP</ns1:convRateComparisionResult>
                  <ns1:cpa>3</ns1:cpa>
                  <ns1:cpaComparisionResult>UP</ns1:cpaComparisionResult>
                  <ns1:avgDeliverRank>3</ns1:avgDeliverRank>
                  <ns1:totalVimps>300</ns1:totalVimps>
                  <ns1:vImps>200</ns1:vImps>
                  <ns1:inViewClickCnt>30</ns1:inViewClickCnt>
                  <ns1:inViewRate>30</ns1:inViewRate>
                  <ns1:inViewClickRate>40</ns1:inViewClickRate>
               </ns1:stats>
            </ns1:values>
         </ns1:rval>
      </ns1:getResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
