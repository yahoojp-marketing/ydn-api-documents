# AccountAdProductService
AccountAdProductServiceは、広告掲載方式のリストを提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201911/AccountAdProductService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201911/AccountAdProductService?wsdl|
#### Namespace
http://im.yahooapis.jp/V201911/AccountAdProduct
#### サービス概要
AccountAdProductServiceは、広告掲載方式のリストを提供します。
#### 操作
AccountAdProductServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[AccountAdProduct](../data/AccountAdProduct)

## get

### リクエスト
アカウントで利用できる広告掲載方式を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector |  | [AccountAdProductSelector](../data/AccountAdProduct/AccountAdProductSelector.md)|アカウントで利用できる広告掲載方式を取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/AccountAdProduct" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201911/AccountAdProduct">
      <selector>
        <accountIds>1111</accountIds>
        <accountIds>2222</accountIds>
      </selector>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [AccountAdProductPage](../data/AccountAdProduct/AccountAdProductPage.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/AccountAdProduct" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>AccountAdProduct</ns2:service>
      <ns2:requestTime>1574393561126</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/AccountAdProduct">
      <ns2:rval>
        <totalNumEntries>1</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:accountAdProduct>
            <ns2:accountId>1111</ns2:accountId>
            <ns2:adProduct>
              <ns2:adProductType>TARGET_MATCH</ns2:adProductType>
            </ns2:adProduct>
            <ns2:adProduct>
              <ns2:adProductType>VIDEO_AD</ns2:adProductType>
            </ns2:adProduct>
          </ns2:accountAdProduct>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
