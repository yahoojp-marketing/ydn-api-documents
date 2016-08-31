# Release Notes
## Release version　　
5.4 (WSDL version: 5.4.0)

## Type of Version up　　
Minor version up 

## Main Contents of this Release
#### 1. Addition of Search Targeting function
The feature of Search Target List which specifies the duration
of search keyword and also specifies the number of searches will
be available.
 <br>

* Target Web Service  
 * [SearchKeywordIdeaService](/docs/en/api_reference/services/SearchKeywordIdeaService.md)
 * [SearchKeywordListService](/docs/en/api_reference/services/SearchKeywordListService.md)

* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.
 
#### 2. Addition of Download Operation History data function  
Impression Beacon URL will be added as one of setting item of Ad.
It allows you to aggregate Impressions data using Impression Beacon
URL via analytics tools provided by vendors.<br>

* Target Web Service  
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
  
* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.

#### 3. Addition of Rule type of Site Retargeting function
Some of Web Services will have maintenance release. <br>
Details of maintenance on each target web service is available on the 'Impacts on each Version from the change of Services'.<br>
   
* Target Web Service  
 * [AccountService](/docs/en/api_reference/services/AccountService.md)
 * [AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md)
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
  
* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.

## Impacts on each Version from the change of Services 
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.3 and before</p></th>
    <th valign="top"><p>Ver.5.4</p></th>
  </tr>
  <tr>
    <td><p>SearchKeywordIdeaService</p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Added following items on "SearchKeywordIdeaSelector".<br>
    　- Duration of Search Keywords (searchKeywordRecency)<br>
    　- Number of Search times of Search Keywords (searchKeywordFrequency)<br>
    Added following Enum items.<br>
    　- Duration of Search Keywords (KeywordRecency)<br>
    　- Number of Search times of Search Keywords (KeywordFrequency)</p></td>
  </tr>
  <tr>
    <td><p>SearchKeywordListService</p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Added following items on "SearchKeywordList".<br>
    　- Duration of Search Keywords (searchKeywordRecency)<br>
    　- Number of Search times of Search Keywords (searchKeywordFrequency)<br>
    Removed following items on "SearchKeyword"<br>
    　- Search Keywords (searchKeyword)<br>
    　- Number of PC user's search volume (desktopSearchVolume)<br>
    　- Number of Smartphone user's search volume (smartPhoneSearchVolume)<br>
    　- Number of Tablet user's search volume (tabletSearchVolume)<br>
    Added following Enum items.<br>
    　- Duration of Search Keywords (KeywordRecency)<br>
    　- NUmber of Search times of Search Keywords (KeywordFrequency)</p></td>
    　</tr>
  <tr>
    <td><p>AdGroupAdService </p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Added following items on "AdGroupAd" which stores ad information<br>
    　- Impression Beacon URL (impressionBeaconUrls)<br>
    　- Impression Beacon URL remove flag (isRemoveBeaconUrls)<br>
    Added following Enum items.<br>
    　- Remove flag (isRemoveFlg)</p></td>
  </tr>
  <tr>
    <td><p>AccountService</p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Changed following items for service suspended status on Enum of "AccountStatus".<br>
    　- PENDING → SUSPENDED</p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Changed following data object names.<br>
     - AdGroupTargetList → AdGroupTargets<br>
     - TargetList → AdGroupTargetList</p></td>
  </tr>
  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>- No change.</p></td>
    <td><p>
    Changed following data object name.<br>
    - TargetList → RetargetingTargetList</p></td>
  </tr>
</tbody>
</table>


## Sunset Date of YDN API Ver.5.1
YDN API Ver.5.1 is plan to sunset in September 15, 2016 (JST).
