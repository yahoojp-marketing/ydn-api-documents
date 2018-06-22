# PlacementUrlIdeaService
プレイスメントターゲティングで入稿時に設定するURL候補を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V201806/PlacementUrlIdeaService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V201806/PlacementUrlIdeaService?wsdl|
#### Namespace
http://im.yahooapis.jp/V201806/PlacementUrlIdea
#### サービス概要
プレイスメントターゲティングで入稿時に設定するURL候補を取得します。<br>
URLと共にPC、スマートフォン、タブレットでのリーチ数（Reaches）とADリクエスト数（AdRequests）が取得できます。
#### 操作
PlacementUrlIdeaServiceで提供される操作を説明します。

+ [get](#get)

#### オブジェクト
[PlacementUrlIdea](../data/PlacementUrlIdea)

## get

### リクエスト
URL候補を取得します。

| パラメータ | 必須 | データ型 | 説明 |
|---|---|---|---|
| selector | ○ | [PlacementUrlIdeaSelector](../data/PlacementUrlIdea/PlacementUrlIdeaSelector.md) | URL候補を取得します。 |

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlIdea" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <get xmlns="http://im.yahooapis.jp/V201806/PlacementUrlIdea" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <selector>
        <keyword>Yahoo</keyword>
        <siteCategories>TC-SC-8888888877</siteCategories>
        <adFormats>
          <adStyle>TEXT</adStyle>
        </adFormats>
        <adFormats>
          <adStyle>IMAGE</adStyle>
          <mediaAdFormat>SQUARE</mediaAdFormat>
        </adFormats>
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
| rval | [PlacementUrlIdeaPage](../data/PlacementUrlIdea/PlacementUrlIdeaPage.md) | 操作結果を含むコンテナです。 |

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <ResponseHeader xmlns="http://im.yahooapis.jp/V201806/PlacementUrlIdea" xmlns:ns2="http://im.yahooapis.jp/V201806">
      <ns2:service>PlacementUrlIdea</ns2:service>
      <ns2:requestTime>1528278913426</ns2:requestTime>
      <ns2:timeTakenSeconds>0.2671</ns2:timeTakenSeconds>
    </ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse xmlns="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/PlacementUrlIdea">
      <ns2:rval>
        <totalNumEntries>2</totalNumEntries>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:placementUrlIdea>
            <ns2:searchUrl>UNKNOWN_URL</ns2:searchUrl>
            <ns2:keyword/>
            <ns2:desktopReaches>0</ns2:desktopReaches>
            <ns2:desktopAdRequests>0</ns2:desktopAdRequests>
            <ns2:smartPhoneReaches>1500</ns2:smartPhoneReaches>
            <ns2:smartPhoneAdRequests>15000</ns2:smartPhoneAdRequests>
            <ns2:tabletReaches>0</ns2:tabletReaches>
            <ns2:tabletAdRequests>0</ns2:tabletAdRequests>
          </ns2:placementUrlIdea>
        </ns2:values>
        <ns2:values>
          <operationSucceeded>true</operationSucceeded>
          <ns2:placementUrlIdea>
            <ns2:searchUrl>yahoo.co.jp</ns2:searchUrl>
            <ns2:keyword>Yahoo</ns2:keyword>
            <ns2:siteCategory>TC-SC-8888888877</ns2:siteCategory>
            <ns2:adFormat>
              <ns2:adStyle>TEXT</ns2:adStyle>
              <ns2:adType>TEXT_LONG_AD1</ns2:adType>
            </ns2:adFormat>
            <ns2:adFormat>
              <ns2:adStyle>IMAGE</ns2:adStyle>
              <ns2:adType>STATIC_FRAME_AD</ns2:adType>
              <ns2:width>1200</ns2:width>
              <ns2:height>628</ns2:height>
            </ns2:adFormat>
            <ns2:desktopReaches>0</ns2:desktopReaches>
            <ns2:desktopAdRequests>0</ns2:desktopAdRequests>
            <ns2:smartPhoneReaches>1500</ns2:smartPhoneReaches>
            <ns2:smartPhoneAdRequests>15000</ns2:smartPhoneAdRequests>
            <ns2:tabletReaches>0</ns2:tabletReaches>
            <ns2:tabletAdRequests>0</ns2:tabletAdRequests>
          </ns2:placementUrlIdea>
        </ns2:values>
      </ns2:rval>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
