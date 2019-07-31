# SearchKeywordIdeaService
SearchKeywordIdeaServiceは、サーチターゲティング対象キーワードを取得します。<br>1リクエストで指定できるキーワードは100件までです。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201907/SearchKeywordIdeaService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201907/SearchKeywordIdeaService?wsdl|
#### Namespace
http://im.yahooapis.jp/V201907/SearchKeywordIdea
#### サービス概要
サーチターゲティング対象キーワードを取得します。
#### 操作
SearchKeywordIdeaServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[SearchKeywordIdea](../data/SearchKeywordIdea)

## get

### リクエスト
サーチターゲティング対象キーワードを取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [SearchKeywordIdeaSelector](../data/SearchKeywordIdea/SearchKeywordIdeaSelector.md) | サーチターゲティング対象キーワードを取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201907/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201907/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201907">
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

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [SearchKeywordIdeaPage](../data/SearchKeywordIdea/SearchKeywordIdeaPage.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201907/SearchKeywordIdea" xmlns:ns2="http://im.yahooapis.jp/V201907">
      <ns2:service>SearchKeywordIdea</ns2:service>
      <ns2:requestTime>1551686140249</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201907" xmlns:ns2="http://im.yahooapis.jp/V201907/SearchKeywordIdea">
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
