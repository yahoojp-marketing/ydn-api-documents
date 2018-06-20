# Release Notes
## Release version
V201806 (WSDL version V201806)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations).* 

### 1.Change on releasing and numbering new versions

#### (1)Releasing new versions on regular basis

The new version has been released on regular basis as follows.

< Before change >
 * The timing of the release:<br>A new API version was released for every system enhancement
 * Version numbering: <br>VX.X (example: V6.1)

< After the change of V201806 >
 * The timing of the release:<br>Some enhancements in a certain period will be released in bulk<br>
*We will inform the closing of the oldest available version on a new version release.<br>
 * Version numbering: <br>VYYYYMM (example: V201806)

#### (2)Change on version numbering
In order to clear duplicating entities issue because of auto generation in some environment, we made a NameSpace classification and the object architecture change.

*For more detail, please confirm "[Change on version numbering and wsdl configuration](./api_reference/appendix/numbering_new_versions.md)"

### 2. Displaying cost related indicators with numbers under decimal places

The number of cost related indicators up to the third decimal place is calculated and displayed.These reporting fields below are affected with this change.
* cost (cost)
* averageCpc (Avg.CPC)
* avgCpv (Average CPV)

*On the reports created on API V6.1 or before with specifying "ONETIME" (creating a repot once) for 'ReportIntervalType', the cost related indicators are displayed with whole number (integer value). To display the numbers after decimal points, create a new report with ONETIME on V201806.<br>
*On the reports other than "ONETIME" for 'ReportIntervalType', indicators keep displaying with whole number (integer value)  even when created on V201806 or later.

##### Target Web Service  
 * [ReportService](./api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 3. Adding reporting fields related to video views
Following data items related to video views have been added to reports of video ads.

* videoViews (Video Views)
* videoViewsTo3Sec (3-second Video Views)
* paidVideoViews (Paid Video Views)
* paidVideoViewRate (Paid Video View Rate)

Please note that the reporting fields below will not be available for the versions after V201806.<br>
*However, these fields will be continuously supported by V201806, V6.1 or earlier versions. 

* autoVideoPlays (Auto Video Plays)
* clickVideoPlays (Click Video Plays)
* videoPlays (Video Plays)
* videoViewedRate (Video Viewed Rate)<br>

If you are using these items for your report definitions, please check and modify as soon as possible.<br>
For new items see the matrix below.

<table>
<tr><th>Closing item</th><th>To be changed to</th></tr>
<tr><td>autoVideoPlays (Auto Video Plays) </td><td rowspan="2">paidVideoViews (Paid Video Views) </td></tr>
<tr><td>clickVideoPlays (Click Video Plays) </td></tr>
<tr><td>videoPlays (Video Plays) </td><td>videoViews (Video Views) </td></tr>
<tr><td>videoViewedRate (Video Viewed Rate) </td><td>paidVideoViewRate (Paid Video View Rate) </td></tr>
</table>

##### Target Web Service  
 * [StatsService](./api_reference/services/StatsService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 4. Conversion feature enhancement
#### (1) Conversion optimization available at the ad group level
Conversion optimization setting is available at the ad group level in addition to the campaign level.<br>
*For both of campaign and ad group level, 'optimizerType' supports Conversion optimization setting.

#### (2) New setting "Conversion count" in conversion tracking
An option to include or exclude conversion counts can be added when setting up conversion tracking. When you selected 'Conversion count' to include the conversion, that conversion will be counted, which will let you optimize only specific conversion.

#### (3) Adding report fields (applies to all available versions)
With the addition of the 'Conversion counting' setting, the following items were added to the reporting fields.<br>
With the current items, it was not possible to obtain conversions when 'Conversion counting' was set to 'exclude'.<br>
With the newly added items including 'All...' in the names, all conversions can be obtained regardless of your "Conversion count" setting.

* allConv (All Conv.)
* allConvRate (All Conv. Rate)
* costPerAllConv (Cost Per All Conv.)
* allConvValue (All Conv. Value)
* valuePerAllConv (Value Per All Conv.)
* convValue (Conv. Value)
* valuePerConv (Value Per Conv.)
* convValueOld (Conv. Value (old))
* valuePerConvOld (Value / Conversions (old))

#### (4) New counting methods (Many per click/One per click) in conversion tracking
It enables you to select whether the conversion is counted every time or only once when more than one conversions occurred by the same user.<br>
Unique conversions can be obtained by selecting "One per click" (i.e. "Once") to exclude the conversions by the same user after the initial time.

#### (5) Change in the Conversion Tag
One of the Conversion Tags obtained by 'ConversionTrackerService' has been changed. Please confirm the details below.

　　Before :  yahoo_ydn_conv_amount<br> 
　　After  :  yahoo_ydn_conv_value 

*If you have been using a conversion tracking before the effective date, the current tag can be used continuously.

##### Target Web Service
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [ConversionTrackerService](./api_reference/services/ConversionTrackerService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

### 5. System updates
Feature enhancement and some system updates have been made for the following services.<br>
Please confirm the details at the part of 'Impact on each Version from the change of Services' below.<br>

##### Target Web Service  
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)
 * [BulkService](/docs/ja/api_reference/services/BulkService.md)
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)

## Impact on each Version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>Ver.6.1 or before</th>
<th>V201806</th>
</tr>
<tr>
<td>StatsService</td>
<td>
*It can browse Conversion indexes already provided.<br><br>
*Performance data can be obtained by daily basis such as 'Yesterday', 'Today'.<br></td>
<td>
*It can browse all Conversion indexes, already provided and newly added. Following reporting fields were added.<br>
-allConv (All Conv.)<br>
-allConvRate (All Conv. Rate)<br>
-costPerAllConv (Cost Per All Conv.)<br>
-allConvValue (All Conv. Value)<br>
-valuePerAllConv (Value Per All Conv.)<br>
-convValue (Conv. Value)<br>
-valuePerConv (Value Per Conv.)<br>
-convValueOld (Conv. Value (old))<br>
-valuePerConvOld (Value / Conversions (old))<br><br>

*Reporting fields related to video views have been added<br>
-videoViews (Video Views)<br>
-videoViewsTo3Sec (3-second Video Views)<br>
-paidVideoViews (Paid Video Views)<br>
-paidVideoViewRate (Paid Video View Rate)<br><br>

*It displays start/end of performance data as date and time.<br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>
*Conversion optimization setting is unavailable on ad geroup level.</td>
<td>
*Conversion optimization setting is available on ad group level.<br><br>
*Following objects were added.<br>
-AdGroupConversionOptimizer<br>
-AdGroupConversionOptimizerType<br>
-NoneAdGroupConversionOptimizer<br>
-ManualAdGroupConversionOptimizer<br>
-AutoAdGroupConversionOptimizer<br>
-ConversionOptimizerEligibilityFlg<br><br>
*'campaignId' was removed from 'AdGroupOperation'.<br><br>
*Some error codes were added.
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>*Conversion optimization setting with 'targetCpa'.<br>
</td>
<td>
*Conversion optimization setting with 'optimizerType'.<br><br>
*Following objects were added.<br>
-CampaignConversionOptimizer<br>
-CampaignConversionOptimizerType<br>
-ManualCampaignConversionOptimizer<br>
-AutoCampaignConversionOptimizer<br>
-CampaignConversionOptimizerType<br>
-ConversionOptimizerEligibilityFlg<br><br>
*Some error codes were added.
</td>
</tr>
<tr>
<td>ReportService</td>
<td>*No change in API IF.<br></td>
<td>*It displays the numbers of following indicators up to the third decimal place.<br>
-cost (cost)<br>
-averageCpc (Avg. CPC)<br>
-avgCpv (Average CPV)<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>
*Following reporting fields related to conversion were added.<br>
-allConv (All Conv.)<br>
-allConvRate (All Conv. Rate)<br>
-costPerAllConv (Cost Per All Conv.)<br>
-allConvValue (All Conv. Value)<br>
-valuePerAllConv (Value Per All Conv.)<br>
-convValue (Conv. Value)<br>
-valuePerConv (Value Per Conv.)<br>
-convValueOld (Conv. Value (old))<br>
-valuePerConvOld (Value / Conversions (old))<br><br> 
</td>
<td>
*It displays the numbers of following indicators up to the third decimal place.<br>
-cost (cost)<br>
-averageCpc (Avg. CPC)<br>
-avgCpv (Average CPV)<br><br>

*Following reporting fields related to conversion were added.<br>
-allConv (All Conv.)<br>
-allConvRate (All Conv. Rate)<br>
-costPerAllConv (Cost Per All Conv.)<br>
-allConvValue (All Conv. Value)<br>
-valuePerAllConv (Value Per All Conv.)<br>
-convValue (Conv. Value)<br>
-valuePerConv (Value Per Conv.)<br>
-convValueOld (Conv. Value (old))<br>
-valuePerConvOld (Value / Conversions (old))<br><br>

*'displayFieldName' was removed from 'ReportDefinitionField' and folllwing items were added.<br>
-displayFieldNameJA<br>
-displayFieldNameEN<br>
-fieldType<br>
-impossibleCombinationFields<br>
</td>
</tr>
<tr>
<td>BulkService</td>
<td>*No change in API IF.<br></td>
<td>*Setting with other than CAMPAIGN on 'downloadType' was disabled.<br><br>
*'Output' (format) was removed from the search criteria of 'BulkUpload'.<br>
</td>
</tr>
<tr>
<td>ConversionTrackerService</td>
<td>*No change in API IF.<br></td>
<td>*Following items were added to 'ConversionTrackerSelector'.<br>
-countingType<br>
-excludeFromBidding<br><br>

*Following items were added to 'ConversionTrackerPage'.<br>
-totalAllConversions<br>
-totalAllConversionValue<br><br>

*Following items were added to 'ConversionTracker'.<br>
-countingType<br>
-excludeFromBidding<br>
-allConversions<br>
-allConversionValue<br>
</td></tr>
</tbody>
</table>


## Sunset Date of YDN API Ver.6.0
YDN API Ver.6.0.0 sunset is scheduled as follows.
* Deprecation Date : July 20, 2018 (Fri)
* End of Life Date : September 20, 2018 (Mon)
