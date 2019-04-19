# Release Notes
## Release version
V201903 (WSDL version V201903)

## Main Contents of this Release
*Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

### 1. Labeling feature released
Labeling feature in Yahoo! JAPAN Display Ad Network (YDN) became available. Changes on the V201903 release are as follows.

#### ■ Create, Setup, Edit, Delet labels
 * Create, edit, delete labels<br>
 * Setup a label to ad creatives (such as campaign, ad group, ad) and release the label<br>
 * Get label setting information<br>
 * Label report<br>

*This new feature became available on the Campaign Management Tool on February 6, 2019.<br>

##### Target Web Service  
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AdGroupAdLabelService](./api_reference/services/AdGroupAdLabelService.md)
 * [AdGroupLabelService](./api_reference/services/AdGroupLabelService.md)
 * [BulkService](./api_reference/services/BulkService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [CampaignLabelService](./api_reference/services/CampaignLabelService.md)
 * [LabelService](./api_reference/services/LabelService.md)
 * [ReportDefinitionService](./api_reference/services/ReportDefinitionService.md)
 * [ReportService](./api_reference/services/ReportService.md)
 * [StatsService](./api_reference/services/StatsService.md)

### 2. New indexes on report and analytics
Adding new indexes related to ROAS on reports and analytics (statistics), following changes were made on V201903.<br>

* The following new indexes related to ROAS were added in performance data and performance reports.<br>
   * Conv. Value /Cost
   * All Conv. Value /Cost
   * Conv. Value via ad click /Cost

 * The name of the current "Conversion Label Name" on Performance Report was changed to "Conversion Name" after the effective date.It was unified to the same name on the Campaign Management Tool.<br>
   * The value of "Conversion Label Name" was transferred to "Conversion Name".<br>
   * "Conversion Label Name" is deprecated, please confirm and change to "Conversion Name" if you are using the "Conversion Label Name".<br>

* See also the [documentation](./api_reference/appendix/reports) for detail.<br>
* This new feature became available on the Campaign Management Tool on February 6, 2019.<br>

##### Target Web Service   
 * [StatsService](./api_reference/services/StatsService.md)

### 3. Auto-tagging feature released
Auto-tagging feature in Yahoo! JAPAN Display Ad Network (YDN) became available. Auto-tagging "On/Off" is available.<br>
*This new feature became available on the Campaign Management Tool on January 29, 2019.<br>

##### Target Web Service   
 * [AccountService](./api_reference/services/StatsService.md)

### 4. Targeting enhancement
Actual performance of targeting became available on statistics by enhanced targeting feature.<br>
*This new feature became available on the Campaign Management Tool on February 27, 2019.<br>

##### Target Web Service  
 * [StatsService](./api_reference/services/StatsService.md)

### 5. Dynamic ads for display in YDN
Following updates were made on Dynamic ads for display.<br>
 * Create a campaign of Dynamic ads for display
 * Setup data feed to campaign
 * Download editorial results of "Declined" and "Removed" statuses (Max. 100,000 items)

Maximum number of downloadable error information became 100,000 items on the latest version and all available versions.<br>

*This new feature became available on the Campaign Management Tool on February 13, 2019.<br>

#### ※Update on Dynamic Ads for Display feature enhancement (April 18, 2019 released)

* Periodic Upload of Item List file became available<br>
Data feed directly from the Item List file on advertiser’s server by YDN system periodically and update Item List with the feed data.
* Item Set feature became available<br>
"Item Set" supports several filtering items such as category ID, price, ratings are selectable as conditions.Adding the Item set to ad group, ad delivery will become available for various product categories and price zones by each ad group.
* New items on Operation History (for all available versions of YDN API)<br>
Following items (rows) were added to Operation history due to the addition of Item set feature.<br>
　・Item List Name<br>
　・Item List ID<br>
　・Item Set Name<br>
　・Item Set ID<br>

##### Target Web Service 
 * [AdGroupAdService](./api_reference/services/AdGroupAdService.md)
 * [AdGroupService](./api_reference/services/AdGroupService.md)
 * [CampaignService](./api_reference/services/CampaignService.md)
 * [FeedDataService](./api_reference/services/FeedDataService.md)
 * [FeedHolderService](./api_reference/services/FeedHolderService.md)
 * [FeedFtpService](./api_reference/services/FeedFtpService.md)
 * [FeedFtpRequestService](./api_reference/services/FeedFtpRequestService.md)
 * [FeedSetService](./api_reference/services/FeedSetService.md)



## Impact on each version from the change of Services
<table class="standard">
<tbody>
<tr>
<th>Service</th>
<th>V201812 or before</th>
<th>V201903</th>
</tr>
<tr>
<td>BulkService</td>
<td>Campaign label, ad group label and ad label can be specified as EntityTypes on importing template.<br>
</td>
<td>Campaign label, ad group label and ad label can be specified as EntityTypes on importing template.<br>
</td>
</tr>
<tr>
<td>CampaignService</td>
<td>*No change in API IF.<br>
-Ad product information is not returned to campaign of Dynamic ads for display.
</td>
<td>
-Can get label information set to components.<br>
-Can create Dynamic ads for display campaign.<br>
</td>
</tr>
<tr>
<td>AdGroupService</td>
<td>*No change in API IF.<br>
</td>
<td>-Can get label information set to components.<br>
-Can search Item Set ID.<br>
-Can set up Item Set to ad group, and revise/remove Item Set.<br> 
-Change WSDL.<br>   
</td>
</tr>
<tr>
<td>AdGroupAdService</td>
<td>*No change in API IF.<br>
-Cannot get Dynamic Ads for Display.
</td>
<td>
Following operations are available:<br>
-Get labels information<br>
-Create Dynamic ads for display<br>
-Update Dynamic ads for display<br>
-Delete Dynamic ads for display<br>
-Get Dynamic ads for display<br>
</td>
</tr>
<tr>
<td>CampaignLabelService</td>
<td>-<br>
</td>
<td>
Can set a label to campaign, or release the label<br>
</td>
</tr>
<tr>
<td>AdGroupLabelService</td>
<td>-<br>
</td>
<td>Can set a label to ad group, or release the label<br>
</td>
</tr>
<tr>
<td>AdGroupAdLabelService</td>
<td>-<br>
</td>
<td>Can set a label to ad, or release the label
</td>
</tr>
<tr>
<td>LabelService</td>
<td>-<br>
</td>
<td>Following operations are available:<br>
-Create labels<br>
-Setup a label to each entity<br>
-Update label information<br>
-Release label setting<br>
-Delete labels<br>
-Get label information<br>
</td>
</tr>
<tr>
<td>StatsService</td>
<td>*No change in API IF.<br>
</td>
<td>
-Can get items related to ROAS<br>
-Can get actual performance by each target<br>
</td>
</tr>
<tr>
<td>ReportDefinitionService</td>
<td>*No change in API IF.<br>
</td>
<td>
-Can get performance report by each label<br>
-Can get items related to ROAS<br>
</td>
</tr>
<tr>
<td>ReportService</td>
<td>*No change in API IF.<br>
</td>
<td>
-Can get performance report by each label.<br>
-Can get items related to ROAS<br>
</td>
</tr>
<tr>
<td>FeedDataService</td>
<td>Can upload file in ZIP format.<br>
</td>
<td>
Can upload file both in ZIP and TSV format. 
</td>
</tr>
<tr>
<td>FeedFtpService</td>
<td>-</td>
<td>
Can add and update the information of FTP server for Periodic Upload.
</td>
</tr>
<tr>
<td>FeedFtpRequestService</td>
<td>-</td>
<td>
Can request "Upload now" process of Periodic Upload.。
</td>
</tr>
<tr>
<td>FeedSetService</td>
<td>-</td>
<td>
Can create, add and remove Item Set.
</td>
</tr>
<tr>  
<td>FeedHolderService</td>
<td>*No change in API IF.<br>
</td>
<td>
Can get URL for downloading editorial reject reasons.
</td>
</tr>
<tr>
<td>AccountAdProductService</td>
<td>*No change in API IF.<br>
</td>
<td>
"DYNAMIC_ADS" returns.
</td>
</tr>
<tr>
<td>AccountService</td>
<td>*No change in API IF.<br>
</td>
<td>
Can set On/Off of Auto-tagging setting.
</td>
</tr>
</tbody>
</table>


## Sunset Date of YDN API V201809
YDN API V201809 sunset is scheduled as follows.
* Deprecation Date : April 11, 2019 (Thu)
* End of Life Date : July 11, 2019 (Thu)
