# LocationService
LocationServiceでは、アカウントのロケーション情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201903/LocationService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201903/LocationService?wsdl|

#### Namespace
http://im.yahooapis.jp/V201903/Location

#### サービス概要
アカウントのロケーション情報を取得します。<br>
ほかのServiceとは、リクエストするURL（エンドポイント）が異なります。

#### 操作
LocationServiceで提供される操作を説明します。

##### LocationServiceの場合
メインURLを使用してリクエストを送信します。<br>
メインURLはLocationServiceのWSDLに含まれています。

##### ほかのServiceの場合
ローカルURLを使用してリクエストを送信します。<br>
ローカルURLの作成方法：<br>
　1. LocationServiceを使用して、割り当てられたコロケーションのURL接頭部を取得します。<br>
　2. URL接頭部を利用可能なバージョンと対象Service名と組み合わせます。

※ロケーション情報の有効期間は決まっておりません。<br>
　頻繁に変更されるものではありませんので、無効になった時点で取得しなおしてください。

+ [get](#get)
アカウントに割り当てられたロケーションのURL接頭部の情報を取得します。

#### オブジェクト
[Location](../data/Location)

## get
アカウントに割り当てられたロケーションのURL接頭部の情報を取得します。

### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201903/Location" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201903/Location">
      <accountId>1234567890</accountId>
    </get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
レスポンスフィールド

| パラメータ | データ型 | 説明 |
|---|---|---|
| rval | [LocationReturnValue](../data/Location/LocationReturnValue.md) | 操作結果を含むロケーション情報のコンテナです。 | error | [Error](../data/Common/Error.md) | エラーです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201903/Location" xmlns:ns2="http://im.yahooapis.jp/V201903">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1551686142117</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201903" xmlns:ns2="http://im.yahooapis.jp/V201903/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://im.yahooapis.jp/test</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
