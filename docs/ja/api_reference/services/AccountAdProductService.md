# AccountAdProductService
AccountAdProductServiceは、広告掲載方式のリストを提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AccountAdProductService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AccountAdProductService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
AccountAdProductServiceは、広告掲載方式のリストを提供します。
#### 操作
AccountAdProductServiceで提供される操作を説明します。
## get
### リクエスト
アカウントで利用できる広告掲載方式を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector |  | [AccountAdProductSelector](../data/AccountAdProductSelector.md)|アカウントで利用できる広告掲載方式を取得します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
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
        <ns1:accountIds>12345</ns1:accountIds>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
##### ＜リクエストサンプル＞（代行認証）
```xml	
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
      <ns1:accountId>12345</ns1:accountId>
      <ns1:onBehalfOfAccountId>33333-3333-33333-3333</ns1:onBehalfOfAccountId>
      <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>    
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountIds>12345</ns1:accountIds>
        <ns1:accountIds>23456</ns1:accountIds>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AccountAdProductPage](../data/AccountAdProductPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AccountAdProductService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>AccountAdProdcutPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountAdProduct>
            <ns1:accountId>100001</ns1:accountId>
            <ns1:adProduct>
              <ns1:adProductType>INTEREST_MATCH</ns1:adProductType>
              <ns1:status>OPEN</ns1:status>
            </ns1:adProduct>
            <ns1:adProduct>
              <ns1:adProductType>TARGET_MATCH</ns1:adProductType>
              <ns1:status>OPEN</ns1:status>
            </ns1:adProduct>
            <ns1:adProduct>
              <ns1:adProductType>NO_MATCH</ns1:adProductType>
              <ns1:status>SHUT</ns1:status>
            </ns1:adProduct>
          </ns1:accountAdProduct>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:accountAdProduct>
            <ns1:accountId>100002</ns1:accountId>
            <ns1:adProduct>
              <ns1:adProductType>MOBILE_TARGETING</ns1:adProductType>
              <ns1:status>OPEN</ns1:status>
            </ns1:adProduct>
          </ns1:accountAdProduct>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
