# Release Notes
## Release version　　
5.1 (WSDL version: 5.1.0)
## Type of Version up　　
Minor version up 
## Main Contents of this Release
#### 1. Renewal of Report Functions
Renewal of Report Functions

Report Category | Report Types
--------------- | ------------
AD | ・Account Report<br>・Campaign Report<br>・Ad Group Report<br>・Ad report<br>・Destination URL Report
INTEREST_CATEGORY | Interest Category Report
SITE_CATEGORY | Site Category Report
URL | Ad Delivery URL Report
FREQUENCY | Frequency Report

*The date range has changed for the report type below (3 months -> 13 months)<br>
・Account Report<br>
・Campaign Report<br>
・Ad Group Report<br>
・Ad report<br>
・Destination URL Report<br>
・Ad Delivery Report<br>
・Frequency Report<br>
<br>
*Report items are added for the the reports types below:<br>
- Ad Report<br>
　・Prefecture<br>
　・City<br>
　・Gender<br>
　・Age<br>
　・Search Keyword<br>
- Destination URL Report<br>
　・Time<br>
　・Ad Format/Media type<br>
　・Image name<br>
　・Prefecture<br>
　・City<br>
　・Gender<br>
　・Age<br>
　・Search Keyword<br>
　・Conversion Name<br>
　・Objective of Conversion Tracking<br>
<br>
*Limit of additional report definition has changed. (1 -> 30)<br>
<br>
*Sorting request has changed to listing type. (Maximum of 5)<br>

* Target Web Service  
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
 * [ReportService](/docs/en/api_reference/services/ReportService.md)
  
* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.
 
#### 2. Change of Carrier Setting   
Value below has been deleted for carrier setting.<br>
・EMOBILE<br>
・WILLCOM<br>

* Target Web Service  
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
  
* Target Data Object  
 * There is no change in Data Object.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.

#### 3. Impacts on each Version from the change of Services 
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.0 and before</p></th>
    <th valign="top"><p>Ver.5.1</p></th>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupTargetService</p></td>
    <td valign="top"><p>- No change in APIIF</p></td>
    <td valign="top"><p>- APIIF changed<br>
・"ReportType" has changed to "ReportCategory".<br>
・"ReportFrequency" has changed to "ReportIntervalType".<br>
・"ReportFrequencyRange" enumeration has been added.<br>
・"ReportDefinition" has changed to as follows:<br>
　・"frequencyRange" has been added.<br>
　・"sort" has changed to "sortFields[]".<br>
　・Objects below are deleted:<br>
　　・"campaignId"<br>
　　・"reportType"<br>
　　・"segments[]"<br>
　・Items below are available on "fields[]": <br>
　　・"AD_TYPE"<br>
　　・"AD_STYLE"<br>
　　・"MEDIA_AD_FORMAT"<br>
　　・"AD_LAYOUT"<br>
　　・"IMAGE_OPTION"<br>
<br>
- Error messages<br>
・"250001: Invalid combination in Template settings." will return if combination of template flag setting and other setting are not done correctly.<br>
・"250002: Invalid field settings."will return if fields are set correctly.<br>
・"250003: Invalid combination in report date settings." will return if combination of performance report creation timing and other setting are not done correctly.<br>
・"250004：Invalid combination in date range type." will return if combination of report period type setting and other setting are not done correctly.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupAdService</p></td>
    <td valign="top"><p>- No change on APIIF<br></p></td>
    <td valign="top"><p>- APIIF changed
・"ReportClosedDateRecord" has been added.<br>
・Items below are available on "key".<br>
　・FREQ_REPORT_CLOSED_DATE<br>
　・REPORT_CLOSED_DATE</p></td>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupAdService</p></td>
    <td valign="top"><p>- APIIF changed<br>
・Few values cannot be used for carrier setting from September 2015.<br>
　Error will return if the deleted values are used.</p></td>
    <td valign="top"><p>- APIIF changed<br>
・Few values cannot be used for carrier setting.</p></td>
  </tr>
</tbody></table>

## Technical reference
The document with contents of this release is YDN API Ver.5.1.

## WSDL files
If you would like to use the new functions, please download the WSDL from the Download Page.

## Sample program
Sample programs are available from the Download Page.

## Regarding the older version of YDN API
You still can use older version (Ver.5.0 or below) of YDN API.

## Sunset Date of YDN API Ver.4.6
YDN API Ver.4.6 is plan to sunset in December 2015(JST) or later.
