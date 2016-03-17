# SOAP Error Codes

### Error Process Outline
When a SOAP request is successful, YDN API sends back the "HTTP 200 OK" response code, along with a SOAP response. <br>
If an error occurs while a SOAP request is being processed, YDN API sends back a message with an error code. <br>
For details, please refer to [Error](/docs/en/api_reference/data/Error.md) and/or [ErrorDetail](/docs/en/api_reference/data/ErrorDetail.md).<br>

##### Response Sample
```xml
<SOAP-ENV:Envelopexmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>         
      <SOAP-ENV:Fault>             
         <faultcode>faultCode</faultcode>             
         <faultstring>faultString</faultstring>             
         <faultactor></faultactor>             
         <detail>                 
            <requestKey>detail/requestKey</requestKey>                 
            <requestValue>detail/requestValue</requestValue>             
         </detail>         
      </SOAP-ENV:Fault>     
   </SOAP-ENV:Body> 
</SOAP-ENV:Envelope>
```
### Error Code
The following list provides SOAP error codes and error content displayed when an error or problem occurs.  

#### General Errors
##### Service
Same for all services: 

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
110001 | Invalid Request.  | Invalid Request.  
110002 | Frequency limit exceeded. Please try your request again later.  | Frequency limit exceeded. Please try your request again later.  
110003 | Invalid location.  | Invalid location.  
110005 | Not a valid id.  | Not a valid id.  
110006 | Can not login for %s.  | Cannot login for %s.  
110007 | Invalid method.  | Invalid method.  
110008 | Invalid selector.  | Invalid selector.  
110009 | Invalid operations.  | Invalid operations.  
110010 | Invalid operator.  | Invalid operator.  
119999 | An internal error has occurred.  | An internal error has occurred.  
120001 | Required.  | Required.  
120002 | Invalid value.  | Invalid value.  
120003 | Invalid number format.  | Invalid number format.  
120004 | Invalid string format.  | Invalid string format.  
120005 | Invalid date format.  | Invalid date format.  
120006 | Invalid enum.  | Enumeration item value is undefined.  
120007 | Invalid step value.  | Invalid step value.  
120008 | Invalid url format.  | Invalid url format.  
120009 | Invalid email format.  | Invalid email format.  
120010 | Too many items.  | Too many items.  
120011 | Too little items.  | Too few items.  
120012 | Too many values.  | Too many values.  
120013 | Too little values.  | Too few values.  
120014 | Too long values.  | Value(s) are too long.  
120015 | Too short value.  | Value(s) are too short.  
120016 | Too large value.  | Value(s) are too large.  
120017 | Too small value.  | Value(s) are too small.  
120018 | Duplicate values.  | Value(s) are duplicated.  
120019 | Can not set empty.  | Item cannot be set while empty.  
120020 | Can not set value.  | Value cannot be set.  
120021 | Insufficient search parameters.  | Insufficient search parameters.  
120022 | Deactivated.  | Not active.  
120023 | Over limit.  | Over limit.  
120024 | Invalid relation.  | Invalid relationship.
120025 | Out of range.  | Out of range.
120026 | Status error.  | Status error.
120029 | This value is registered.  | This value is registered.

#### Submission-related Errors
##### Service
[RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
210001 | Selected value is not approved to update.  | The selected elements is not approved to use for the updates of target list.
210002 | Cannot update from the dependency.  | Due to the dependency relations, updateis not possible.

##### Service
[AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220016 | Advance setting was made to the product or targeting that is not available.  | The advance setting is only available for the specified product.
220018 | This Target settings is unavailable.  | The type of campaign is not available for the target settings.

##### Service
[BulkService](/docs/en/api_reference/services/BulkService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220001 | Over limit of uncompleted bulk download job.  | The registration limit of uncompleted bulk download jobs has been exceeded.
220002 | Over limit of bulk download job.  | The registration limit of bulk download jobs has been exceeded.
220003 | Creating bulk downloadUrl is failed.  | Creation of bulk download URL failed.
220004 | Bulk download URL has expired.  | Bulk download URL has expired.
220005 | Invalid bulk download request.  | The bulk download URL is illegal.
220019 | Another job is in progress.  | It is running another job.

##### Service
[CampaignService](/docs/en/api_reference/services/CampaignService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220007 | Unavailable the adProductType.  | adProductType specified is not available. 
220014 | Budget is lower than bidding price.  | The bidding price has been set higher than the budget.
220121 | Frequency setting was made to the product that is not available.  | You can not set frequency ads instruments designated.
220122 | Unavailable combination of frequency settings.  | Combination of frequency setting is invalid.
220123 | Unavailable conversion optimizer.  | Conversion optimization setting is not possible due to the non-eligible Ad distribution.
220124 | Disable conversion optimizer.  | Target CPA cannot be set, due to the unusable conversion optimization.

##### Service
[AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220006 | Unavailable value.  | A value which cannot be used has been entered.
220008 | Under examination.  | Review in progress of edited data.
220009 | Ad type you chose does not support the specified adProductType.  | Ad type you chose does not support the specified adProductType.
220010 | Can not specify APP and OS for the device type.  | APP and OS you specified does not support for the device type.
220015 | Bidding price is higher than campaign budget.  | The bidding price has been set higher than the campaign budget. 
220113 | Unsupported ad product type.  | Delivery method of campaign (AdproductType) cannot relate to media.
220114 | Invalid ad style.  | Invalid ad style.
220115 | Unavailable aspect ratio of an image. | The pixel size is not available to use for the specific image.
220126 | Invalid pattern in ad type and layout. | Unavailable match setting between the ad type and ad layout.
220127 | Invalid ad type. | Setting is only available for Responsive Ad or Static Frame Ad.
220128 | Invalid color set ID. | Unavailable Color Set ID has been set.

##### Service
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
  
Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220125 | Unavailable the dynamicImageExtensions.  | Cannot set Dynamic Image Extensions, due to the non-eligible Ad distribution.
220132 | Cannot set the carrier type. | Selected device is not available to select the carrier type.

##### Service
[MediaService](/docs/en/api_reference/services/MediaService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220102 | Over limit of file size.  | It exceeds the file size limit.
220103 | Unsupported filename extension.  | The image file is not GIF/JPEG.
220104 | Only GIF89a is supported.  | GIF file is not in GIF89a.
220105 | Animated GIF pixel size does not fit.  | The following file could not be registered, because the file size did not fit the pixel size of the animated GIF format.
220106 | Only RGB is supported.  | Color space of image file is not in the RGB.
220107 | Invalid aspect ratio of an image.  | Image file of the ads is not in supportive size.
220108 | A function is not permitted this account.  | A function is not permitted this account.
220109 | Duplicate image file.  | Image file is already created.
220110 | Creating media downloadUrl is failed.  | Creating media file download failed.
220111 | Media download URL has expired.  | Media file download URL has expired.
220112 | Invalid media download request.  | Invalid media file download request.
220116 | Unsupported file format.  | Image file format is not supported.
220117 | Inifinite loop setting is not allowed for Animated GIF.  | Inifinate loop has been set for animated GIF ads.
220118 | Animated GIF movie time is too long (Max 15 seconds).  | Animation has been set longer than 15 seconds.
220119 | Submitted file is transparent GIF.  | Image file is transparent GIF.
220120 | Submitted file is 0 byte.  | Image file is 0byte.
22129 | Invalid combination in user status and logo flag. | Unavailable setting between the status flag and logo flag.
22130 | Invalid combination in logo flag and media format. | Unavailable setting between the logo flag and image format.
22131 | Field value is not updatable. | Update has been attempted to the field that cannot be updated.

### Report Process-related Errors
##### Service
[ReportService](/docs/en/api_reference/services/ReportService.md), [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
240001 | Over limit of uncompleted report download job.  | The registration limit of uncompleted report download jobs has been exceeded.
240002 | Over limit of report download job.  | The registration limit of report download jobs has been exceeded.
240003 | Invalid division specified.  | Invalid division specified.
240004 | Invalid segment match pattern.  | Invalid segment match pattern.
240005 | Invalid field item.  | Invalid field item.
240006 | Invalid sort item.  | Invalid sort item.
240007 | Creating report downloadUrl is failed.  | Creation of report download URL failed.
240008 | Report download URL has expired.  | Report download URL has expired.
240009 | Invalid report download request.  | The report download URL is illegal. 
240010 | Over limit of report template number.  | The number of registeration template is over the limit number. 
240011 | Custom date is unavailable when is set as template.  | Cannot select “custom date” for the period when template flag is set.
240012 | Field item was not set properly on the specified report type.  | Field item value as a mandatory report the specified type is not set.
240013 | Sort setting was made to the field that is not specified.  | items that are not specified in the field is set to sort.
