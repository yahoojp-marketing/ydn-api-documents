# AdGroupAdService
AdGroupAdServiceは広告の操作を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AdGroupAdService?wsdl|
#### Namespace
http://im.yahooapis.jp/V6
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

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:ns1="http://im.yahooapis.jp/V6"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
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
                <ns1:adIds>8888888</ns1:adIds>
                <ns1:adIds>9999999</ns1:adIds>
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
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
                <ns1:totalNumEntries>1</ns1:totalNumEntries>
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
                        <ns1:impressionBeaconUrls>http:// www.yahoo.co.jp/</ns1:impressionBeaconUrls>
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

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>                
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
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
                    <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>                
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
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
                    <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                    <ns1:impressionBeaconUrls>http:// yahoo2.co.jp</ns1:impressionBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1c</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:ResponsiveAd">
                        <ns1:type>RESPONSIVE_AD</ns1:type>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
                    </ns1:ad>
                     <ns1:impressionBeaconUrls></ns1:impressionBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1d</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:StaticFrameAd">
                        <ns1:type>STATIC_FRAME_AD</ns1:type>
                        <ns1:size>300X250</ns1:size>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:layout>SQUARE_BANNER_TOP</ns1:layout>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
                        <ns1:colorSetId>123213</ns1:colorSetId>
                    </ns1:ad>
               </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1e</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPVAdGroupAdBid">
                        <ns1:type>MANUAL_CPV</ns1:type>
                        <ns1:maxCpv>100</ns1:maxCpv>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:VideoAd">
                        <ns1:type>VIDEO_AD</ns1:type>
                        <ns1:thumbnailMediaId>123456</ns1:thumbnailMediaId>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
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
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
                        <ns1:adName>広告名１a</ns1:adName >
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
                            <ns1:headline>タイトル（PC）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http: //yahoo.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>たいとる（もば）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                        <ns1:impressionBeaconUrls>http:// yahoo2.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:adId>88888888</ns1:adId>
                        <ns1:adName>広告名1c</ns1:adName>
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:ResponsiveAd">
                            <ns1:type>RESPONSIVE_AD</ns1:type>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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
                        <ns1:adId>99999999</ns1:adId>
                        <ns1:adName>広告名1d</ns1:adName >
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:StaticFrameAd">
                            <ns1:type>STATIC_FRAME_AD</ns1:type>
                            <ns1:size>300X250</ns1:size>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:layout>SQUARE_BANNER_TOP</ns1:layout>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
                            <ns1:colorSetId>123213</ns1:colorSetId>
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
                        <ns1:adId>12341234</ns1:adId>
                        <ns1:adName>広告名1e</ns1:adName >
                        <ns1:adStyle>VIDEO</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPVAdGroupAdBid">
                            <ns1:type>MANUAL_CPV</ns1:type>
                            <ns1:maxCpv>100</ns1:maxCpv>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:VideoAd">
                            <ns1:type>VIDEO_AD</ns1:type>
                            <ns1:thumbnailMediaId>123456</ns1:thumbnailMediaId>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>SET</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１a</ns1:adName>                
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
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
                    <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名１b</ns1:adName>                
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
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
                    <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                    <ns1:impressionBeaconUrls>http:// yahoo2.co.jp</ns1:impressionBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1c</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:ResponsiveAd">
                        <ns1:type>RESPONSIVE_AD</ns1:type>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
                    </ns1:ad>
                     <ns1:isRemoveBeaconUrls>TRUE</ns1:isRemoveBeaconUrls>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1d</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>100</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:StaticFrameAd">
                        <ns1:type>STATIC_FRAME_AD</ns1:type>
                        <ns1:size>300X250</ns1:size>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:layout>SQUARE_BANNER_TOP</ns1:layout>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
                        <ns1:colorSetId>123213</ns1:colorSetId>
                    </ns1:ad>
               </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adName>広告名1e</ns1:adName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPVAdGroupAdBid">
                        <ns1:type>MANUAL_CPV</ns1:type>
                        <ns1:maxCpv>100</ns1:maxCpv>
                    </ns1:bid>
                    <ns1:ad xsi:type="ns1:VideoAd">
                        <ns1:type>VIDEO_AD</ns1:type>
                        <ns1:thumbnailMediaId>1234567</ns1:thumbnailMediaId>
                        <ns1:headline>タイトル</ns1:headline>
                        <ns1:description>説明</ns1:description>
                        <ns1:url>http://www.yahoo.co.jp</ns1:url>
                        <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                        <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                        <ns1:principal>主体者表記</ns1:principal>
                        <ns1:logoMediaId>1111</ns1:logoMediaId>
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
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
                        <ns1:adName>広告名１a</ns1:adName >
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
                            <ns1:headline>タイトル（PC）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http: //yahoo.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>たいとる（もば）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                        <ns1:impressionBeaconUrls>http:// yahoo2.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:adId>88888888</ns1:adId>
                        <ns1:adName>広告名1c</ns1:adName>
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:ResponsiveAd">
                            <ns1:type>RESPONSIVE_AD</ns1:type>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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
                        <ns1:adId>99999999</ns1:adId>
                        <ns1:adName>広告名1d</ns1:adName >
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:StaticFrameAd">
                            <ns1:type>STATIC_FRAME_AD</ns1:type>
                            <ns1:size>300X250</ns1:size>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:layout>SQUARE_BANNER_TOP</ns1:layout>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
                            <ns1:colorSetId>123213</ns1:colorSetId>
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
                        <ns1:adId>12341234</ns1:adId>
                        <ns1:adName>広告名1e</ns1:adName >
                        <ns1:adStyle>VIDEO</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPVAdGroupAdBid">
                            <ns1:type>MANUAL_CPV</ns1:type>
                            <ns1:maxCpv>100</ns1:maxCpv>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:VideoAd">
                            <ns1:type>VIDEO_AD</ns1:type>
                            <ns1:thumbnailMediaId>123456</ns1:thumbnailMediaId>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
              <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>111111111</ns1:accountId>
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
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adId>8888888</ns1:adId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adId>9999999</ns1:adId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>111111111</ns1:accountId>
                    <ns1:campaignId>2222222</ns1:campaignId>
                    <ns1:adGroupId>3333333</ns1:adGroupId>
                    <ns1:adId>1231231</ns1:adId>
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
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V6"
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
                        <ns1:adName>広告名１a</ns1:adName >
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
                            <ns1:headline>タイトル（PC）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http: //yahoo.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:approvalStatus>APPROVED</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:MobileAd">
                            <ns1:type>TEXT_SHORT_AD1</ns1:type>
                            <ns1:url>http: //yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:headline>たいとる（もば）</ns1:headline>
                            <ns1:description>説明文１</ns1:description>
                            <ns1:description2>説明文２</ns1:description2>
                            <ns1:mobileCarriers>DOCOMO</ns1:mobileCarriers>
                            <ns1:mobileCarriers>KDDI</ns1:mobileCarriers>
                            <ns1:mobileCarriers>SOFTBANK</ns1:mobileCarriers>
                        </ns1:ad>
                        <ns1:impressionBeaconUrls>http:// yahoo.co.jp</ns1:impressionBeaconUrls>
                        <ns1:impressionBeaconUrls>http:// yahoo2.co.jp</ns1:impressionBeaconUrls>
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
                        <ns1:adId>88888888</ns1:adId>
                        <ns1:adName>広告名1c</ns1:adName>
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:ResponsiveAd">
                            <ns1:type>RESPONSIVE_AD</ns1:type>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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
                        <ns1:adId>99999999</ns1:adId>
                        <ns1:adName>広告名1d</ns1:adName >
                        <ns1:adStyle>IMAGE</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupAdBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>100</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:StaticFrameAd">
                            <ns1:type>STATIC_FRAME_AD</ns1:type>
                            <ns1:size>300X250</ns1:size>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:layout>SQUARE_BANNER_TOP</ns1:layout>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
                            <ns1:colorSetId>123213</ns1:colorSetId>
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
                        <ns1:adId>1231231</ns1:adId>
                        <ns1:adName>広告名1e</ns1:adName >
                        <ns1:adStyle>VIDEO</ns1:adStyle>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:approvalStatus>REVIEW</ns1:approvalStatus>
                        <ns1:bid xsi:type="ns1:ManualCPVAdGroupAdBid">
                            <ns1:type>MANUAL_CPV</ns1:type>
                            <ns1:maxCpv>100</ns1:maxCpv>
                        </ns1:bid>
                        <ns1:ad xsi:type="ns1:VideoAd">
                            <ns1:type>VIDEO_AD</ns1:type>
                            <ns1:thumbnailMediaId>123456</ns1:thumbnailMediaId>
                            <ns1:headline>タイトル</ns1:headline>
                            <ns1:description>説明</ns1:description>
                            <ns1:url>http://www.yahoo.co.jp</ns1:url>
                            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
                            <ns1:buttonText>FOR_MORE_INFO</ns1:buttonText>
                            <ns1:principal>主体者表記</ns1:principal>
                            <ns1:logoMediaId>1111</ns1:logoMediaId>
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
