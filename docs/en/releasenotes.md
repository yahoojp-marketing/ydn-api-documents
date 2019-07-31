# Release note
## Release version　　
V201907 (WSDL version: V201907)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

### 1. Enhancement on Dynamic Ads for Display
As Dynamic Ads for Display enhancement, following features became available on uploading Item list file.

 * Debug mode became available.<br>
 * Detail information such like uploading route, error information, etc, became available on file uploading.<br>
 * Status about periodic upload was added.<br>

##### Web Service  
 * [FeedDataService](./api_reference/services/FeedDataService.md)

### 2. Aspect ratio for images and videos
Adding images and videos by their aspect ratio became available. <br>
On getMediaAdFormat of "DictionaryService", acquiring a flag for aspect ratio compatibility, actual number of aspect ratio, maximum file size, etc. became available. <br>

##### Web Service  
 * [DictionaryService](./api_reference/services/DictionaryService.md)
 * [MediaService](./api_reference/services/MediaService.md)
 * [VideoService](./api_reference/services/VideoService.md)

### 3. PC Brand Panel
Following changes were made in order to support ad distribution "PC Brand Panel." <br>

 * CampaignService (all available versions) :<br>
　This service supports get, add, update, and delete campaigns for "PC Brand Panel (Static Image)" and "PC Brand Panel (Video)".<br>
 * AdGroupAdService :<br>
　This service supports create, get, update, and delete Banner ad (video).
　* "PC Brand Panel" is available for specific advertisers. <br>
<br>

##### Web Service
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)


### 4. Measurement indexes
Measurement indexes used on Performance Report and Analytics were added and changed. <br>

#### Measurement change
The following indexes were changed to client-side measurement. <br>
* Impressions <br>
* CTR <br>
　** The data before June 30, 2019 will not be available. <br>
　** The server-side measurement data can be checked with the indexes "Impressions (previous)" and "CTR (previous)". <br>

#### Definition change
The definition of average CPV changed. <br>
 * Before : "view cost÷the number of paid video views" <br>
 * After : "view cost÷10 sec video views" <br>
　** "10 sec video views" is same with "the number of paid video views". <br><br>

#### Counting method change  * all available versions
The method of counting Viewable impressions changed as follows. This is applied only to viewable impressions which occurs after the effective date. <br>
 * Before :
Viewable impressions is counted on the day when the ad is displayed.<br>
 * After : 
Viewable impressions is counted on the day when the ad becomes viewable (the ad is displayed in viewer’s recognition range).<br><br>

#### New indexes
The following indexes were added to YDN API. <br>
<table>
<tr><th>JA / EN</th><th>Field names of Performance Report</th><th>Field names of Analytics</th><th>description</th></tr> 
<tr><td>インプレッション数（旧）/<br>Impressions (previous)</td><td>IMPS_PREV</td><td>impsPrev</td><td>Impressions by server side measurement. <br>
Check the number of impressions before June 30, 2019 with this index. </td></tr>
<tr><td>クリック率（旧）/<br>CTR (previous)</td><td>CLICK_RATE_PREV</td><td>clickRatePrev</td><td>Click through rate by server-side measurement. <br>
Check the number of impressions before June 30, 2019 with this index. </td></tr>
<tr><td>メジャードインプレッション数 /<br>Measured impressions</td><td>MEASURED_IMPS</td><td>measuredImps</td><td>Impressions that can count viewable impressions by client-side measurement.</td></tr>
<tr><td>メジャードインプレッション測定率 /<br>Measured impressions rate</td><td>MEASURED_IMPS_RATE</td><td>measuredImpsRate</td><td>Measurement rate of measured impressions to impressions by client-side measurement. </td></tr>
<tr><td>ビューアブルインプレッション率 /<br>Viewable impressions rate</td><td>VIEWABLE_IMPS_RATE</td><td>viewableImpsRate</td><td>Impression rate that can count viewable impressions by client-side measurement. </td></tr>
<tr><td>ビューアブルクリック数 /<br>Viewable clicks</td><td>VIEWABLE_CLICK</td><td>viewableClicks</td><td>Clicks for viewable impressions by client-side measurement. </td></tr>
<tr><td>ビューアブルクリック率 /<br>Viewable click rate</td><td>VIEWABLE_CLICK_RATE</td><td>viewableClickRate</td><td>CTR for viewable impressions by client-side measurement. </td></tr>
<tr><td>動画の10秒再生数 /<br>10 sec video views</td><td>VIDEO_VIEWS_TO_10_SEC</td><td>videoViewsTo10Sec</td><td>Number of video views for 10 seconds or more. <br>** The value is same to charged video views. </td></tr>
</table>

##### Web Service  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [StatsService](./api_reference/services/StatsService.md)

### 5. Changes on names related to some AdType

Due to renaming YDN ad types, some Enum names and Entity names were changed as follows. <br>
These changes were applied to the import template and operation history on all available YDN API versions. Both previous and new names will be supported when importing with the template. <br>
** For setting AdType with reporting filter on V201907, the setting has to be made with the changed AdType name. <br>

<table>
<tr><th>Enum name (before)</th><th>Entity name (before)</th><th>Enum name (after)</th><th>Entity name (after)</th></tr> 
<tr><td>RESPONSIVE_AD</td><td>ResponsiveAd</td><td>RESPONSIVE_IMAGE_AD</td><td>ResponsiveImageAd</td></tr>
<tr><td>VIDEO_AD</td><td>VideoAd</td><td>RESPONSIVE_VIDEO_AD</td><td>ResponsiveVideoAd</td></tr>
<tr><td>NONE</td><td>None</td><td>BANNER_IMAGE_AD</td><td>BannerImageAd</td></tr>
</table>

##### Web Service
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [StatsService](./api_reference/services/StatsService.md)


### 6. Uploading animated GIF sunsets
"Animation" field has been removed from getMediaAdFormat of DictionaryService due to the sunset of uploading animated GIF. <br>

##### Web Service
 * [DictionaryService](./api_reference/services/DictionaryService.md)


### 7. Changes on names of feature and index
Some feature name and index names were changed. [Learn more](https://promotionalads.yahoo.co.jp/support/release/677944.html#article_en) <br>
Following Stats services were renamed as follows due to this change. <br>
 * totalClickCost　→　cost 
 * avgClickCost　→　avgCpc

##### Web Service
 * [StatsService](./api_reference/services/StatsService.md)


### 8. Maintenance release
#### Report service integration
ReportService was integrated with ReportDefinitionService. <br>
The report definition and report job will be created with ReportDefinitionService after the release. Learn about details on the following document. <br>

 * [Reference](./api_reference/services/ReportDefinitionService.md)<br>
 * [Best Practice](./bestpractice/ydn_report.md)<br>

#### Discontinuation of periodic reports (all available versions)
For periodic reports created on and before V201806, intervalType was changed to ONETIME. After this change, all periodic reports do not run. <br>

#### LocationService sunset<br>
LocationService has been closed.


##### Web Service
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * LocationService *Closed on V201907
 * ReportService *Closed on V201907


## Impact on each Version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>Before V201903</th>
<th>V201907</th>
</tr>
<tr>
<td>FeedDataService</td>
<td>No change in API IF.<br>
</td>
<td>- Debug mode is available on getUploadUrl<br>
- getUploadStatus can acquire the file uploading route, error rate, completion date and status added for periodic upload.<br>
</td>
</tr>
<tr>
<td>DictionaryService</td>
<td>No change in API IF</td>
<td>
- Cannot get animation and id field<br>
- Can get information for Aspect ratio 
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>Create, update, get, delete campaigns of PC Brand Panel</td>
<td>
- Create, update, get, delete campaigns of PC Brand Panel<br>
- Can create, update, get and delete BannerVideoAd (Banner (video) ads).<br>
- Can get renamed Enum name and renamed Entity name<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>No change in API IF</td>
<td>Can get new index and renamed old index on client-side measurement.
</td>
</tr>

<tr>
<td>ReportDefinitionService</td>
<td>No change in API IF</td>
<td>- Can get new index and renamed old index on client side measurement.<br>
- Can create report definition and job entry at the same time
</td>
</tr>
<tr>
<td>ReportService</td>
<td>No change in API IF</td>
<td>Not available</td>
</tr>
<tr>
<td>LocationService</td>
<td>Same location returns uniformly (without effecting to existing users) </td>
<td>Not available</td>
</tr>

<tbody>
</table>


## Sunset schedule of YDN API V201812
YDN API V201812 is scheduled to sunset as follows.
* Deprecation Date : September 2, 2019 (Mon)
* End of Life Date : December 2, 2019 (Mon)
