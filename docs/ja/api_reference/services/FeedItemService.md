# FeedItemService

FeedItemServiceは商品情報の操作を提供します。

#### WSDL

| environment |                                      url                                      |
| ----------- | ----------------------------------------------------------------------------- |
| production  | https://location.im.yahooapis.jp/services/V201911/FeedItemService?wsdl |
| sandbox     | https://sandbox.im.yahooapis.jp/services/V201911/FeedItemService?wsdl  |

#### Namespace

http://im.yahooapis.jp/V201911/FeedItem

#### Service Overview

商品情報の更新を行います。

#### Operation

FeedItemServiceで提供される操作を説明します。

+ [mutate(SET)](#mutateset)

## mutate(SET)

### リクエスト

商品情報を変更します。

| パラメータ | 必須 | データ型 |
| ---------- | ---- | -------- |
| operations | Yes | [FeedItemOperation](../data/FeedItem/FeedItemOperation.md) |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/FeedItem" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/FeedItem">
      <operations>
        <operator>SET</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>100000</feedHolderId>
          <itemId>100</itemId>
          <inStock>1</inStock>
          <capacity>100</capacity>
          <price>2000</price>
          <salePrice>3000</salePrice>
          <formattedPrice>3,000円</formattedPrice>
          <formattedSalePrice>2,000円</formattedSalePrice>
          <displaySettings>1</displaySettings>
          <availability>IN_STOCK</availability>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス

| パラメータ | データ型 |
| -------- | ------- |
| rval | [FeedItemReturnValue](../data/FeedItem/FeedItemReturnValue.md) |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/FeedItem" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>FeedItem</ns2:service>
      <ns2:requestTime>1574394393466</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/FeedItem">
      <ns2:rval>
        <ListReturnValue.Type>FeedItemReturnValue</ListReturnValue.Type>
        <Operation.Type>SET</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:requestReceived>true</ns2:requestReceived>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
