# AdGroupAdService
AdGroupAdServiceは広告の操作を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
広告の取得と更新を行います。
#### 操作
AdGroupAdServiceで提供される操作を説明します。
## get
### リクエスト
広告の情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupAdSelector](../data/AdGroupAdSelector.md) | 広告の情報を取得します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignIds>2222222</ns1:campaignIds>
                <ns1:adGroupIds>3333333</ns1:adGroupIds>
                <ns1:adIds>5555555</ns1:adIds>
                <ns1:adIds>7777777</ns1:adIds>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
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
 xmlns:ns1="http://im.yahooapis.jp/V5">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignIds>2222222</ns1:campaignIds>
                <ns1:adGroupIds>3333333</ns1:adGroupIds>
                <ns1:adIds>5555555</ns1:adIds>
                <ns1:adIds>7777777</ns1:adIds>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
                <ns1:approvalStatuses>REVIEW</ns1:approvalStatuses>
                <ns1:paging>
                  <ns1:startIndex>1</ns1:startIndex>
                  <ns1:numberResults>20</ns1:numberResults>
                </ns1:paging>
            </ns1:selector>
        </ns1:get>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>　
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdPage](../data/AdGroupAdPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupAdPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>5555555</ns1:adId>
                        <ns1:adName>PC広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle >
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:TextAd">
                            <ns1:type>TEXT_LONG_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>PC広告タイトル</ns1:headline>
                            <ns1:description>PC広告の説明文１</ns1:description>
                            <ns1:description2>PC広告の説明文２</ns1:description2>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>7777777</ns1:adId>
                        <ns1:adName>モバイル広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle >
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>PRE_DISAPPROVED</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes>Z101</ns1:disapprovalReasonCodes>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>0</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>モバイル広告タイトル</ns1:headline>
                            <ns1:description>モバイル説明１</ns1:description>
                            <ns1:description2>モバイル説明２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### リクエスト
広告を追加します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 広告グループに広告を追加します。 | 

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
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>                  
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:TextAd">
                        <ns1:type>TEXT_LONG_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>タイトル（PC）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                    </ns1:ad>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>                  
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:MobileAd">
                        <ns1:type>TEXT_SHORT_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>たいとる（もば）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                        <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                        <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                        <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                    </ns1:ad>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
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
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>                  
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:TextAd">
                        <ns1:type>TEXT_LONG_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>タイトル（PC）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                    </ns1:ad>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>                 
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:MobileAd">
                        <ns1:type>TEXT_SHORT_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>たいとる（もば）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                        <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                        <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                        <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                    </ns1:ad>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>5555555</ns1:adId>
                        <ns1:adName>PC広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:TextAd">
                            <ns1:type>TEXT_LONG_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>PC広告タイトル</ns1:headline>
                            <ns1:description>PC広告の説明文１</ns1:description>
                            <ns1:description2>PC広告の説明文２</ns1:description2>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>7777777</ns1:adId>
                        <ns1:adName>モバイル広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>モバイル広告タイトル</ns1:headline>
                            <ns1:description>モバイル説明１</ns1:description>
                            <ns1:description2>モバイル説明２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### リクエスト
広告を変更します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 広告グループに登録された広告を変更します。 | 

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
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>
                    <ns1:adId>5555555</ns1:adId>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:TextAd">
                        <ns1:type>TEXT_LONG_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>タイトル（PC）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                    </ns1:ad>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>
                    <ns1:adId>7777777</ns1:adId>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:MobileAd">
                        <ns1:type>TEXT_SHORT_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>たいとる（もば）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                        <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                        <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                        <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                    </ns1:ad>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
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
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>
                    <ns1:adId>5555555</ns1:adId>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:TextAd">
                        <ns1:type>TEXT_LONG_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>タイトル（PC）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                    </ns1:ad>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>
                    <ns1:adId>7777777</ns1:adId>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:MobileAd">
                        <ns1:type>TEXT_SHORT_AD1</ns1:type>
                        <ns1:url>http: //yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>yahoo.co.jp</ns1:displayUrl>
                        <ns1:headline>たいとる（もば）</ns1:headline>
                        <ns1:description>説明文１</ns1:description>
                        <ns1:description2>説明文２</ns1:description2>
                        <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                    </ns1:ad>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>5555555</ns1:adId>
                        <ns1:adName>PC広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:TextAd">
                            <ns1:type>TEXT_LONG_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>PC広告タイトル</ns1:headline>
                            <ns1:description>PC広告の説明文１</ns1:description>
                            <ns1:description2>PC広告の説明文２</ns1:description2>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>7777777</ns1:adId>
                        <ns1:adName>モバイル広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>PRE_DISAPPROVED</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes>Z101</ns1:disapprovalReasonCodes>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>モバイル広告タイトル</ns1:headline>
                            <ns1:description>モバイル説明１</ns1:description>
                            <ns1:description2>モバイル説明２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### リクエスト
広告を削除します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupAdOperation](../data/AdGroupAdOperation.md) | 広告を削除します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
              <ns1:operator>REMOVE</ns1:operator> 
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand> 
                    <ns1:accountId>111111111</ns1:accountId> 
                    <ns1:campaignId>2222222</ns1:campaignId> 
                    <ns1:adGroupId>3333333</ns1:adGroupId> 
                    <ns1:adId>5555555</ns1:adId> 
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:accountId>111111111</ns1:accountId> 
                    <ns1:campaignId>2222222</ns1:campaignId> 
                    <ns1:adGroupId>3333333</ns1:adGroupId> 
                    <ns1:adId>7777777</ns1:adId> 
                </ns1:operand> 
            </ns1:operations> 
        </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

##### ＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?> 
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"> 
    <SOAP-ENV:Header> 
        <ns1:RequestHeader> 
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license> 
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId> 
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword> 
            <ns1:accountId>111111111</ns1:accountId> 
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxxx</ns1:onBehalfOfAccountId> 
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword> 
        </ns1:RequestHeader> 
    </SOAP-ENV:Header> 
    <SOAP-ENV:Body> 
        <ns1:mutate> 
            <ns1:operations> 
              <ns1:operator>REMOVE</ns1:operator> 
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:campaignId>2222222</ns1:campaignId>
                <ns1:adGroupId>3333333</ns1:adGroupId>
                <ns1:operand> 
                    <ns1:accountId>111111111</ns1:accountId> 
                    <ns1:campaignId>2222222</ns1:campaignId> 
                    <ns1:adGroupId>3333333</ns1:adGroupId> 
                    <ns1:adId>5555555</ns1:adId> 
                </ns1:operand> 
                <ns1:operand> 
                    <ns1:accountId>111111111</ns1:accountId> 
                    <ns1:campaignId>2222222</ns1:campaignId> 
                    <ns1:adGroupId>3333333</ns1:adGroupId> 
                    <ns1:adId>7777777</ns1:adId> 
                </ns1:operand> 
            </ns1:operations> 
        </ns1:mutate> 
    </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupAdReturnValue](../data/AdGroupAdReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupAdService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupAdReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>5555555</ns1:adId>
                        <ns1:adName>PC広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:TextAd">
                            <ns1:type>TEXT_LONG_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>PC広告タイトル</ns1:headline>
                            <ns1:description>PC広告の説明文１</ns1:description>
                            <ns1:description2>PC広告の説明文２</ns1:description2>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroupAd>
                        <ns1:accountId>111111111</ns1:accountId>
                        <ns1:campaignId>2222222</ns1:campaignId>
                        <ns1:campaignName>サンプルキャンペーン</ns1:campaignName>
                        <ns1:adGroupId>3333333</ns1:adGroupId>
                        <ns1:adGroupName>サンプル広告グループ</ns1:adGroupName>
                        <ns1:adId>7777777</ns1:adId>
                        <ns1:adName>モバイル広告名</ns1:adName >
                        <ns1:adStyle>TEXT</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>PRE_DISAPPROVED</ns1:approvalStatus>
                        <ns1:disapprovalReasonCodes>Z101</ns1:disapprovalReasonCodes>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>モバイル広告タイトル</ns1:headline>
                            <ns1:description>モバイル説明１</ns1:description>
                            <ns1:description2>モバイル説明２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                    </ns1:adGroupAd>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:error>
                        <ns1:code>2012</ns1:code>
                        <ns1:message>This is Sample Error</ns1:message>
                        <ns1:detail/>
                    </ns1:error>
                </ns1:values>
            </ns1:rval>
        </ns1:mutateResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
