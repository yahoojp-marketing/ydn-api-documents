# PlacementUrlIdeaService
プレイスメントターゲティングで入稿時に設定するURL候補を取得します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/V5.2/PlacementUrlIdeaService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/V5.2/PlacementUrlIdeaService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
プレイスメントターゲティングで入稿時に設定するURL候補を取得します。<br>
URLと共にPC、スマートフォン、タブレットでのリーチ数（Reaches）とADリクエスト数（AdRequests）が取得できます。
#### 操作
PlacementUrlIdeaServiceで提供される操作を説明します。
## get
### リクエスト
URL候補を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [PlacementUrlIdeaSelector](../data/PlacementUrlIdeaSelector.md) | URL候補を取得します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
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
                <ns1:conditions>
                    <ns1:keyword>Yahoo</ns1:keyword>
                    <ns1:siteCategory>TC-SC-8888888888</ns1:siteCategory>
                </ns1:conditions> 
                <ns1:conditions>
                    <ns1:keyword>Yahooo</ns1:keyword>
                    <ns1:siteCategory>TC-SC-8888888877</ns1:siteCategory>
                </ns1:conditions> 
                <ns1:paging>
                   <ns1:startIndex>1</ns1:startIndex>
                   <ns1:numberResults>3</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:conditions>
                    <ns1:keyword>Yahoo</ns1:keyword>
                    <ns1:siteCategory>TC-SC-8888888888</ns1:siteCategory>
                </ns1:conditions> 
                <ns1:conditions>
                    <ns1:keyword>Yahooo</ns1:keyword>
                    <ns1:siteCategory>TC-SC-8888888877</ns1:siteCategory>
                </ns1:conditions> 
                <ns1:paging>
                   <ns1:startIndex>1</ns1:startIndex>
                   <ns1:numberResults>3</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [PlacementUrlIdeaPage](../data/PlacementUrlIdeaPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>PlacementUrlIdeaService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>PlacementUrlIdeaPage</ns1:Page.Type>
                <ns1:values>
                <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:placementUrlIdea>
                        <ns1:searchUrl>UNKNOWN_URL</ns1:searchUrl>
                         <ns1:desktopReaches>100</ns1:desktopReaches>
                         <ns1:desktopAdRequests>100</ns1:desktopAdRequests>
                         <ns1:smartPhoneReaches>60</ns1:smartPhoneReaches>
                         <ns1:smartPhoneAdRequests>60</ns1:smartPhoneAdRequests>
                         <ns1:tabletReaches>30</ns1:tabletReaches>
                         <ns1:tabletAdRequests>30</ns1:tabletAdRequests>
                    </ns1:placementUrlIdea>
                </ns1:values>
                <ns1:values>
                    <ns1:operationKey>0</ns1:operationKey>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:placementUrlIdea>
                        <ns1:keyword>Yahoo</ns1:keyword>
                        <ns1:siteCategory>TC-SC-8888888888</ns1:siteCategory>
                        <ns1:searchUrl>yahoo.co.jp</ns1:searchUrl>
                        <ns1:adFormat>
　　　                  <ns1:type>TEXT</ns1:type>
                        </ns1:adFormat>
　　　　　　   <ns1:adFormat>
　　　　　　       <ns1:type>IMAGE</ns1:type>
                            <ns1:width>728</ns1:width>
                        <ns1:height>90</ns1:height>
                        </ns1:adFormat>
                        <ns1:adFormat>                        
                        <ns1:type>IMAGE</ns1:type>
                            <ns1:width>320</ns1:width>
                            <ns1:height>250</ns1:height>
                        </ns1:adFormat>                       
                        <ns1:adFormat>
                            <ns1:type>IMAGE</ns1:type>
                            <ns1:width>320</ns1:width>
                            <ns1:height>100</ns1:height>
                        </ns1:adFormat>
                        <ns1:desktopRearches>1000</ns1:desktopRearches>
                        <ns1:desktopAdRequests>100</ns1:desktopAdRequests>
                        <ns1:smartPhoneRearches>60</ns1:smartPhoneRearches>
                        <ns1:smartPhoneAdRequests>60</ns1:smartPhoneAdRequests>
                        <ns1:tabletRearches>30</ns1:tabletRearches>
                        <ns1:tabletAdRequests>30</ns1:tabletRearches>
                    </ns1:placementUrlIdea> 
                </ns1:values>
                <ns1:values>
                     <ns1:operationKey>1</ns1:operationKey>
                     <ns1:operationSucceeded>true</ns1:operationSucceeded>
                   　<ns1:placementUrlIdea>
                        <ns1:keyword>Yahooo</ns1:keyword>
                        <ns1:siteCategory>TC-SC-8888888877</ns1:siteCategory>
                        <ns1:searchUrl>yahoo.co.jp</ns1:searchUrl>
                        <ns1:adFormat>
                        <ns1:type>TEXT</ns1:type>
                        </ns1:adFormat>
                        <ns1:desktopRearches>1000</ns1:desktopRearches>
                        <ns1:desktopAdRequests>100</ns1:desktopAdRequests>
                        <ns1:smartPhoneRearches>60</ns1:smartPhoneRearches>
                        <ns1:smartPhoneAdRequests>60</ns1:smartPhoneAdRequests>
                        <ns1:tabletRearches>30</ns1:tabletRearches>
                        <ns1:tabletAdRequests>30</ns1:tabletAdRequests>
                     </ns1:placementUrlIdea> 
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
