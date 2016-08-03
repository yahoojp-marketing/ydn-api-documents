# AdGroupService
AdGroupServiceは広告グループの操作を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AdGroupService?wsdl|
#### Namespace
http://im.yahooapis.jp/V5
#### サービス概要
広告グループの取得と更新を行います。
#### 操作
AdGroupServiceで提供される操作を説明します。
## get
### リクエスト
広告の情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupSelector](../data/AdGroupSelector.md) | 広告グループの情報を取得します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:campaignIds>100000001</ns1:campaignIds>
                <ns1:campaignIds>100000002</ns1:campaignIds>
                <ns1:adGroupIds>100000003</ns1:adGroupIds>
                <ns1:adGroupIds>100000004</ns1:adGroupIds>
                <ns1:adGroupIds>100000005</ns1:adGroupIds>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
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
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:get>
            <ns1:selector>
                <ns1:accountId>100000000</ns1:accountId>
                <ns1:campaignIds>100000003</ns1:campaignIds>
                <ns1:campaignIds>100000007</ns1:campaignIds>
                <ns1:adGroupIds>100000005</ns1:adGroupIds>
                <ns1:adGroupIds>100000006</ns1:adGroupIds>
                <ns1:adGroupIds>100000007</ns1:adGroupIds>
                <ns1:userStatuses>ACTIVE</ns1:userStatuses>
                <ns1:userStatuses>PAUSED</ns1:userStatuses>
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
| rval | [AdGroupPage](../data/AdGroupPage.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getResponse>
            <ns1:rval>
                <ns1:totalNumEntries>2</ns1:totalNumEntries>
                <ns1:Page.Type>AdGroupPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:adGroupId>1000000001</ns1:adGroupId>
                        <ns1:adGroupName>ad group name1</ns1:adGroupName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:device>DESKTOP</ns1:device>
                        <ns1:dynamicImageExtensions>ACTIVE</ns1:dynamicImageExtensions>
                    </ns1:adGroup>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:adGroupId>1000000002</ns1:adGroupId>
                        <ns1:adGroupName>ad group name2</ns1:adGroupName>
                        <ns1:userStatus>PAUSED</ns1:userStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:device>DESKTOP</ns1:device>
                        <ns1:device>TABLET</ns1:device>
                        <ns1:deviceApp>APP</ns1:deviceApp>
                        <ns1:deviceApp>WEB</ns1:deviceApp>
                        <ns1:deviceOs>ANDROID</ns1:deviceOs>
                        <ns1:deviceOs>IOS</ns1:deviceOs>
                        <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                        <ns1:dynamicImageExtensions>PAUSED</ns1:dynamicImageExtensions>
                    </ns1:adGroup>
                </ns1:values>
            </ns1:rval>
        </ns1:getResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### リクエスト
広告グループを追加します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | キャンペーンに広告グループを追加します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>200</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
                    <ns1:device>TABLET</ns1:device>
                    <ns1:deviceApp>APP</ns1:deviceApp>
                    <ns1:deviceApp>WEB</ns1:deviceApp>
                    <ns1:deviceOs>ANDROID</ns1:deviceOs>
                    <ns1:deviceOs>IOS</ns1:deviceOs>
                    <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                    <ns1:dynamicImageExtensions>ACTIVE</ns1:dynamicImageExtensions>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>120</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
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
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>ADD</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>200</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
                    <ns1:device>TABLET</ns1:device>
                    <ns1:deviceApp>APP</ns1:deviceApp>
                    <ns1:deviceApp>WEB</ns1:deviceApp>
                    <ns1:deviceOs>ANDROID</ns1:deviceOs>
                    <ns1:deviceOs>IOS</ns1:deviceOs>
                    <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                    <ns1:dynamicImageExtensions>ACTIVE</ns1:dynamicImageExtensions>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>120</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>ADD</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:adGroupId>1000000001</ns1:adGroupId>
                        <ns1:adGroupName>ad group name</ns1:adGroupName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:device>SMARTPHONE</ns1:device>
                        <ns1:deviceApp>APP</ns1:deviceApp>
                        <ns1:deviceOs>ANDROID</ns1:deviceOs>
                        <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                        <ns1:dynamicImageExtensions>ACTIVE</ns1:dynamicImageExtensions>
                    </ns1:adGroup>
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
広告グループを変更します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | 広告グループを変更します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000001</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>120</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
                    <ns1:device>TABLET</ns1:device>
                    <ns1:deviceApp>APP</ns1:deviceApp>
                    <ns1:deviceApp>WEB</ns1:deviceApp>
                    <ns1:deviceOs>ANDROID</ns1:deviceOs>
                    <ns1:deviceOs>IOS</ns1:deviceOs>
                    <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                    <ns1:dynamicImageExtensions>PAUSED</ns1:dynamicImageExtensions>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000002</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                    <ns1:userStatus>PAUSED</ns1:userStatus>
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
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>SET</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000001</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 1</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                    <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                        <ns1:type>MANUAL_CPC</ns1:type>
                        <ns1:maxCpc>120</ns1:maxCpc>
                    </ns1:bid>
                    <ns1:device>DESKTOP</ns1:device>
                    <ns1:device>TABLET</ns1:device>
                    <ns1:deviceApp>APP</ns1:deviceApp>
                    <ns1:deviceApp>WEB</ns1:deviceApp>
                    <ns1:deviceOs>ANDROID</ns1:deviceOs>
                    <ns1:deviceOs>IOS</ns1:deviceOs>
                    <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                    <ns1:dynamicImageExtensions>PAUSED</ns1:dynamicImageExtensions>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000002</ns1:adGroupId>
                    <ns1:adGroupName>ad group name 2</ns1:adGroupName>
                    <ns1:userStatus>ACTIVE</ns1:userStatus>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含むコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>SET</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:adGroupId>1000000001</ns1:adGroupId>
                        <ns1:adGroupName>ad group name</ns1:adGroupName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:device>DESKTOP</ns1:device>
                        <ns1:device>TABLET</ns1:device>
                        <ns1:deviceApp>APP</ns1:deviceApp>
                        <ns1:deviceApp>WEB</ns1:deviceApp>
                        <ns1:deviceOs>ANDROID</ns1:deviceOs>
                        <ns1:deviceOs>IOS</ns1:deviceOs>
                        <ns1:smartDeviceCarriers>DOCOMO</ns1:smartDeviceCarriers>
                        <ns1:dynamicImageExtensions>PAUSED</ns1:dynamicImageExtensions>
                    </ns1:adGroup>
                </ns1:values>
                <ns1:values>
                        <ns1:operationSucceeded>false</ns1:operationSucceeded>
                        <ns1:error>
                            <code>2012</ns1:code>
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
広告グループを削除します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupOperation](../data/AdGroupOperation.md) | キャンペーンから広告グループを削除します。 | 

##### ＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
xmlns:ns1="http://im.yahooapis.jp/V5">
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
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000001</ns1:adGroupId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000002</ns1:adGroupId>
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
            <ns1:license>1111-1111-1111-1111</ns1:license>
            <ns1:apiAccountId>2222-2222-2222-2222</ns1:apiAccountId>
            <ns1:apiAccountPassword>password</ns1:apiAccountPassword>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>3333-3333-3333-3333</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>password2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutate>
            <ns1:operations>
                <ns1:operator>REMOVE</ns1:operator>
                <ns1:accountId>1000000001</ns1:accountId>
                <ns1:campaignId>1000000001</ns1:campaignId>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000001</ns1:adGroupId>
                </ns1:operand>
                <ns1:operand>
                    <ns1:accountId>1000000001</ns1:accountId>
                    <ns1:campaignId>1000000001</ns1:campaignId>
                    <ns1:adGroupId>1000000002</ns1:adGroupId>
                </ns1:operand>
            </ns1:operations>
        </ns1:mutate>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupReturnValue](../data/AdGroupReturnValue.md) | 操作結果を含むコンテナです | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://im.yahooapis.jp/V5"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>AdGroupService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:mutateResponse>
            <ns1:rval>
                <ns1:ListReturnValue.Type>AdGroupReturnValue</ns1:ListReturnValue.Type>
                <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:accountId>1000000001</ns1:accountId>
                        <ns1:campaignId>1000000001</ns1:campaignId>
                        <ns1:campaignName>campaign name</ns1:campaignName>
                        <ns1:adGroupId>1000000001</ns1:adGroupId>
                        <ns1:adGroupName>ad group name</ns1:adGroupName>
                        <ns1:userStatus>ACTIVE</ns1:userStatus>
                        <ns1:bid xsi:type="ns1:ManualCPCAdGroupBid">
                            <ns1:type>MANUAL_CPC</ns1:type>
                            <ns1:maxCpc>120</ns1:maxCpc>
                        </ns1:bid>
                        <ns1:device>SMARTPHONE</ns1:device>
                        <ns1:deviceApp>APP</ns1:deviceApp>
                        <ns1:deviceOs>ANDROID</ns1:deviceOs>
                        <ns1:dynamicImageExtensions>PAUSED</ns1:dynamicImageExtensions>
                    </ns1:adGroup>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>false</ns1:operationSucceeded>
                    <ns1:adGroup>
                        <ns1:adGroupId>1000000002</ns1:adGroupId>
                    </ns1:adGroup>
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
