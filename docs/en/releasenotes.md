# Release Notes
## Release version　　
5.2 (WSDL version: 5.2.0)

## Type of Version up　　
Minor version up 

## Main Contents of this Release
#### 1. Addition of Carrier Targeting functions
Selecting carrier is added as a targeting feature in ad group level. <br>

* Target Web Service  
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)

* Target Data Object  
 * Please confirm from Data Objects page for more details.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.
 
#### 2. Addition of Site Retargeting tag functions  
Two features are added from Site Retargeting.<br>
　・ Creation of tags<br>
　・ Retrieving the tag details<br>

* Target Web Service  
 * [RetargetingTagService](/docs/en/api_reference/services/RetargetingTagService.md)
  
* Target Data Object  
 * There is no change in Data Object.
  
* Target Enumerations  
 * Please confirm from Data Objects page for more details.

## Impacts on each Version from the change of Services 
<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.1 and before</p></th>
    <th valign="top"><p>Ver.5.2</p></th>
  </tr>
  <tr>
    <td valign="top"><p>AdGroupService</p></td>
    <td valign="top"><p>No change.</p></td>
    <td valign="top"><p>- Mobile carrier field (smartDeviceCarriers) is added in Ad group entity (AdGroup).<br>
    - Enum of device carrier selection (SmartDeviceCarrier) is added.<br>
    - Error added for when device is selected that cannot select the carrier type.</p></td>
  </tr>
  <tr>
    <td valign="top"><p>RetargetingTagService</p></td>
    <td valign="top"><p>No change.<br></p></td>
    <td valign="top"><p>- Tag field (tag) is addeed in Site retargeting tag entity (RetargetingTag).<br>
    - Entity of tag operation (RetargetingTagOperation) and entity of operation results (RetargetingTagReturnValue) are added.</p></td>
  </tr></tbody>
</table>

## Sunset Date of YDN API Ver.4.6 and Ver.4.7
YDN API Ver.4.6 and Ver.4.7 are plan to sunset in December 25, 2015 (JST).
