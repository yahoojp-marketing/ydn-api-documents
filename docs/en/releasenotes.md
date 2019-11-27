# Release note
## Release version　　
V201911 (WSDL version: V201911)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

### 1. Reach reports  
“Reach report” became available on the performance report. The number of unique users that have one or more viewable impressions during the specified period will be counted and shown as “Reaches.”

##### Web Service  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 2. Started accepting script tag of script tag providers  
The following companies provide tracking script tag. <br>
　‐ Integral Ad Science Japan KK<br>
　‐ Oracle America, Inc. (former: MOAT)

##### Web Service  
 * [AdGoupAdService](./api_reference/services/AdGroupAdService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)


### 3. Service added to support features of Display Ads (Auction) 
The following features of Display Ads (Auction) became available. <br>

 * Campaign with goals <br>
 * Audience Category Targeting <br> 
 * Converting campaigns created on Yahoo! JAPAN Display Ad Network (YDN) to campaigns on Display Ads (Auction) <br>
 ** Display Ads (Auction) is an ad distribution type provided only for some customers. <br>
 ** BulkService does not support download/upload campaigns of Display Ads (Auction). <br>

##### Web Service  
 * [AccountService](./api_reference/services/AccountService.md)
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [AdGroupTargetService](./api_reference/services/AdGroupTargetService.md)
 * [CampaignMigrationService](./api_reference/services/CampaignMigrationService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 4. Enhancement on Dynamic Ads for Display
Following enhancements were made on Dynamic Ads for Display for YDN. <br>
 * Campaign banner feature
 * Add new items and change/remove some existing items on Item List
 * Item List template change
 * Tracking feature enhancement

More details of these features are available on  “[YDN] Enhancement on YDN Dynamic Ads for Display and Video Ads (https://promotionalads.yahoo.co.jp/support/release/775442.html#article_en)”. <br>
** Dynamic Ads for Display is an ad distribution limited to some advertisers. The release of these enhancements is scheduled December 4, 2019.   

##### Web Service  
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [FeedItemService](./api_reference/services/FeedItemService.md)
 * [FeedSetService](./api_reference/services/FeedSetService.md)
 * [MediaService](./api_reference/services/MediaService.md)


### 5. Maintenance release
- “getColorSet” on DictionaryService became unavailable.

##### Web Service
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 
** The previously informed ”Supports new format of Conversion tag and Site general tag” release was postponed.  Please wait for further announcements regarding details.   


## Impact on each Version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>Before V201907</th>
<th>V2019011</th>
</tr>
<tr>
<td>AccountService</td>
<td>No change in API IF.</td>
<td>
Can get a list of roles for the available campaign goals <br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>No change in API IF.</td>
<td>
- Can set Destination URL (campaign banner) and campaign banner image<br>
- Can set third-party script tag src attribute URL<br>
- Can set each Viewing Beacon URLs (25%, 50%, 75%) <br>
- Can get/add/set ads of Display Ads (Auction) campaigns <br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>No change in API IF.</td>
<td>
Can get/add/set ad groups of Display Ads (Auction) campaigns <br>
</td>
</tr>
<tr>
<td>AdGroupTargetService</td>
<td>No change in API IF.</td>
<td>
Can get/set Audience category for Targeting <br>
</td>
</tr>
<tr>
<td>CampaignMigrationService</td>
<td>-</td>
<td>
- Added as a new service <br>
- Can convert YDN campaigns to Display Ads (Auction) campaigns <br>
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>No change in API IF.</td>
<td>
Can get/add/set Display Ads (Auction) campaigns <br>
</td>
</tr>
<tr>
<td>DictionaryService</td>
<td>No change in API IF.</td>
<td>
- Add a flag of campaign banner image on MediaAdFormat <br>
- Can get geographic location information and Google Product Category available on Item List <br>
- Can get a master data of Audience category <br>
- Can get a domain list of third-party script tag src attribute URL <br>
- getColorSet became unavailable <br>
</td>
</tr>
<tr>
<td>FeedItemService</td>
<td>-<br>
</td>
<td>
- Added as a new service <br>
- Can update Item List information of specified Item ID <br>
</td>
</tr>
<tr>
<td>FeedSetService</td>
<td>No change in API IF.<br>
</td>
<td>
Can use items added to Item List on Item Set <br>
</td>
</tr>
<tr>
<td>MediaService</td>
<td>No change in API IF.<br>
</td>
<td>
Can get/add campaign banner image <br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>No change in API IF.<br>
</td>
<td>
- Can select Reach report <br>
- Can get the latest updated date of Reach report <br>
- Can select Audience category report <br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>No change in API IF.<br>
</td>
<td>
Can get analytics data of Audience category <br>
</td>
</tr>
</tbody>
</table>


## Sunset schedule of YDN API V201903
YDN API V201903 is scheduled to sunset as follows.
* Deprecation Date: December 25, 2019 (Wed) 
* End of Life Date : March 25, 2020 (Wed)
