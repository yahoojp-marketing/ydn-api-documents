# AdGroupTargetService
AdGroupTargetServiceでは、広告グループにおけるターゲティング設定情報の操作（取得、追加、更新、削除、置換）を行います。
#### WSDL
| environment | url |
|---|---|
| production  | https://location.im.yahooapis.jp/services/Vx.x/AdGroupTargetService?wsdl |
| sandbox  | https://sandbox.im.yahooapis.jp/services/Vx.x/AdGroupTargetService?wsdl |
#### Namespace
http://im.yahooapis.jp/V6
#### サービス概要
広告グループにおけるターゲティング設定情報の操作（取得、追加、更新、置き換え、削除）を行います。
#### 操作
AdGroupTargetServiceで提供される操作を説明します。

## get
### リクエスト
広告グループにおけるターゲティングの設定情報を取得します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupTargetSelector](../data/AdGroupTargetSelector.md) | getメソッドの検索条件（実行パラメータ）を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:v6="http://im.yahooapis.jp/V6">
  <soapenv:Header>
    <v6:RequestHeader>
      <v6:license>1111-1111-1111-1111</v6:license>
      <v6:apiAccountId>2222-2222-2222-2222</v6:apiAccountId>
      <v6:apiAccountPassword>password</v6:apiAccountPassword>
    </v6:RequestHeader>
  </soapenv:Header>
  <soapenv:Body>
    <v6:get>
      <v6:selector>
        <v6:accountId>10</v6:accountId>
        <v6:campaignIds>11100</v6:campaignIds>
        <v6:campaignIds>200010</v6:campaignIds>
        <v6:adGroupIds>9999</v6:adGroupIds>
        <v6:targetTypes>AD_SCHEDULE_TARGET</v6:targetTypes>
        <v6:targetTypes>GEO_TARGET</v6:targetTypes>
        <v6:targetTypes>AGE_TARGET</v6:targetTypes>
        <v6:targetTypes>GENDER_TARGET</v6:targetTypes>
        <v6:targetTypes>INTEREST_CATEGORY</v6:targetTypes>
        <v6:targetTypes>SITE_CATEGORY</v6:targetTypes>
        <v6:targetTypes>SITE_RETARGETING</v6:targetTypes>
        <v6:targetTypes>SEARCH_TARGET</v6:targetTypes>
        <v6:targetTypes>PLACEMENT_TARGET</v6:targetTypes>
        <v6:targetTypes>DEVICE_TARGET</v6:targetTypes>
        <v6:targetTypes>CARRIER_TARGET</v6:targetTypes>
        <v6:targetTypes>APP_TARGET</v6:targetTypes>
        <v6:targetTypes>OS_TARGET</v6:targetTypes>
        <v6:targetTypes>OS_VERSION_TARGET</v6:targetTypes>
        <v6:paging>
          <v6:startIndex>1</v6:startIndex>
          <v6:numberResults>100</v6:numberResults>
        </v6:paging>
      </v6:selector>
    </v6:get>
  </soapenv:Body>
</soapenv:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupTargetPage](../data/AdGroupTargetPage.md) | getメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupTargetService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>1</ns1:totalNumEntries>
        <ns1:Page.Type>AdGroupTargetPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>10</ns1:startHour>
              <ns1:endHour>20</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:dayOfWeek>TUESDAY</ns1:dayOfWeek>
              <ns1:startHour>10</ns1:startHour>
              <ns1:endHour>20</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:dayOfWeek>SUNDAY</ns1:dayOfWeek>
              <ns1:startHour>2</ns1:startHour>
              <ns1:endHour>22</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GeoTarget">
              <ns1:type>GEO_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:geo>TC-CI-00000102</ns1:geo>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:InterestCategoryTarget">
              <ns1:type>INTEREST_CATEGORY</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:category>TC-IC-20110160100</ns1:category>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:SiteCategoryTarget">
              <ns1:type>SITE_CATEGORY</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:category>TC-SC-10110110100100</ns1:category>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:gender>ST_MALE</ns1:gender>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:gender>ST_UNKNOWN</ns1:gender>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:age>GT_RANGE22_29</ns1:age>
              <ns1:estimateFlg>PAUSED</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:age>GT_RANGE30_39</ns1:age>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:age>GT_UNKNOWN</ns1:age>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:PlacementTarget">
              <ns1:type>PLACEMENT_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:urlListId>555555555</ns1:urlListId>
              <ns1:urlListName>Sample</ns1:urlListName>
              <ns1:urlListType>WHITE_LIST</ns1:urlListType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:DeviceTarget">
              <ns1:type>DEVICE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:device>WAP_MOBILE</ns1:device>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:CarrierTarget">
              <ns1:type>CARRIER_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:carrier>SOFTBANK</ns1:carrier>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:DeviceAppTarget">
              <ns1:type>APP_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:deviceApp>APP</ns1:deviceApp>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:DeviceOsTarget">
              <ns1:type>OS_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:deviceOs>IOS</ns1:deviceOs>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:DeviceOsVersionTarget">
              <ns1:type>OS_VERSION_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:deviceOsVersion>v4.5</ns1:deviceOsVersion>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
### リクエスト
広告グループにおけるターゲティングの設定情報を追加します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupTargetMutateOperation](../data/AdGroupTargetMutateOperation.md) | mutate/replaceメソッドで操作対象となるターゲティング設定情報を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:v6="http://im.yahooapis.jp/V6"
                  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <soapenv:Header>
    <v6:RequestHeader>
      <v6:license>1111-1111-1111-1111</v6:license>
      <v6:apiAccountId>2222-2222-2222-2222</v6:apiAccountId>
      <v6:apiAccountPassword>password</v6:apiAccountPassword>
    </v6:RequestHeader>
  </soapenv:Header>
  <soapenv:Body>
    <v6:mutate>
      <v6:operations>
        <v6:operator>ADD</v6:operator>
        <v6:accountId>10</v6:accountId>
        <v6:operand>
          <v6:campaignId>10</v6:campaignId>
          <v6:adGroupId>10</v6:adGroupId>
          <v6:target xsi:type="v6:AgeTarget">
            <v6:type>AGE_TARGET</v6:type>
            <v6:age>GT_RANGE12_14</v6:age>
            <v6:estimateFlg>ACTIVE</v6:estimateFlg>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>10</v6:campaignId>
          <v6:adGroupId>10</v6:adGroupId>
          <v6:target xsi:type="v6:GenderTarget">
            <v6:type>GENDER_TARGET</v6:type>
            <v6:gender>ST_UNKNOWN</v6:gender>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:AdScheduleTarget">
            <v6:type>AD_SCHEDULE_TARGET</v6:type>
            <v6:dayOfWeek>SUNDAY</v6:dayOfWeek>
            <v6:startHour>1</v6:startHour>
            <v6:endHour>2</v6:endHour>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:AdScheduleTarget">
            <v6:type>AD_SCHEDULE_TARGET</v6:type>
            <v6:dayOfWeek>SUNDAY</v6:dayOfWeek>
            <v6:startHour>3</v6:startHour>
            <v6:endHour>4</v6:endHour>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:GeoTarget">
            <v6:type>GEO_TARGET</v6:type>
            <v6:targetId>TC-CI-00000102</v6:targetId>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:InterestCategoryTarget">
            <v6:type>INTEREST_CATEGORY</v6:type>
            <v6:targetId>TC-IC-40150150100</v6:targetId>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:SiteCategoryTarget">
            <v6:type>SITE_CATEGORY</v6:type>
            <v6:targetId>TC-SC-10110140100100</v6:targetId>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:SiteRetargetingTarget">
            <v6:type>SITE_RETARGETING</v6:type>
            <v6:targetId>1100000001</v6:targetId>
            <v6:deliverType>INCLUDE</v6:deliverType>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:SearchTarget">
            <v6:type>SEARCH_TARGET</v6:type>
            <v6:targetId>4444444444</v6:targetId>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:GenderTarget">
            <v6:type>GENDER_TARGET</v6:type>
            <v6:gender>ST_MALE</v6:gender>
            <v6:estimateFlg>PAUSED</v6:estimateFlg>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:GenderTarget">
            <v6:type>GENDER_TARGET</v6:type>
            <v6:gender>ST_UNKNOWN</v6:gender>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:AgeTarget">
            <v6:type>AGE_TARGET</v6:type>
            <v6:age>GT_RANGE22_29</v6:age>
            <v6:estimateFlg>ACTIVE</v6:estimateFlg>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:AgeTarget">
            <v6:type>AGE_TARGET</v6:type>
            <v6:age>GT_UNKNOWN</v6:age>
          </v6:target>
        </v6:operand>
        <v6:operand>
          <v6:campaignId>2222222</v6:campaignId>
          <v6:adGroupId>3333333</v6:adGroupId>
          <v6:target xsi:type="v6:PlacementTarget">
            <v6:type>PLACEMENT_TARGET</v6:type>
            <v6:targetId>555555555</v6:targetId>
            <v6:deliverType>WHITE_LIST</v6:deliverType>
          </v6:target>
        </v6:operand>
      </v6:operations>
    </v6:mutate>
  </soapenv:Body>
</soapenv:Envelope>
```
### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTargetReturnValue.md) | mutate/replaceメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupTargetService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>10</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:dayOfWeek>MONDAY</ns1:dayOfWeek>
              <ns1:startHour>10</ns1:startHour>
              <ns1:endHour>20</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GeoTarget">
              <ns1:type>GEO_TARGET</ns1:type>
              <ns1:targetId>TC-CI-00000102</ns1:targetId>
              <ns1:geoNameJa>あああああ</ns1:geoNameJa>
              <ns1:geoNameEn>aaaaaaaa</ns1:geoNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:InterestCategoryTarget">
              <ns1:type>INTEREST_CATEGORY</ns1:type>
              <ns1:targetId>TC-IC-20110160100</ns1:targetId>
              <ns1:categoryFullNameJa>あああああ</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>aaaaaaaa</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:SiteCategoryTarget">
              <ns1:type>SITE_CATEGORY</ns1:type>
              <ns1:targetId>TC-SC-10110110100100</ns1:targetId>
              <ns1:categoryFullNameJa>あああああ</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>aaaaaaaa</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:gender>ST_MALE</ns1:gender>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:age>GT_UNKNOWN</ns1:age>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:PlacementTarget">
              <ns1:type>PLACEMENT_TARGET</ns1:type>
              <ns1:targetId>555555555</ns1:targetId>
              <ns1:placementUrlListName>Sample</ns1:placementUrlListName>
              <ns1:deliverType>WHITE_LIST</ns1:deliverType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:DeviceTarget">
              <ns1:type>DEVICE_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:deviceType>WAP_MOBILE</ns1:deviceType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:bidMultiplier>0.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:CarrierTarget">
              <ns1:type>CARRIER_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:mobileCarrier>SOFTBANK</ns1:mobileCarrier>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:target xsi:type="ns1:AppTarget">
              <ns1:type>APP_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:appType>APP</ns1:appType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:target xsi:type="ns1:OsTarget">
              <ns1:type>OS_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:osType>IOS</ns1:osType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>111111111</ns1:accountId>
            <ns1:campaignId>2222222</ns1:campaignId>
            <ns1:adGroupId>3333333</ns1:adGroupId>
            <ns1:target xsi:type="ns1:OsVersionTarget">
              <ns1:type>OS_VERSION_TARGET</ns1:type>
              <ns1:targetId>1111</ns1:targetId>
              <ns1:osVersion>v4.5</ns1:osVersion>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
### リクエスト
広告グループにおけるターゲティングの設定情報を更新します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupTargetMutateOperation](../data/AdGroupTargetMutateOperation.md) | mutate/replaceメソッドで操作対象となるターゲティング設定情報を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V6">
      <license>1111-1111-1111-1111</license>
      <apiAccountId>2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword>password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutate xmlns:ns2="http://im.yahooapis.jp/V6">
      <ns2:operations>
        <ns2:operator>SET</ns2:operator>
        <ns2:accountId>10000002</ns2:accountId>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
            <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
            <ns2:targetId>as050102</ns2:targetId>
            <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
            <ns2:startHour>1</ns2:startHour>
            <ns2:endHour>2</ns2:endHour>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
            <ns2:type>AGE_TARGET</ns2:type>
            <ns2:targetId>ag0302</ns2:targetId>
            <ns2:age>GT_RANGE12_14</ns2:age>
            <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
            <ns2:type>GENDER_TARGET</ns2:type>
            <ns2:targetId>ge0202</ns2:targetId>
            <ns2:gender>ST_FEMALE</ns2:gender>
            <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
            <ns2:type>GEO_TARGET</ns2:type>
            <ns2:targetId>TC-CI-00000102</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
            <ns2:type>INTEREST_CATEGORY</ns2:type>
            <ns2:targetId>TC-IC-40150150100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
            <ns2:type>SITE_CATEGORY</ns2:type>
            <ns2:targetId>TC-SC-10110140100100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
      </ns2:operations>
    </ns2:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTargetReturnValue.md) | mutate/replaceメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupTargetService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>4.8946</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupTargetReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>as050102</ns1:targetId>
              <ns1:dayOfWeek>FRIDAY</ns1:dayOfWeek>
              <ns1:startHour>1</ns1:startHour>
              <ns1:endHour>2</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>ag0301</ns1:targetId>
              <ns1:age>GT_RANGE12_14</ns1:age>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>ge0201</ns1:targetId>
              <ns1:gender>ST_FEMALE</ns1:gender>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GeoTarget">
              <ns1:type>GEO_TARGET</ns1:type>
              <ns1:targetId>TC-CI-00000102</ns1:targetId>
              <ns1:geoNameJa>岩手県</ns1:geoNameJa>
              <ns1:geoNameEn>iwate_pref</ns1:geoNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:InterestCategoryTarget">
              <ns1:type>INTEREST_CATEGORY</ns1:type>
              <ns1:targetId>TC-IC-40150150100</ns1:targetId>
              <ns1:categoryFullNameJa>消費財 &gt; 美容コスメ &gt; 化粧品 &gt; メイクアップ &gt; ネイル</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>Consumer Packaged Goods &gt; Beauty and Personal Care &gt; Cosmetics &gt; Makeup &gt; Nail</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:SiteCategoryTarget">
              <ns1:type>SITE_CATEGORY</ns1:type>
              <ns1:targetId>TC-SC-10110140100100</ns1:targetId>
              <ns1:categoryFullNameJa>ニュース &gt; 政治</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>News &gt; Politics</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
### リクエスト
広告グループにおけるターゲティングの設定情報を削除します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupTargetMutateOperation](../data/AdGroupTargetMutateOperation.md) | mutate/replaceメソッドで操作対象となるターゲティング設定情報を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V6">
      <license>1111-1111-1111-1111</license>
      <apiAccountId>2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword>password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutate xmlns:ns2="http://im.yahooapis.jp/V6">
      <ns2:operations>
        <ns2:operator>REMOVE</ns2:operator>
        <ns2:accountId>10000002</ns2:accountId>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
            <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
            <ns2:targetId>as050102</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
            <ns2:type>GEO_TARGET</ns2:type>
            <ns2:targetId>TC-CI-00000102</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
            <ns2:type>AGE_TARGET</ns2:type>
            <ns2:targetId>ag0302</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
            <ns2:type>GENDER_TARGET</ns2:type>
            <ns2:targetId>ge0202</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
            <ns2:type>INTEREST_CATEGORY</ns2:type>
            <ns2:targetId>TC-IC-40150150100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>1.1</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
            <ns2:type>SITE_CATEGORY</ns2:type>
            <ns2:targetId>TC-SC-10110140100100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:PlacementTarget">
            <ns2:type>PLACEMENT_TARGET</ns2:type>
            <ns2:targetId>1000031424</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SearchTarget">
            <ns2:type>SEARCH_TARGET</ns2:type>
            <ns2:targetId>1000107465</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>10000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteRetargetingTarget">
            <ns2:type>SITE_RETARGETING</ns2:type>
            <ns2:targetId>1000261610</ns2:targetId>
          </ns2:target>
        </ns2:operand>
      </ns2:operations>
    </ns2:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTargetReturnValue.md) | mutate/replaceメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupTargetService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.4675</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupTargetReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>as050102</ns1:targetId>
              <ns1:dayOfWeek>FRIDAY</ns1:dayOfWeek>
              <ns1:startHour>1</ns1:startHour>
              <ns1:endHour>2</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GeoTarget">
              <ns1:type>GEO_TARGET</ns1:type>
              <ns1:targetId>TC-CI-00000102</ns1:targetId>
              <ns1:geoNameJa>岩手県</ns1:geoNameJa>
              <ns1:geoNameEn>iwate_pref</ns1:geoNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>ag0302</ns1:targetId>
              <ns1:age>GT_RANGE12_14</ns1:age>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>ge0202</ns1:targetId>
              <ns1:gender>ST_FEMALE</ns1:gender>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:InterestCategoryTarget">
              <ns1:type>INTEREST_CATEGORY</ns1:type>
              <ns1:targetId>TC-IC-40150150100</ns1:targetId>
              <ns1:categoryFullNameJa>消費財 &gt; 美容コスメ &gt; 化粧品 &gt; メイクアップ &gt; ネイル</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>Consumer Packaged Goods &gt; Beauty and Personal Care &gt; Cosmetics &gt; Makeup &gt; Nail</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>1.1</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:SiteCategoryTarget">
              <ns1:type>SITE_CATEGORY</ns1:type>
              <ns1:targetId>TC-SC-10110140100100</ns1:targetId>
              <ns1:categoryFullNameJa>ニュース &gt; 政治</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>News &gt; Politics</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:target xsi:type="ns1:PlacementTarget">
              <ns1:type>PLACEMENT_TARGET</ns1:type>
              <ns1:targetId>1000031424</ns1:targetId>
              <ns1:placementUrlListName>c a</ns1:placementUrlListName>
              <ns1:deliverType>WHITE_LIST</ns1:deliverType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:target xsi:type="ns1:SearchTarget">
              <ns1:type>SEARCH_TARGET</ns1:type>
              <ns1:targetId>1000107465</ns1:targetId>
              <ns1:searchKeywordListName>ドラマ</ns1:searchKeywordListName>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:target xsi:type="ns1:SiteRetargetingTarget">
              <ns1:type>SITE_RETARGETING</ns1:type>
              <ns1:targetId>1000261610</ns1:targetId>
              <ns1:targetListName>デフォルトリスト（ IP15OYD5W1 ）</ns1:targetListName>
              <ns1:deliverType>INCLUDE</ns1:deliverType>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## replace
### リクエスト
広告グループにおけるターゲティングの設定情報を置換（削除して追加）します。

| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupTargetOperation](../data/AdGroupTargetOperation.md) | mutate/replaceメソッドで操作対象となるターゲティング設定情報を保持します。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Header>
    <RequestHeader xmlns="http://im.yahooapis.jp/V6">
      <license>1111-1111-1111-1111</license>
      <apiAccountId>2222-2222-2222-2222</apiAccountId>
      <apiAccountPassword>password</apiAccountPassword>
    </RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:replace xmlns:ns2="http://im.yahooapis.jp/V6">
      <ns2:operations>
        <ns2:accountId>10000002</ns2:accountId>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AdScheduleTarget">
            <ns2:type>AD_SCHEDULE_TARGET</ns2:type>
            <ns2:targetId>as050102</ns2:targetId>
            <ns2:dayOfWeek>FRIDAY</ns2:dayOfWeek>
            <ns2:startHour>1</ns2:startHour>
            <ns2:endHour>2</ns2:endHour>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:AgeTarget">
            <ns2:type>AGE_TARGET</ns2:type>
            <ns2:targetId>ag0302</ns2:targetId>
            <ns2:age>GT_RANGE12_14</ns2:age>
            <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GenderTarget">
            <ns2:type>GENDER_TARGET</ns2:type>
            <ns2:targetId>ge0202</ns2:targetId>
            <ns2:gender>ST_FEMALE</ns2:gender>
            <ns2:estimateFlg>ACTIVE</ns2:estimateFlg>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:GeoTarget">
            <ns2:type>GEO_TARGET</ns2:type>
            <ns2:targetId>TC-CI-00000102</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:InterestCategoryTarget">
            <ns2:type>INTEREST_CATEGORY</ns2:type>
            <ns2:targetId>TC-IC-40150150100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
        <ns2:operand>
          <ns2:accountId>10000002</ns2:accountId>
          <ns2:campaignId>20000002</ns2:campaignId>
          <ns2:adGroupId>30000002</ns2:adGroupId>
          <ns2:bidMultiplier>2.0</ns2:bidMultiplier>
          <ns2:target xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns2:SiteCategoryTarget">
            <ns2:type>SITE_CATEGORY</ns2:type>
            <ns2:targetId>TC-SC-10110140100100</ns2:targetId>
          </ns2:target>
        </ns2:operand>
      </ns2:operations>
    </ns2:replace>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
### レスポンス
| パラメータ | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupTargetReturnValue](../data/AdGroupTargetReturnValue.md) | mutate/replaceメソッドの実行結果（全Entityのリスト）を保持します。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V6" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupTargetService</ns1:service>
      <ns1:remainingQuota>-1</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>-1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>4.8946</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:replaceResponse>
      <ns1:rval>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AdScheduleTarget">
              <ns1:type>AD_SCHEDULE_TARGET</ns1:type>
              <ns1:targetId>as050102</ns1:targetId>
              <ns1:dayOfWeek>FRIDAY</ns1:dayOfWeek>
              <ns1:startHour>1</ns1:startHour>
              <ns1:endHour>2</ns1:endHour>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:AgeTarget">
              <ns1:type>AGE_TARGET</ns1:type>
              <ns1:targetId>ag0301</ns1:targetId>
              <ns1:age>GT_RANGE12_14</ns1:age>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GenderTarget">
              <ns1:type>GENDER_TARGET</ns1:type>
              <ns1:targetId>ge0201</ns1:targetId>
              <ns1:gender>ST_FEMALE</ns1:gender>
              <ns1:estimateFlg>ACTIVE</ns1:estimateFlg>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:GeoTarget">
              <ns1:type>GEO_TARGET</ns1:type>
              <ns1:targetId>TC-CI-00000102</ns1:targetId>
              <ns1:geoNameJa>岩手県</ns1:geoNameJa>
              <ns1:geoNameEn>iwate_pref</ns1:geoNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:InterestCategoryTarget">
              <ns1:type>INTEREST_CATEGORY</ns1:type>
              <ns1:targetId>TC-IC-40150150100</ns1:targetId>
              <ns1:categoryFullNameJa>消費財 &gt; 美容コスメ &gt; 化粧品 &gt; メイクアップ &gt; ネイル</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>Consumer Packaged Goods &gt; Beauty and Personal Care &gt; Cosmetics &gt; Makeup &gt; Nail</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupTargetList>
            <ns1:accountId>10000002</ns1:accountId>
            <ns1:campaignId>20000002</ns1:campaignId>
            <ns1:adGroupId>30000002</ns1:adGroupId>
            <ns1:bidMultiplier>2</ns1:bidMultiplier>
            <ns1:target xsi:type="ns1:SiteCategoryTarget">
              <ns1:type>SITE_CATEGORY</ns1:type>
              <ns1:targetId>TC-SC-10110140100100</ns1:targetId>
              <ns1:categoryFullNameJa>ニュース &gt; 政治</ns1:categoryFullNameJa>
              <ns1:categoryFullNameEn>News &gt; Politics</ns1:categoryFullNameEn>
            </ns1:target>
          </ns1:adGroupTargetList>
        </ns1:values>
      </ns1:rval>
    </ns1:replaceResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
