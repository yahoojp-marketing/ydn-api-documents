# LocationService
LocationServiceでは、アカウントのロケーション情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/LocationService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/LocationService?wsdl|

#### Namespace
http://im.yahooapis.jp/V201806/

#### サービス概要
Webサービスをリクエストする際には、まずLocationServiceを利用し、アカウントのコロケーションを取得してください。<br>
次に取得したコロケーションのURL接頭部よりローカルURLを作成しWebサービスをリクエストします。<br>
なお、LocationService自体は、LocationServiceのWSDLに記載されたメインURLを使用します。

#### 操作
LocationServiceで提供される操作を説明します。

##### LocationServiceの場合
メインURLを使用してLocationServiceに対してリクエストを送信します。<br>
メインURLはLocationServiceのWSDLに含まれています。

##### その他のWebサービスの場合
ローカルURLを使用してリクエストを送信します。<br>
ローカルURLを作成するには、 LocationServiceを使用して、アカウントに割り当てられたコロケーションのURL接頭部を入手します。<br>
次に、URL接頭部を現行バージョンおよび特定のサービス名と組み合わせて、ローカルURLを作成します。<br>
<br>
また、ロケーション情報の有効な期間は決まっていませんが、頻繁に変更されるものではありませんので、各処理の度に取得する必要はありません。<br>
無効になった場合は、Invalid locationエラーが発生します。その場合は再取得を実施してください。

+ [get](#get)

#### オブジェクト
[Location](../data/Location)

## get

### リクエスト

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/Location" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/Location">
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
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/Location" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>Location</ns2:service>
      <ns2:requestTime>1528278912470</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Location">
      <ns2:rval>
        <operationSucceeded>true</operationSucceeded>
        <ns2:value>https://im.yahooapis.jp/test</ns2:value>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
