# SearchKeywordIdeaService
SearchKeywordIdeaService retrieves the keyword for search targeting. <br>
It can designate up to 100 keywords per request.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/SearchKeywordIdeaService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/SearchKeywordIdeaService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### Service Overview
Retrieves the keyword for search targeting.
#### Operation
Explains oprations provided by SearchKeywordIdeaService

## get
### Request
Retrieves the keyword for seach targeting.

| Parameter | Requirement | Data Type | Description | 
|---|---|---|---|
| selector | required | [SearchKeywordIdeaSelector](../data/SearchKeywordIdeaSelector.md) | Retrieves the keyword for search targeting. | 

##### Request Sample (For Keyword search)
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
                <ns1:keywords>Yahoo</ns1:keywords>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### Request Sample (For Keyword ID search)
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
                <ns1:keywordIds>1000000001</ns1:keywordIds>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Response
| Parameter | Data Type | Description | 
|---|---|---|
| rval | [SearchKeywordIdeaPage](../data/SearchKeywordIdeaPage.md) | A container that stores results. | 

##### Response Sample
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>SearchKeywordIdeaService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>SearchKeywordIdeaPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:searchKeywordIdea>
                        <ns1:searchKeywordId>1000000001</ns1:searchKeywordId>
                        <ns1:searchKeyword>Yahoo! Japan</ns1:searchKeyword>
                        <ns1:desktopSearchVolume>100</ns1:desktopSearchVolume>
                        <ns1:smartPhoneSearchVolume>200</ns1:smartPhoneSearchVolume>
                        <ns1:tabletSearchVolume>300</ns1:tabletSearchVolume>
                    </ns1:searchKeywordIdea> 
                </ns1:values>
                <ns1:values>
                     <ns1:operationSucceeded>true</ns1:operationSucceeded>
                     <ns1:searchKeywordIdea>
                         <ns1:searchKeywordId>1000000002</ns1:searchKeywordId>
                         <ns1:searchKeyword>Y!J</ns1:searchKeyword>
                         <ns1:desktopSearchVolume>300</ns1:desktopSearchVolume>
                         <ns1:smartPhoneSearchVolume>200</ns1:smartPhoneSearchVolume>
                         <ns1:tabletSearchVolume>300</ns1:tabletSearchVolume>
                    </ns1:searchKeywordIdea> 
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
