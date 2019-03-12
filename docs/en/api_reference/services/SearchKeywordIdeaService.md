# SearchKeywordIdeaService
SearchKeywordIdeaService retrieves the keyword for search targeting. <br>
It can designate up to 100 keywords per request.

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/SearchKeywordIdeaService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/SearchKeywordIdeaService?wsdl |
#### Namespace
http://im.yahooapis.jp/V201903/SearchKeywordIdea
#### Service Overview
Retrieves the keyword for search targeting.
#### Operation
Explains oprations provided by SearchKeywordIdeaService

+ [get](#get)

#### Object
[SearchKeywordIdea](../data/SearchKeywordIdea)

## get

### Request
Retrieves the keyword for seach targeting.

| Parameter | Requirement | Data Type | Description |
|---|---|---|---|
| selector | required | [SearchKeywordIdeaSelector](../data/SearchKeywordIdea/SearchKeywordIdeaSelector.md) | Retrieves the keyword for search targeting. |

##### Request Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <selector>
        <keywordIds>1111</keywordIds>
        <keywordIds>2222</keywordIds>
        <searchKeywordRecency>WITHIN_30DAYS</searchKeywordRecency>
        <searchKeywordFrequency>TWICE_OR_MORE</searchKeywordFrequency>
        <sortField>DESKTOP_SEARCH_VOLUME</sortField>
        <sortType>DESC</sortType>
        <matchType>EXACT</matchType>
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
| Parameter | Data Type | Description |
|---|---|---|
| rval | [SearchKeywordIdeaPage](../data/SearchKeywordIdea/SearchKeywordIdeaPage.md) | A container that stores results. |

##### Response Sample
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>SearchKeywordIdea</ns2:service>
      <ns2:requestTime>1551686140263</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/SearchKeywordIdea">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:searchKeywordIdea>
            <ns2:searchKeywordId>1111</ns2:searchKeywordId>
            <ns2:searchKeyword>TEST</ns2:searchKeyword>
            <ns2:desktopSearchVolume>200</ns2:desktopSearchVolume>
            <ns2:smartPhoneSearchVolume>3000</ns2:smartPhoneSearchVolume>
            <ns2:tabletSearchVolume>0</ns2:tabletSearchVolume>
            <ns2:releaseDate>20190101</ns2:releaseDate>
          </ns2:searchKeywordIdea>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
