# FeedFtpRequestService
FeedFtpRequestServiceでは、登録されたFTP設定情報を即時実行を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201911/FeedFtpRequestService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201911/FeedFtpRequestService?wsdl |

#### Namespace
http://im.yahooapis.jp/V201911/FeedFtpRequest

#### サービス概要
登録されたFTP設定情報の即時実行を行います。

#### 操作
提供される操作を説明します。

+ [mutate(ADD)](#mutateadd)

#### オブジェクト
[FeedFtpRequest](../data/FeedFtpRequest)

## mutate(ADD)
登録されたFTP設定情報の即時実行を行います。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| operations | ○ | [FeedFtpRequestOperation](../data/FeedFtpRequest/FeedFtpRequestOperation.md) | 即時実行を行うFTP設定情報 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201911/FeedFtpRequest" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <mutate xmlns="http://im.yahooapis.jp/V201911/FeedFtpRequest">
      <operations>
        <operator>ADD</operator>
        <accountId>1234567890</accountId>
        <operand>
          <feedHolderId>10001</feedHolderId>
        </operand>
      </operations>
    </mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
| フィールド | データ型 | 説明 |
|---|---|---|
| rval | [FeedFtpReturnValue](../data/FeedFtpRequest/FeedFtpRequestReturnValue.md) | 登録結果 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201911/FeedFtpRequest" xmlns:ns2="http://im.yahooapis.jp/V201911">
      <ns2:service>FeedFtpRequest</ns2:service>
      <ns2:requestTime>1574414261453</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse xmlns="http://im.yahooapis.jp/V201911" xmlns:ns2="http://im.yahooapis.jp/V201911/FeedFtpRequest">
      <ns2:rval>
        <ListReturnValue.Type>FeedSetReturnValue</ListReturnValue.Type>
        <Operation.Type>ADD</Operation.Type>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:feedFtp>
            <ns2:feedHolderId>10001</ns2:feedHolderId>
          </ns2:feedFtp>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
