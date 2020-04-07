# ディスプレイ広告（運用型）で目的別キャンペーンを入稿する（V201911のみ）


## ディスプレイ広告（運用型）とは

[ヤフーのバナー広告「ディスプレイ広告（運用型）」](https://promotionalads.yahoo.co.jp/service/displayads/)をご参照ください。現在は一部のお客様のみご利用になれます。


## YDN APIでの入稿方法

YDN APIでは、ディスプレイ広告（運用型）（以下、運用型と表記）のキャンペーン（以下、目的別キャンペーンと表記）や広告グループ、広告の作成に、以下のサービスを利用します。

- [CampaignService](../api_reference/services/CampaignService.md#campaignservice)
- [AdGroupService](../api_reference/services/AdGroupService.md#adgroupservice)
- [AdGroupAdService](../api_reference/services/AdGroupAdService.md#adgroupadservice)

利用するサービスはディスプレイ広告（YDN）（以下、YDNと表記）と同様ですが、作成リクエストや更新リクエストで必要となる項目が、YDNとは異なります。
ここでは運用型のキャンペーンや広告グループ、広告を作成する手順について、詳しく説明します。


## 目的別キャンペーン、広告グループ、広告を作成する手順

### 1. 目的別キャンペーンとは

目的別キャンペーンを作成する際には、広告出稿の目的（以下、キャンペーン目的と表記）を指定する必要があります。

また、アカウント毎に利用可能なキャンペーン目的が異なるため、事前に利用可能なキャンペーン目的を`AccountService/get`で確認する必要があります。

詳細は[Accountオブジェクト](../api_reference/data/Account/Account.md#account)を参照してください。


### 2. 目的別キャンペーンを作成する

CampaignServiceのaddを利用します。
リクエストのAPI仕様については、[Campaignオブジェクト](../api_reference/data/Campaign/Campaign.md#campaign)を参照してください。

目的別キャンペーンの作成で必要となる項目は、以下のとおりです。  
※YDNと共通する項目は省略しています。

<table>
<tr><th>フィールド</th><th>要不要</th><th>補足</th></tr>
<tr><td>campaignGoal</td><td>必須</td><td>AccountService/getのaccountAuthoritiesで取得した値から、設定する目的を入力</td></tr>
<tr><td>budget.amount</td><td>必須</td><td>1日の予算</td></tr>
<tr><td>campaignBiddingStrategy</td><td>必須</td><td>詳細はYahoo!広告ヘルプ「<a href="https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518">入札戦略について</a>」を参照してください。</td></tr>
<tr><td>viewableFrequencyCap</td><td>任意</td><td>　</td></tr>
</table>

**注意事項**

Campaignオブジェクトにおける以下のフィールドは、YDNで作成したキャンペーン専用です。目的別キャンペーンでは設定できません。フィールドによっては固定値が設定されていますが、目的別キャンペーンでは無効な値になります。

<table>
<tr><th>無効化されるフィールド</th><th>補足</th></tr>
<tr><td>adProductType</td><td>　</td></tr>
<tr><td>campaignType</td><td>「STANDARD」が固定値として設定</td></tr>
<tr><td>budget.budgetDeliveryMethod</td><td>「STANDARD」が固定値として設定</td></tr>
<tr><td>biddingStrategy</td><td>　</td></tr>
<tr><td>frequencyCap</td><td>　</td></tr>
<tr><td>conversionOptimizer</td><td>「manualCampaignConversionOptimizer」が固定値として設定</td></tr>
</table>


**＜リクエストサンプル＞（標準認証）**

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201911/Campaign" xmlns:ns2="http://im.yahooapis.jp/V201911">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1001326677</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>1001326677</ns1:accountId>
          <ns1:campaignName>campaign_add_test_1581666807828</ns1:campaignName>
          <ns1:userStatus>PAUSED</ns1:userStatus>
          <ns1:startDate>20210101</ns1:startDate>
          <ns1:endDate>20230101</ns1:endDate>
          <ns1:budget>
            <ns1:amount>100</ns1:amount>
          </ns1:budget>
          <ns1:campaignGoal>WEBSITE_TRAFFIC</ns1:campaignGoal>
          <ns1:campaignBiddingStrategy>
            <ns1:type>MAX_CPC</ns1:type>
            <ns1:maxCpcBidValue>100</ns1:maxCpcBidValue>
          </ns1:campaignBiddingStrategy>
          <ns1:viewableFrequencyCap>
            <ns1:level>CAMPAIGN</ns1:level>
            <ns1:timeUnit>DAY</ns1:timeUnit>
            <ns1:vImps>1</ns1:vImps>
          </ns1:viewableFrequencyCap>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>    
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


### 3. 広告グループを作成する

AdGroupServiceのaddを利用します。

リクエストのAPI仕様については、[AdGroupオブジェクト](../api_reference/data/AdGroup/AdGroup.md#adgroup)を参照してください。

目的別キャンペーン配下の広告グループ作成に必要な項目は、以下のとおりです。  
※YDNと共通する項目は省略しています。

<table>
<tr><th>フィールド</th><th>要不要</th><th>補足</th></tr>
<tr><td>adGroupBiddingStrategy</td><td>任意</td><td>詳細はYahoo!広告ヘルプ<a href="https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518">入札戦略について</a>を参照してください。</td></tr>
</table>

**注意事項**

AdGroupオブジェクトの以下のフィールドは、YDNで作成した広告グループ専用です。運用型の広告グループでは設定できません。フィールドによっては固定値が設定されていますが、運用型の広告グループでは無効な値になります。

<table>
<tr><th>無効化されるフィールド</th><th>補足</th></tr>
<tr><td>bid</td><td>　</td></tr>
<tr><td>dynamicImageExtensions</td><td>　</td></tr>
<tr><td>smartDeviceCarriers</td><td>　</td></tr>
<tr><td>conversionOptimiser</td><td>「ManualAdGroupConversionOptimizer」が固定値として設定</td></tr>
</table>


**＜リクエストサンプル＞（標準認証）**

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201911/AdGroup" xmlns:ns2="http://im.yahooapis.jp/V201911">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1001326677</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>1001326677</ns1:accountId>
          <ns1:campaignId>26923311</ns1:campaignId>
          <ns1:adGroupName>adgroup_add_1581667045308</ns1:adGroupName>
          <ns1:userStatus>PAUSED</ns1:userStatus>
          <ns1:device>NONE</ns1:device>
          <ns1:deviceApp>NONE</ns1:deviceApp>
          <ns1:deviceOs>NONE</ns1:deviceOs>
          <ns1:adGroupBiddingStrategy>
            <ns1:maxCpcBidValue>50</ns1:maxCpcBidValue>
          </ns1:adGroupBiddingStrategy>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>    
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


### 4. 入札戦略を設定する

目的別キャンペーンで入札戦略を設定するには、`CampaignBiddingStrategy`オブジェクトの`type`フィールドで示される入札戦略のタイプと、対応する入札価格のフィールドを同時に指定してリクエストします。  
※`type`フィールドと入札価格のフィールドの関係は、[CampaignBiddingStrategyオブジェクト](../api_reference/data/Campaign/CampaignBiddingStrategy.md#campaignbiddingstrategy)を参照してください。

例えば、最大入札価格（MAX_CPC）を設定する場合、以下のようにリクエストします。

```xml
<ns1:campaignBiddingStrategy>
  <ns1:type>MAX_CPC</ns1:type>
  <ns1:maxCpcBidValue>100</ns1:maxCpcBidValue>
</ns1:campaignBiddingStrategy>
```


**広告グループで入札戦略を設定するには**

- 広告グループでは、キャンペーンの入札戦略が引き継がれます。  
- 広告グループ単位で入札価格を設定する場合は、キャンペーンの入札戦略に対応した入札価格として利用されます。

**注意事項**

YDNで作成したキャンペーンを目的別キャンペーンに変換した場合、過去に設定した入札価格はそのまま保持されますが、`type`フィールドに対応する値のみが配信に利用されます。


### 5. ターゲティングを設定する

YDNのキャンペーンと目的別キャンペーンでは、設定できるターゲティングが異なります。  
詳細は、[AdGroupTargetオブジェクト](../api_reference/data/AdGroupTarget/AdGroupTarget.md)を参照してください。


### 6. 広告を作成する

AdGroupAdServiceのaddを利用します。  
リクエストのAPI仕様については、[AdGroupAdオブジェクト](../api_reference/data/AdGroupAd/AdGroupAd.md#adgroupad)をご参照ください。

**注意事項**

AdGroupAdオブジェクトの以下のフィールドは、YDNで作成した広告専用です。運用型の広告では設定できません。

<table>
<tr><th>無効化されるフィールド</th><th>補足</th></tr>
<tr><td>bid</td><td>　</td></tr>
</table>


**＜リクエストサンプル＞（標準認証）**

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201911/AdGroupAd" xmlns:ns2="http://im.yahooapis.jp/V201911">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns2:license>1111-1111-1111-1111</ns2:license>
      <ns2:apiAccountId>2222-2222-2222-2222</ns2:apiAccountId>
      <ns2:apiAccountPassword>password</ns2:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>1001326677</ns1:accountId>
        <ns1:operand>
          <ns1:accountId>1001326677</ns1:accountId>
          <ns1:campaignId>26923311</ns1:campaignId>
          <ns1:adGroupId>209011481</ns1:adGroupId>
          <ns1:adName>ad_add_1581667335407</ns1:adName>
          <ns1:userStatus>PAUSED</ns1:userStatus>
          <ns1:ad xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:TextAd">
            <ns1:type>TEXT_LONG_AD1</ns1:type>
            <ns1:url>https://www.yahoo.co.jp</ns1:url>
            <ns1:displayUrl>www.yahoo.co.jp</ns1:displayUrl>
            <ns1:headline>headline</ns1:headline>
            <ns1:description>description</ns1:description>
            <ns1:description2>description2</ns1:description2>
          </ns1:ad>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>    
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


## 自動入札（目標単価指定）を利用する

目的別キャンペーンでは、自動入札を入札戦略「目標単価指定（tCPA）」で設定します。  
ここでは、キャンペーン、または広告グループで目標単価指定（tCPA）を利用する方法をご紹介します。

目標単価指定（tCPA）の利用可否については[入札戦略について](https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518)を参照してください。  
対象のキャンペーンが条件を満たしている場合は、`ConversionOptimizer`オブジェクトの`eligibilityFlg`フィールドが`ENABLE`で返却されます。

以下は、各ステップにおけるレスポンスおよびリクエストの例です。

**ConversionOptimizerオブジェクトのレスポンス例**

キャンペーンが目標単価指定（tCPA）を利用できない場合の`ConversionOptimizer`のレスポンス例です。

```xml
<ns3:conversionOptimizerxmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:type="ns3:ManualCampaignConversionOptimizer">
  <ns3:optimizerType>MANUAL</ns3:optimizerType>
</ns3:conversionOptimizer>
```

目標単価指定（tCPA）を利用できる場合の`ConversionOptimizer`のレスポンス例です。

```xml
<ns3:conversionOptimizerxmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:type="ns3:ManualCampaignConversionOptimizer">
  <ns3:optimizerType>MANUAL</ns3:optimizerType>
  <ns3:eligibilityFlg>ENABLE</ns3:eligibilityFlg>
</ns3:conversionOptimizer>
```

**CampaignBiddingStrategyオブジェクトによる目標単価指定（tCPA）のリクエスト例**

キャンペーンの`CampaignBiddingStrategy`オブジェクトによる目標単価指定（tCPA）のリクエスト例です。

```xml
<ns1:campaignBiddingStrategy>
  <ns1:type>TARGET_CPA</ns1:type>
  <ns1:targetCpaBidValue>100</ns1:targetCpaBidValue>
</ns1:campaignBiddingStrategy>
```

※入札戦略タイプは、キャンペーンのみで変更が可能です。
