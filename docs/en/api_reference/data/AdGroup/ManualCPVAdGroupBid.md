

# ManualCPVAdGroupBid

ManualCPVAdGroupBid object stores the bid amount of ad group (CPV).

※This information is available only when a campaign ID for ad distribution type 'VIDEO_AD' or 'PC_BRAND_PANEL_VIDEO' is specified.
More details are described on [Create Ad Group - Enter the Bid amount of the Ad Group](https://ads-help.yahoo.co.jp/yahooads/ydn/articledetail?lan=en&aid=487).

### Service

+ [AdGroupService](../../services/AdGroupService.md)

### Namespace

[AdGroupService#Namespace](../../services/AdGroupService.md#namespace)

| Field | Type | Description | response | get | add | set | remove |
| ----- | ---- | ----------- | -------- | --------- | --------- | --------- | --------- |
| type | enum <a href="./BiddingStrategyType.md">BiddingStrategyType</a> | Bidding method. | yes | - | Requirement | Requirement<br/>NotUpdatable | Ignore<br/>NotUpdatable | |
| maxCpv | xsd:long | Bid amount | yes | - | Requirement | Requirement<br/>Updatable | Ignore<br/>NotUpdatable | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
