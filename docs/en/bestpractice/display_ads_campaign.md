# Create a campaign by objective on Display Ads (Auction)(V201911 only)


## What is Display Ads (Auction)

Refer to the introduction on [ヤフーのバナー広告「ディスプレイ広告（運用型）」](https://promotionalads.yahoo.co.jp/service/displayads/) (Japanese context only). Currently available for limited users.


## How to create a campaign on YDN API

For creating a campaign, ad group and ads of Display Ads (Auction), following services of YDN API will be used.

- [CampaignService](../api_reference/services/CampaignService.md#campaignservice)
- [AdGroupService](../api_reference/services/AdGroupService.md#adgroupservice)
- [AdGroupAdService](../api_reference/services/AdGroupAdService.md#adgroupadservice)

On creating and updating requests of Display Ads (Auction), some required items of these services are different from the one on YDN.
Follow the steps below to learn about how to create a campaign, ad group and ads of Display Ads (Auction).


## Steps to create a campaign by goal, ad group and ads

### 1. Campaign by goal

When you create a campaign, a goal of the campaign set to achieve a business goal is required.

Since available campaign goals vary by each account, you need to check available campaign goals in advance.

See also [Account object](../api_reference/data/Account/Account.md#account) for more detail.


### 2. Create a campaign by goal

Use "add" of CampaignService.
See also [Campaign object](../api_reference/data/Campaign/Campaign.md#campaign) for more detail of API request specification.

Required items on creating a campaign by goal are as follows.  
※Common items with YDN are omitted.

<table>
<tr><th>Field</th><th>Required?</th><th>Note</th></tr>
<tr><td>campaignGoal</td><td>Required</td><td>Enter a campaign goal from the value acquired on accountAuthorities of AccountService/get</td></tr>
<tr><td>budget.amount</td><td>Required</td><td>Campaign Daily Budget</td></tr>
<tr><td>campaignBiddingStrategy</td><td>Required</td><td>More detail is described on Yahoo! Ads Help "<a href="https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518">入札戦略について (Bidding Strategy)</a>" (Japanese context only).</td></tr>
<tr><td>viewableFrequencyCap</td><td>Optional</td><td>　</td></tr>
</table>

**Note**

Following fields on Campaign object are for YDN campaign only. These are not available for campaigns by goal on Display Ads (Auction). Fixed values on some fields are invalid for campaigns by goal.

<table>
<tr><th>Ignored field</th><th>Note</th></tr>
<tr><td>adProductType</td><td>　</td></tr>
<tr><td>campaignType</td><td>"STANDARD" is set as fixed value</td></tr>
<tr><td>budget.budgetDeliveryMethod</td><td>"STANDARD" is set as fixed value</td></tr>
<tr><td>biddingStrategy</td><td>　</td></tr>
<tr><td>frequencyCap</td><td>　</td></tr>
<tr><td>conversionOptimizer</td><td>"manualCampaignConversionOptimizer" is set as fixed value</td></tr>
</table>


**Request Sample (Standard authentication)**

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


### 3. Create an ad group

Use "add" of AdGroupService.

See also [AdGroup object](../api_reference/data/AdGroup/AdGroup.md#adgroup) for more detail of API request specification.

Required items on creating an ad group in a campaign by goal are as follows.  
※Common items with YDN are omitted.

<table>
<tr><th>Field</th><th>Required?</th><th>Note</th></tr>
<tr><td>adGroupBiddingStrategy</td><td>Optional</td><td>More detail is described on Yahoo! Ads Help "<a href="https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518">入札戦略について (Bidding Strategy)</a>" (Japanese context only).</td></tr>
</table>

**Note**

Following fields on AdGroup object are for YDN ad group only. These are not available for ad group of Display Ads (Auction). Fixed values on some fields are invalid for ad group of Display Ads (Auction).

<table>
<tr><th>Ignored field</th><th>Note</th></tr>
<tr><td>bid</td><td>　</td></tr>
<tr><td>dynamicImageExtensions</td><td>　</td></tr>
<tr><td>smartDeviceCarriers</td><td>　</td></tr>
<tr><td>conversionOptimiser</td><td>"ManualAdGroupConversionOptimizer" is set as fixed value</td></tr>
</table>


**Request Sample (Standard authentication)**

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


### 4. Set Bidding Strategy

When setting a bidding strategy on campaign by goal, specify both of bidding strategy type described on the 'type' field of 'CampaignBiddingStrategy' object and applicable bid field together for request.
※See also [CampaignBiddingStrategy object](../api_reference/data/Campaign/CampaignBiddingStrategy.md#campaignbiddingstrategy) for relation between 'type' field and bid field.

For example, when setting max bid (MAX_CPC), describe the request as follows.

```xml
<ns1:campaignBiddingStrategy>
  <ns1:type>MAX_CPC</ns1:type>
  <ns1:maxCpcBidValue>100</ns1:maxCpcBidValue>
</ns1:campaignBiddingStrategy>
```


**Set Bidding Strategy on Ad Group**

- Bidding strategy set on campaign will be applied to ad groups.  
- When setting a bid by each ad group, the bid will be used as applicable for campaign's bidding strategy.

**Note**

When migrating YDN campaign to campaign by goal, the bid on the campaign can be applied to the migrated campaign but only values applicable for 'type' field will be used on ad delivery.


### 5. Set Targeting

Targeting settings available on campaigns by goal of Display Ads (Auction) are different from YDN campaign.  
See also [AdGroupTarget object](../api_reference/data/AdGroupTarget/AdGroupTarget.md) for more detail of API request specification.


### 6. Create Ads

Use "add" of AdGroupAdService.  
See also [AdGroupAd object](../api_reference/data/AdGroupAd/AdGroupAd.md#adgroupad) for more detail of API request specification.

**Note**

Following fields on AdGroupAd object are for YDN ads only. These are not available for ads of Display Ads (Auction).

<table>
<tr><th>Ignored field</th><th>Note</th></tr>
<tr><td>bid</td><td>　</td></tr>
</table>


**Request Sample (Standard authentication)**

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


## Use Auto-bidding (tCPA)

For campaigns by goal, auto bidding can be set with bidding strategy "tCPA".  
Follow the introduction below for using "tCPA" on campaign or on ad group.

About the availability of tCPA is described on [入札戦略について (Bidding Strategy)](https://ads-help.yahoo.co.jp/yahooads/display/articledetail?lan=ja&aid=51518) (Japanese context only).  
When the campaign can use tCPA, it responds "ENABLE" on `eligibilityFlg` field of `ConversionOptimizer` object.

Following is a sample response and request of each step.

**Response Sample of ConversionOptimizer object**

Sample: Response of `ConversionOptimizer` when the campaign cannot use tCPA.

```xml
<ns3:conversionOptimizerxmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:type="ns3:ManualCampaignConversionOptimizer">
  <ns3:optimizerType>MANUAL</ns3:optimizerType>
</ns3:conversionOptimizer>
```

Sample: Response of `ConversionOptimizer` when the campaign can use tCPA.

```xml
<ns3:conversionOptimizerxmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:type="ns3:ManualCampaignConversionOptimizer">
  <ns3:optimizerType>MANUAL</ns3:optimizerType>
  <ns3:eligibilityFlg>ENABLE</ns3:eligibilityFlg>
</ns3:conversionOptimizer>
```

**Request Sample of tPCA by CampaignBiddingStrategy object**

Sample: Request of tCPA by `CampaignBiddingStrategy` object for campaign.

```xml
<ns1:campaignBiddingStrategy>
  <ns1:type>TARGET_CPA</ns1:type>
  <ns1:targetCpaBidValue>100</ns1:targetCpaBidValue>
</ns1:campaignBiddingStrategy>
```

※Bidding strategy type can be modified only by campaign.
