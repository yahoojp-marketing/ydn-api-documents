# Release Notes
## Release version
V201809 (WSDL version V201809)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

### 1. Site Retargeting enhancement
Site Retargeting feature (RetargetingListService) on Yahoo! JAPAN Display Ad Network (YDN) have an enhancement as below.
#### (1)“Target list size” added to Target list (Similar)
”Target list size" (TargetListSize) which indicates similarity between its original Target list has been added to Target list (Similar). <br>
This enhancement enables to adjust reach by specifying similarity in 10-levels to the original Target list.

#### (2)Targeting feature was added to Target list (Similar) based on App event information
Added “Event type” (EVENT_TYPE) to condition type (RuleType) of Target list, to specify event information (such as app install, purchasing , etc.) within App.<br>
This enhancement will enable you a targeting based on user actions in Apps.
##### Target Web Service  
 * [RetargetingListService](./api_reference/services/RetargetingListService.md)

### 2. Period of performance data available changed
Acquiring performance data (stats information) for the following period is supported.
* Last 13 months (excluding today)
* a specified period
##### Target Web Service 
 * [StatsService](./api_reference/services/StatsService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)

### 3. Video ads to be displayed on Yahoo! JAPAN App (iOS) for tablets supported
Yahoo! JAPAN App (iOS) for tablets has been added to display targets of Video Ads. <br>
'Tablets' is available as Target Device when creating Video ads.<br>
*No change on API Interface.

### 4. Range of Age targeting changed
On YDN Age targeting, the range ‘Age / 12-14’ has been changed to ‘Age / 13-14’. <br>
See more details on “Impact on each Version from the change of Services” below.

##### Target Web Service
 * [AdGroupTargetService](./api_reference/services/AdGroupTargetService.md)
 * [ReportService](./api_reference/services/ReportService.md)

### 5. System updates
Feature enhancement and some system updates have been made for the following services.<br>
Please confirm the details at the part of 'Impact on each Version from the change of Services' below.<br>
 * Reviewed and modified some error codes structure.<br>
 See more details on “Error code structure”.
 * Creating a definition of scheduled performance reports has been disabled on ReportDefinitionService. <br>
 Referring values on performance reports created on V201806 or older are available.
 * Date and time format of acquired performance data has been changed on StatsService and ConversionTrackerService.

##### Target Web Service  
 * All services (error codes changes)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 
## Impact on each Version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>Ver.201806 or before</th>
<th>V201809</th>
</tr>
<tr>
<td>RetargetingListService</td>
<td>
* Get/Set Target List size is not available on Target List (Similar)<br><br>
* Get/Set Event type is not available on Target List (Rule)<br>
</td>
<td>
* Get/Set Target List size in 10 ranges are available on Target List (Similar)<br>
* Get/Set Event type is available on Target List (Rule)<br>
Following items were added to SimilarityTargetLis.<br>
-TargetListSize<br>
-TargetListSizeReaches<br>
* Added EVENT_TYPE to RuleType<br>
* Added followings to objects<br>
-TargetListSize<br>
-TargetListSizeReaches<br>
<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>
* Period of acquiring stats information does not support the last 13 months and a specified period.<br>
- Date and time of Stats process completion is described in the following format:<br>
YYYYMMDDHHmmss<br>
</td>
<td>
* Period of acquiring stats information supports the last 13 months and a specified period.<br>
- Date and time of Stats process start and completion are described in the following format:<br>
YYYYMMDDHHmmss<br><br>
* Following items added to StatsPeriod<br>
- DEFINITE_VALUE_LAST13MONTH<br>
- CUSTOM_DATE<br><br>
* Added statsPeriodCustomDate to StatsSelector<br>
* Added followings to objects<br>
- PeriodDatetime<br>
- StatsPeriodCustomDate<br>
</td>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>* Period of acquiring stats information does not support the last 13 months and a specified period.<br>
</td>
<td>
* Period of acquiring stats information supports the last 13 months and a specified period.<br>
* Date and time of Stats process start and completion are described in the following format:<br>
YYYYMMDDHHmmss
<br><br>
* Added statsPeriodCustomDate to ConversionTrackerSelector<br>
* Added period to ConversionTrackerPage<br>
* Following items added to StatsPeriod<br>
- DEFINITE_VALUE_LAST13MONTH<br>
- CUSTOM_DATE<br><br>
* Added followings to objects<br>
- Period<br>
- PeriodDatetime<br>
- StatsPeriodCustomDate<br><br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>* Although age ranges on Age Targeting report are displayed as ‘Age / 6-11’ and ‘Age 12-14’, data reported after September 2018 will include data of ranges ‘Age / 6-12’ and ‘Age 13-14’.<br></td>
<td>* Age ranges on Age Targeting report were changed to ‘Age / 6-12’ and ‘Age /13-14’.<br><br>
When the performance data of September 2018 and earlier includes a data categorized to‘Age / 6-11’ and ‘Age / 12-14’, they will be summarized to ‘Age / 6-12’ and ‘Age / 13-14’.
</td>
</tr>
<tr>
<td>AdGroupTargetService</td>
<td>
* When setting ‘Age / 12-14’ (GT_RANGE12_14) on Age targeting, actual ad delivery target will be ‘Age / 13-14’. ‘Age / 13-14’ (GT_RANGE13_14) is not available 
</td>
<td>
* Age targeting supports ‘Age / 13-14’ (GT_RANGE13_14)‘Age / 12-14’ (GT_RANGE12-14) is not available<br>
- Added GT_RANGE13_14 to Age
<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>* Following items are not recommended to be used for scheduled reports.<br>
- intervalType<br>
- addTemplate<br>
<br></td>
<td>* Following items entered for scheduled reports are ignored, get is only available.<br>
- intervalType<br>
- addTemplate<br>
<br>
</td>
</tr>
</tbody>
</table>


## Sunset Date of YDN API Ver.6.1.0
YDN API Ver.6.1.0 sunset is scheduled as follows.
* Deprecation Date : October 19, 2018 (Fri)
* End of Life Date : January 18, 2019 (Fri)
