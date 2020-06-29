

# AdGroupTarget

The AdGroupTargets object is a container for storing targeting information specified on ad group.<br/>

**Available targetings for the campaign of Display Ads (YDN) and Display Ads (Auction)**

The available targetings on the campaign by goal of Display Ads (Auction) are different from the campaigns of Display Ads (YDN) as follows.

|             Type of targeting | Display Ads (YDN): campaign | Display Ads (Auction): campaign by goal | Note                                                                                                                                      |
|------------------------------:|:---------------:|:---------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------|
| Day of Week / Hours Targeting |        ○        |                 ○                 |                                                                                                                                           |
|          Geographic Targeting |        ○        |                 ○                 | TC-CI-00000073 is the geo code that shows "Other". It cannot be obtained by getGeographicLocation of DictionaryService, and cannot be specified as geo targeting.     |
|                 Age Targeting |        ○        |                 ○                 |                                                                                                                                           |
|              Gender Targeting |        ○        |                 ○                 |                                                                                                                                           |
|   Interest Category Targeting |        ○        |                 -                 | Unavailable on Display Ads (Auction): campaign by goal.                                                                                          |
|       Site Category Targeting |        ○        |                 ○                 |                                                                                                                                           |
|              Site Retargeting |        ○        |                 ○                 |                                                                                                                                           |
|              Search Targeting |        ○        |                 ○                 |                                                                                                                                           |
|           Placement Targeting |        ○        |                 ○                 |                                                                                                                                           |
|              Device Targeting |        ○        |                 ○                 | Device Targeting is required for "Mobile app campaign" of Display Ads (YDN) and campaign by goal "App promotion" of Display Ads (Auction). <br>And for those campaigns, you have to specify SMARTPHONE or TABLET as target device.       |
|             Carrier Targeting |        ○        |                 -                 | Unavailable on Display Ads (Auction): campaign by goal.                                                                                          |
|             Web/App Targeting |        ○        |                 ○                 |                                                                                                                                           |
|                  OS Targeting |        ○        |                 ○                 | For "Mobile app campaign" of Display Ads (YDN) and campaign by goal "App promotion" of Display Ads (Auction), the OS that you specified for appOs on those campaign is set to OS targeting.         |
|          OS Version Targeting |        ○        |                 ○                 | This targeting type can be specified for "Mobile app campaign" of Display Ads (YDN) and campaign by goal "App promotion" of Display Ads (Auction).             |
|   Audience Category Targeting |        -        |                 ○                 | Unavailable on Display Ads (YDN) :campaign.                                                                                                            |


### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Type</th>
      <th>Description</th>
      <th>response</th>
      <th>add</th>
      <th>set</th>
      <th>remove</th>
      <th>replace</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>accountId</td>
      <td>xsd:long</td>
      <td>Account ID.</td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
    <tr>
      <td>campaignId</td>
      <td>xsd:long</td>
      <td>Campaign ID.</td>
      <td>yes</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
    </tr>
    <tr>
      <td>adGroupId</td>
      <td>xsd:long</td>
      <td>Ad group ID.</td>
      <td>yes</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
      <td>Requirement<br>NotUpdatable</td>
    </tr>
    <tr>
      <td>bidMultiplier</td>
      <td>xsd:double</td>
      <td>Bid adjustment rate.<br>∗If bid adjustment is unable to set targeting, not returned.</td>
      <td>yes</td>
      <td>Optional</td>
      <td>Optional</td>
      <td>Ignore</td>
      <td>Optional</td>
    </tr>
    <tr>
      <td rowspan="3">target</td>
      <td><a href="./Target.md">Target</a><br>
      inherited <a href="./AdScheduleTarget.md">AdScheduleTarget</a><br>
      inherited <a href="./GeoTarget.md">GeoTarget</a><br>
      inherited <a href="./AgeTarget.md">AgeTarget</a><br>
      inherited <a href="./GenderTarget.md">GenderTarget</a><br>
      inherited <a href="./InterestCategoryTarget.md">InterestCategoryTarget</a><br>
      inherited <a href="./SearchTarget.md">SearchTarget</a><br>
      inherited <a href="./SiteCategoryTarget.md">SiteCategoryTarget</a><br>
      inherited <a href="./SiteRetargetingTarget.md">SiteRetargetingTarget</a><br>
      inherited <a href="./PlacementTarget.md">PlacementTarget</a><br>
      inherited <a href="./AudienceCategoryTarget.md">AudienceCategoryTarget</a></td>
      <td rowspan="3">Targeting information of ad group.</td>
      <td>yes</td>
      <td>Requirement</td>
      <td>Requirement</td>
      <td>Requirement</td>
      <td>Requirement</td>
    </tr>
    <tr>
      <td>
      inherited <a href="./DeviceTarget.md">DeviceTarget</a><br>
      inherited <a href="./CarrierTarget.md">CarrierTarget</a><br>
	※
      </td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Requirement</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
    <tr>
      <td>
      inherited <a href="./AppTarget.md">AppTarget</a><br>
      inherited <a href="./OsTarget.md">OsTarget</a><br>
      inherited <a href="./OsVersionTarget.md">OsVersionTarget</a><br>
      </td>
      <td>yes</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
      <td>Ignore</td>
    </tr>
  </tbody>
</table>
*The targetId required on SET will be responded when devices or carriers are set on AdGroup object.<br>

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
