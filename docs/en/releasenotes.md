# Release Notes
## Release version
6.1 (WSDL version: 6.1)

## Type of Version up　　　
Minor version up

## Main Contents of this Release
&lowast;Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations).

#### 1.Bid adjustment rate that is settable per targeting.
Bid adjustment is available to set the rate for each targeting.<br>
Available types of targeting are referable on the following list.

| No | Targeting | Bid adjustment |
|---|---|---|
| 1 | AD_SCHEDULE_TARGET | Available |
| 2 | AGE_TARGET | Available |
| 3 | GENDER_TARGET | Available |
| 4 | GEO_TARGET | Available |
| 5 | INTEREST_CATEGORY | Available |
| 6 | SITE_CATEGORY | Available |
| 7 | SITE_RETARGETING | Not available |
| 8 | SEARCH_TARGET | Not available |
| 9 | PLACEMENT_TARGET | Not available |
| 10 | DEVICE_TARGET<br>(Added by V6.1) | Available |
| 11 | CARRIER_TARGET<br>(Added by V6.1) | Available |
| 12 | APP_TARGET<br>(Added by V6.1) | Not available |
| 13 | OS_TARGET<br>(Added by V6.1) | Not available |
| 14 | OS_VERSION_TARGET<br>(Added by V6.1) | Not available |

##### Target Web Service  
 * [AdGroupService](/docs/ja/api_reference/services/AdGroupService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)

#### 2.	Mobile app campaign
Mobile app campaign are supported to promote mobile apps.<br>
Following functions change by the feature.<br>
‐Targeting functions for mobile apps are added.<br>
‐Counting conversion of app install is available.<br>

##### Target Web Service
 * [CampaignService](/docs/ja/api_reference/services/CampaignService.md)
 * [AdGroupTargetService](/docs/ja/api_reference/services/AdGroupTargetService.md)
 * [AdGroupAdService](/docs/ja/api_reference/services/AdGroupAdService.md)
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [DictionaryService](/docs/ja/api_reference/services/DictionaryService.md)

#### 3.	Improvement of conversion functions
Counting conversions across devices is available.<br>
Counting period of conversions is available to specify from 7 to 90 days by the change above.<br>

##### Target Web Service  
 * [ConversionTrackerService](/docs/ja/api_reference/services/ConversionTrackerService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)

#### 4.	Maintenance Release
Some of Web Services will have maintenance release.<br>
Details of maintenance on each target web service is available on the 'Impacts on each Version from the change of Services'.<br>

##### Target Web Service
 * [ReportService](/docs/ja/api_reference/services/ReportService.md)
 * [DictionaryService](/docs/ja/api_reference/services/DictionaryService.md)
 * [BulkService](/docs/ja/api_reference/services/BulkService.md)
 * [StatsService](/docs/ja/api_reference/services/StatsService.md)

## Impacts on each Version from the change of Services
<table class="standard">
  <tbody>
  <tr>
    <th>Service</th>
    <th>Ver.6.0 and before</th>
    <th>Ver.6.1</th>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>
    No change<br><br>
    The following settings are necessary when create Ad Group.<br>
    ‐device<br>
    ‐deviceApp<br>
    ‐deviceOs<br>
    ‐smartDeviceCarriers
    </p></td>
    <td><p>
    –'deviceOsVersion (OS version)' is added to 'AdGroup'. <br>
    This feature will available to specify OS version to 'AdGroup' on mobile app campaign. <br>
    –Adding error codes
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>
    No change<br><br>
    –Unavailable to get and set Bid adjustment.<br>
    –Targeting operation will run on set method only.<br>
    –Unavailable to get and set new target settings such as 'Device Targeting' and 'OS Version Targeting'.
    </p></td>
    <td><p>
    –Bid adjustment is available to set the rate for each targeting.<br>
    –mutate(add)/mutate(remove)/replace method are added to targeting operation.<br>
    –Following targeting functions are added.<br>
    　‐Device Targeting <br>
    　‐Carrier Targeting <br>
    　‐Web/App Targeting <br>
    　‐OS Targeting <br>
    　‐OS Version Targeting <br>
    –Adding error codes
    </p></td>
  </tr>
  <tr>
    <td><p>CampaignService</p></td>
    <td><p>
    No change<br><br>
    –Unavailable to get, add and set mobile app campaign.
    </p></td>
    <td><p>
    –Available to get, add, set and remove mobile app campaign.<br>
    &lowast;Available to get, add, set and remove following campaign types from Ver.6.1.<br>
    　-Standard Campaign<br>
    　-Mobile App Campaign<br>
    –Adding error codes
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>
    No change<br><br>
    </p></td>
    <td><p>
    No change<br>
    &lowast;Adding error codes
    </p></td>
  </tr>
  <tr>
    <td><p>ConversionTrackerService</p></td>
    <td><p>
    No change<br><br>
    –Unavailable to get and set counting period of conversions. (The period set 30 days only.)<br>
    </p></td>
    <td><p>
    –Counting period of conversions is available to specify from 7 to 90 days.<br>
    –Counting conversion of app install is available.
    </p></td>
  </tr>
  <tr>
    <td><p>DictionaryService</p></td>
    <td><p>
    No change<br><br>
    </p></td>
    <td><p>
    –'getOsVersion' and 'getMediaAdFormat' method are added.<br>
    –Available to specify OS types and OS versions by targeting on mobile app campaign.<br>
    –Available to get OS types and OS versions of mobile apps.<br>
    –Available to get formats of adding creatives.
    </p></td>
  </tr>
  <tr>
    <td><p>ReportService</p></td>
    <td><p>
    No change<br><br>
    'getDownloadUrl' is available.
    </p></td>
    <td><p>
    'getDownloadUrl' is unavailable. (Available to get download URL by get method.)
    </p></td>
  </tr>
  <tr>
    <td><p>BulkService</p></td>
    <td><p>
    –Specifing XML or ZIPPED_XML for output formats is changed to return an invalid error on 'BulkUploadStatusSelector'.<br>
    –'lang' and 'encoding' of 'BulkUploadStatusSelector' become unsupported (ignore).<br>
    –'downloadBulkUploadFileUrl' and 'downloadBulkUploadErrorFileUrl' return the same files.<br>
    (The file downloaded by 'downloadBulkUploadFileUrl' includes error messages.)
    </p></td>
    <td><p>
    –Output formats of 'BulkUploadStatusSelector' are changed as follow.<br>
    　-TSV<br>
    　-CSV<br>
    　-ZIPPED_TSV<br>
    　-ZIPPED_CSV<br>
    　&lowast;XML and ZIPPED_XML are deleted.<br>
    –'lang' and 'encoding' of 'BulkUploadStatusSelector' are deleted.<br>
    –'videoCount' and 'videoErrorCount' are added to 'ProcessingItemsCount'.<br>
    –'uploadBulkJobName' is added to request of 'getUploadUrl'.<br>
    –'downloadBulkUploadErrorFileUrl' is deleted.
    </p></td>
  </tr>
  <tr>
    <td><p>StatsServcie</p></td>
    <td><p>
    No change<br><br>
    Former indexes of conversion are available to get.
    </p></td>
    <td><p>
    –Former and current indexes of conversion are available to get.<br>
    –Current index's values, which include cross device conversion, are available to get.
    </p></td>
  </tr>
</tbody>
</table>

## YDN API Reporting document updates
YDN API Reporting document has been updated. See the followings.
 * [List of Report Fields](/docs/en/api_reference/appendix/reports.md)

## Sunset Date of YDN API Ver.5.4
YDN API Ver.5.4 is planned to sunset on December 21, 2017 (JST).
