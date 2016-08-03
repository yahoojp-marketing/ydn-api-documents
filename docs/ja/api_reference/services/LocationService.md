# LocationService
LocationServiceでは、アカウントのロケーション情報を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/LocationService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/LocationService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
Webサービスをリクエストする際には、まずLocationServiceを利用し、アカウントのコロケーションを取得してください。<br>
次に取得したコロケーションのURL接頭部よりローカルURLを作成しWebサービスをリクエストします。<br>
なお、LocationService自体は、LocationServiceのWSDLに記載されたメインURLを使用します。

#### 操作

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

## get
### リクエスト

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| accountId | ○ | xsd:long | アカウントIDです。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5"> 
  <SOAP-ENV:Header> 
    <ns1:RequestHeader> 
      <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
      <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword> 
    </ns1:RequestHeader> 
  </SOAP-ENV:Header> 
  <SOAP-ENV:Body> 
    <ns1:get> 
      <ns1:accountId>1000000001</ns1:accountId> 
    </ns1:get> 
  </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
レスポンスフィールド

| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [LocationReturnValue](../data/LocationReturnValue.md) | 操作結果を含むロケーション情報のコンテナです。 | error | [Error](../data/Error.md) | エラーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V5">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>LocationService</ns1:service>
      <ns1:remainingQuota>4999</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.3899</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:operationSucceeded>true</ns1:operationSucceeded>
        <ns1:value>colo01.im.yahooapis.jp</ns1:value>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
