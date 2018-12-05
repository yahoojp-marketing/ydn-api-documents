# Release Notes
## Release version
V201812 (WSDL version V201812)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

### 1. Tracking video conversions
Tracking the number of conversions occurred other than from ad clicks after viewing video ads for more than 10 seconds in Yahoo!
JAPAN Display Ad Network (YDN) will become available. Changes on the V201812 release are as follows.

#### (1) Change in conversion related indexes on performance data and reports. 
 * The ‘conversion’ definition on conversion related indexes was enhanced.<br>
　Before:<br>
　-Conversions of users who visited the website from ad clicks.<br>
　After:<br>
　-Conversions of users who (a)visited the website from ad clicks or (b)viewed the video ad for more than 10 seconds and then visited the website other than by clicking on the ad.<br>
　(For videos less than 10 seconds, viewing the full ad will be worth viewing 10 seconds.)<br>
 * New indexes<br>
　-Counts of conversions by click on the ad before visiting the website<br>
　-Counts of conversions across devices<br>

#### (2) Adding Video Beacon URL related items
Video Beacon URL related items have been added to AdGroupAdService to track video conversions. Download file of AuditLogService and BulkService has been added also.  <br>
(Adding the item to the download file effects all available API versions)

#### (3) New item to conversion tag setting
"measurementPeriodView" which is an item to set the tracking period from video view to conversion has been added to ConversionTrackerService. The tracking period can be set within 1 - 30 days. The tracking period has been added to the download file of AuditLogService as well.  <br>
(Adding the item to the download file effects all available API versions)

##### Target Web Service  
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AuditLogService](./api_reference/services/AuditLogService.md)
 * [BulkService](./api_reference/services/BulkService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)


### 2. New format (aspect ratio 1:1) in YDN video ads
A new format (aspect ratio 1:1, pixel size 600×600) has been added. No API user interface change.<br>
(This change effects all available API versions)  

##### Target Web Service  
 * [ReportService](./api_reference/services/ReportService.md)


### 3. Search targeting enhancement
Following changes have been made on requests.
 * Specifying keywords and keywordIds became optional. Specifying both at once became unavailable.
 * Increased maximum number of keywords from 100 to 200.
 * A space character (half-width and full-width) became case-insesitive.
 * Following items were added.  
　　- sortField (sort field)  
　　- sortType (sort type)  
　　- matchType (match type)  

And 'releaseDate' (the date keyword added) was added on response.

##### Target Web Service  
 * [SearchKeywordIdeaService](./api_reference/services/SearchKeywordIdeaService.md)


### 4. System updates
Feature enhancement and some system updates have been made for the following services.
Please confirm the details at the part of 'Impact on each version from the change of Services' below.

 * Older reporting items have been removed from ReportDefinitionService and ReportService.
 * "動作区分/Behavior Type" column has been added to the reporting fields on the document.
   "動作区分/Behavior Type" which describes the action of each reporting field has been added.  <br>
 (This change effects all available API versions) 

##### Target Web Service  
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)


## Impact on each version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201809 or before</th>
<th>V201812</th>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>
- Track ad click conversions with following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
</td>
<td>
- Track ad click conversions and viewing video ads for more than 10 seconds with the following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
- Added following new indexes<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
- Added "measurementPeriodView" which set the tracking period from video view to conversion<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>
- Track ad click conversions with the following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
- Shows following reporting items<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
- Track ad click conversions and viewing video ads for more than 10 seconds with the following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
- Added following new indexes<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
- Removed following reporting items<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>- Beacon URL for video view conversions is not supported<br>
</td>
<td>
- Beacon URL for video view conversions is available<br>
- Following beacon URL for video view conversions related items have been added<br>
　- videoStartBeaconUrls<br>
　- isRemoveVideoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- isRemoveVideo3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- isRemoveVideoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
　- isRemoveVideoCompleteBeaconUrls<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>
- Shows following reporting items<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
- Track ad click conversions and viewing video ads for more than 10 seconds with the following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
- Added following new indexes<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
- Removed following reporting items<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>
- Shows following reporting items<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
<td>
- Track ad click conversions and viewing video ads for more than 10 seconds with the following indexes<br>
　- convRate<br>
　- convValue<br>
　- costPerConv<br>
　- valuePerConv<br>
　- allConv<br>
　- allConvRate<br>
　- allConvValue<br>
　- costPerAllConv<br>
　- valuePerAllConv<br>
- Added following new indexes<br>
　- conversionsViaAdClick<br>
　- conversionRateViaAdClick<br>
　- convValueViaAdClick<br>
　- costPerConvViaAdClick<br>
　- valuePerConvViaAdClick<br>
　- crossDeviceConversions<br>
- Removed following reporting items<br>
　- totalConversionsOld<br>
　- totalConversionRateOld<br>
　- convValueOld<br>
　- costTotalConversionsOld<br>
　- valuePerConvOld<br>
　- totalRevenueOld<br>
　- revenueTotalConversionOld<br>
　- revenue<br>
　- revenuePerConv<br>
　- videoViewedRate<br>
　- videoPlays<br>
　- autoVideoPlays<br>
　- clickVideoPlays<br>
</td>
</tr>
<tr>
<td>SearchKeywordIdeaService</td>
<td>
- Specifying both keywords and keywordIds is required<br>
</td>
<td>
- Specifying keywords and keywordIds became optional on request. And the following items became available.<br>
　-searchMatchType<br>
　-sortField<br>
　-sortKey<br>
- releaseDate has been added on response<br>
</td>
</tr>
<tr>
<td>AuditLogService</td>
<td>
　
</td>
<td>
- Following beacon URL for video view conversions related items have been added<br>
　- videoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
</td>
</tr>
<tr>
<td>BulkService</td>
<td>
　
</td>
<td>
- Following beacon URL for video view conversions related items have been added<br>
　- videoStartBeaconUrls<br>
　- video3SecBeaconUrls<br>
　- videoPaidBeaconUrls<br>
　- videoCompleteBeaconUrls<br>
</td>
</tr>
</tbody>
</table>

## Sunset Date of YDN API V201806
YDN API V201806 sunset is scheduled as follows.
* Deprecation Date : January 15, 2019 (Tue)
* End of Life Date : April 15, 2019 (Mon)
