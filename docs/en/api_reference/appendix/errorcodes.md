# SOAP Error Codes
### Error Process Outline
When a SOAP request is successful, YDN API sends back the "HTTP 200 OK" response code, along with a SOAP response. <br>If an error occurs while a SOAP request is being processed, YDN API sends back a message with an error code. <br>
For details, please refer to [Error](/docs/en/api_reference/data/Common/Error.md) and/or [ErrorDetail](/docs/en/api_reference/data/Common/ErrorDetail.md).<br>

### Sample Error Response

There are 3 types of SOAP error response, SAPFault, Full error and Part error. See the following description about each response.

#### SOAPFault

SOAPFault response returns for WSDL violation, SOAP syntax violation, system error and authentication error.<br>
`<faultcode>` describes an error code, and `<faultstring>` describes an error message.<br>
Detail error are described in `<detail>` in some cases.

The following response is an example of SOAPFault in the case of login failure on [AccountService](/docs/ja/api_reference/services/AccountService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
  <SOAP-ENV:Body>
    <SOAP-ENV:Fault>
      <faultcode>110006</faultcode>
      <faultstring>Can not login for apiAccountId.</faultstring>
      <faultactor/>
      <detail>
        <requestKey>apiAccountId</requestKey>
        <requestValue>xxxx-xxxx-xxxx-xxxx</requestValue>
      </detail>
    </SOAP-ENV:Fault>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

SOAPFault response form depends on API versions. The form above is in case of V201806 version.

#### Full Error

Full Error is returned for the fail of entire request caused by request constraints, etc. It is different from SOAPFault.<br>
Part Error is returned for the request fail caused by constraints in each ‘<operand>’ of SOAP request.

The following response is an example of Full Error in the case of invalid ‘numberResults’ value of `Paging` in [AccountService](/docs/ja/api_reference/services/AccountService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Account" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>AccountService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:getResponse>
      <ns2:error>
        <ns1:code>120003</ns1:code>
        <ns1:message>Invalid number format.</ns1:message>
        <ns1:detail>
          <ns1:requestKey>numberResults</ns1:requestKey>
          <ns1:requestValue>1000000</ns1:requestValue>
        </ns1:detail>
      </ns2:error>
    </ns2:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### Part Error

Part Error is returned in the error case caused by constraints of each element in ‘<operand>’.<br>
Part Error is returned for each ‘<operand>’, whether an error occurred or not.<br>
The error response may contain both of ‘true’ and ‘false’ as value of ‘<operationSucceeded>’, since '<value>' returns for each '<operand>' when you send a single SOAP request which includes multiple ‘<operand>’.

The following response is an example of Part Error in the case of specifying a ‘reportId’ which does not exist in [ReportService](/docs/ja/api_reference/services/ReportService.md).

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://im.yahooapis.jp/V201806" xmlns:ns2="http://im.yahooapis.jp/V201806/Report" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns2:ResponseHeader>
      <ns1:service>ReportService</ns1:service>
      <ns1:timeTakenSeconds>0.1234</ns1:timeTakenSeconds>
      <ns1:requestTime>1234567890</ns1:requestTime>
    </ns2:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns2:mutateResponse>
      <ns2:rval>
        <ns1:ListReturnValue.Type>ReportReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns2:values>
          <ns1:operationSucceeded>false</ns1:operationSucceeded>
          <ns1:error>
            <ns1:code>120022</ns1:code>
            <ns1:message>Deactivated.</ns1:message>
            <ns1:detail>
              <ns1:requestKey>reportId</ns1:requestKey>
              <ns1:requestValue>1234567890</ns1:requestValue>
            </ns1:detail>
          </ns1:error>
        </ns2:values>
      </ns2:rval>
    </ns2:mutateResponse>
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
110004 | Quota exceeded. service = %s , Quota = %s | Quota exceeded.  service = %s , Quota = %s
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
210003 | A function is not permitted this account.| Custom audience is not available for this account. 

##### Service
[AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220016 | Advance setting was made to the product or targeting that is not available.  | The advance setting is only available for the specified product.
220018 | This Target settings is unavailable.  | The type of campaign is not available for the target settings.
220141 | Can not set bidMultiplier. | The bid adjustment rate is not available for the targeting.

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
220143 | Invalid appId.  | Unavailable format of App ID has been set.
220145 | Invalid conversion optimizer. | Conversion optimization setting is not possible using ADD operation. 

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
220133 | Not allowed to set impression beacon url. | Impression beacon URL is not available since the external link to analyzing tool providers is not allowed.
220301 | Over limit to delivered ad. | Number of ads set to be distributed exceeded the limit. 
220302 | Over limit to ad under account. | Number of ads under an account exceeded the limit. 
220321 | Invalid displayUrl. | The display URL is not available for the selected device type on Campaign.
220322 | Invalid tracking parameter. | Invalid string (such as invalid Tracking Parameter, etc.) was found.
220323 | Unavailable tracking parameter for ad. | There is a Tracking Parameter which is not available for the ad product.
220324 | Unavailable tracking parameter for ad. | There is a Tracking Parameter which is not available for the YDN-unaligned tracking tool, or a discontinued Tracking Parameter.

##### Service
[AdGroupService](/docs/en/api_reference/services/AdGroupService.md)

Code           | Message                     | Description                
-------------- | --------------------------- | ---------------------------
220123 | Unavailable conversion optimizer.  | Conversion optimization setting is not possible due to the non-eligible Ad distribution.
220124 | Disable conversion optimizer.  | Target CPA cannot be set, due to the unusable conversion optimization.
220125 | Unavailable the dynamicImageExtensions.  | Cannot set Dynamic Image Extensions, due to the non-eligible Ad distribution.
220132 | Cannot set the carrier type. | Selected device is not available to select the carrier type.
220138 | Unsupported Os Version. | The set OS version is invalid.
220139 | Invalid Os Version. | The OS specified on Mobile App Campaign and the OS version set by targeting do not match.
220140 | Invalid device type. | DeviceType must be SMARTPHONE or TABLET when Campaign type is APP.
220146 | Invalid target cpa value. | Set values more than 1 in the Target CPA when Auto Bidding.
220310 | Over limit to ad group under account. | Number of ad groups under an account exceeded the limit. 

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
220129 | Invalid combination in user status and logo flag. | Unavailable setting between the status flag and logo flag.
220130 | Invalid combination in logo flag and media format. | Unavailable setting between the logo flag and image format.
220131 | Field value is not updatable. | Update has been attempted to the field that cannot be updated.
220135 | Invalid relation in thumbnail flag and media format. | Unavailable setting between the thumbnail flag and image format.

##### Service
[VideoService](/docs/ja/api_reference/services/VideoService.md)

Code           | Message                     | Description                    
-------------- | --------------------------- | ---------------------------
220201 | Creating video downloadUrl is failed. | Creating video downloading URL has failed.
220202 | Invalid video download request. | The URL to download videos is invalid.
220203 | Video download URL has expired. | The URL for downloading videos is expired.
220204 | Creating video uploadUrl is failed. | Creating video uploading URL has failed.
220205 | Invalid video upload request. | The URL for uploading videos is invalid.
220206 | Video upload URL has expired. | The URL for uploading videos is expired.
220207 | Invalid aspect ratio of an video. | Wrong pixel size for video file.
220208 | Duplicate video file. | The specified video file has been already added.
220209 | Video play time is too long (Max 60 seconds). | Play time of the specified video is longer than 60 seconds.
220210 | Video play time is too short (Min 5 seconds). | Play time of the specified video is shorter than 5 seconds.
220211 | Invalid video codec. | Video codec of the specified video file is invalid.
220212 | Invalid audio codec. | Audio codec of the specified video file is invalid.
220213 | Invalid major brand. | Major brand of the video file is invalid.
220214 | Invalid video index. | 'moov atom' has to place on top of the video file.
220215 | Over limit of frame rate. | Frame rate of the video file exceeds the max value.
220216 | Over limit of audio volume. | Audio volume of the video file exceeds the max value.


### Report Process-related Errors
##### Service
[ReportService](/docs/ja/api_reference/services/ReportService.md),[ReportDefinitionService](/docs/ja/api_reference/services/ReportDefinitionService.md)

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
250001 | Invalid combination in Template settings. | Cannot select "custom date" for the period when template flag is set.
250002 | Invalid field settings. | Incorrect combination in report fields is set.
250003 | Invalid combination in report date settings. | Cannot specify a certain date for the timing (interval type) to create a report you specified.
250004 | Invalid combination in date range type. | Cannot select "custom date" for the period you specified.
250005 | Invalid filter`s field. | Specifing the field which cannot be set to the filter.
