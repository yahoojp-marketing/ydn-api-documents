# Release Notes
## Release version　　
6.0 (WSDL version: 6.0)

## Type of Version up　　
Major version up 

## Main Contents of this Release
※Target Data Objects and Enumerations are referable on the list of Data Objects (Enumerations). 

#### 1. Addition of Video Ads function
The feature of Video Ads which supports adding video ads creative and aggregating stats of video ads are 
available.
 <br>

Target Web Service  
 * [VideoService](/docs/en/api_reference/services/VideoService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [AdGroupAdService](/docs/en/api_reference/services/AdGroupAdService.md)
 * [CampaignService](/docs/en/api_reference/services/CampaignService.md)
 * [MediaService](/docs/en/api_reference/services/MediaService.md)
 * [StatsService](/docs/en/api_reference/services/StatsService.md)
 * [BulkService](/docs/en/api_reference/services/BulkService.md)

#### 2. Support collaboration with Yahoo! JAPAN DMP  
Creating/editing 'Custom Audience List' on Yahoo! JAPAN DMP are supported.<br>
※Using this feature requires a conclusion of Yahoo! JAPAN DMP contract.
<br>

Target Web Service  
 * [RetargetingListService](/docs/en/api_reference/services/RetargetingListService.md)
  

#### 3. Maintenance Release
Some of Web Services will have maintenance release. <br>
Details of maintenance on each target web service is available on the 'Impacts on each Version from the change of Services'.<br>
   
Target Web Service  
 * [StatsService](/docs/en/api_reference/services/StatsService.md)
 * [AccountAdProductService](/docs/en/api_reference/services/AccountAdProductService.md)
 * [AuditLogService](/docs/en/api_reference/services/AuditLogService.md)
 * [AdGroupTargetService](/docs/en/api_reference/services/AdGroupTargetService.md)
 * [AdGroupService](/docs/en/api_reference/services/AdGroupService.md)
 * [AccountService](/docs/en/api_reference/services/AccountService.md)
 * [ReportDefinitionService](/docs/en/api_reference/services/ReportDefinitionService.md)
  


## Impacts on each Version from the change of Services 

<table class="standard">
  <tbody><tr>
    <th valign="top"><p>Service</p></th>
    <th valign="top"><p>Ver.5.4 and before</p></th>
    <th valign="top"><p>Ver.6.0</p></th>
  </tr>
  <tr>
  <td colspan="3"><b>Addition of Video Ads function</b></td>
</tr>
  <tr>
    <td><p>VideoService</p></td>
    <td><p>Not supported</p></td>
    <td><p>New service<br>
  Following objects are added:<br>
　-VideoSelector (retains search conditions (exec parameters) on get method) <br>
　-VideoOperation (retains campaigns to be operated on mutate method) <br>
　-VideoPage (retains the exec results (list of all Entities) of get method) <br>
　-VideoReturnValue (retains exec results (list of all Entities) of mutate method) <br>
　-VideoValues (retains exec results (1 entity) of get/mutate method)<br>
　-VideoRecord (retains video information) <br>
　-VideoSetting (retains video settings) <br>
　-UploadVideo (retains video information to be uploaded) <br>
　-UploadUrlPage (retains exec results (list of all Entities) of getUploadUrl method) <br>
　-UploadUrlValues (stores URL information where video to be uploaded to) <br>
　-UploadUrlValue (retains URL information where video to be uploaded to) <br>
　Following Enums are added:<br>
　-VideoFileType (video file type) <br>
　-VideoApprovalStatus (editorial review status on video)<br>
　-VideoProcessStatus (process status on video)<br>
　Adding error codes for video ads<br>
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>No change.</p></td>
    <td><p>-'ManualCPVAdGruopAdBid' (object to retain CPV bidding information) is added. <br>
    -'ManualCPVAdGroupBid' is added to inherited on 'bid' of 'AdGroup'. </p></td>
  </tr>
  <tr>
    <td><p>AdGroupAdService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'VideoAd' (video ads object) is added. <br>
    - 'ManualCPVAdGruopAdBid' (object to retain CPV bidding information) is added. <br>
    - 'VideoAd' is added to inherited on 'ad' of 'AdGroup'. <br>
    - 'ManualCPVAdGruopAdBid' is added to inherited on 'bid' of 'AdGroupAd'. </p>
    </td>
  </tr>
  <tr>
    <td><p>CampaignService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'MANUAL_CPV' is added to 'biddingStrategyType'. <br>
    - 'biddingStrategy' of 'Campaign' is changed to 'Ignore' for Add/Set requests. <br>
   </p></td>
  </tr>
  <tr>
    <td><p>MediaService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'ThumbnailFlg' (object of video thumbnail image flag) is added. <br>
    - 'ThumbnailFlg' is added to 'MediaRecord'. <br>
    </p></td>
  </tr>
    <tr>
    <td><p>StatsService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'VIDEO' is added to 'StatsType'. <br>
    - 'MEDIA' of 'StatsType' is changed to 'IMAGE'. <br>
   - Following items which relate to video ads are added to 'Stats'. <br>  
    　-autoVideoPlays (Auto Video Plays)<br>
　-clickVideoPlays (Video click plays)<br>
　-videoViewedRate (Video Viewed Rate, i.e. Video plays/Impressions)<br>
　-averageCpv (average CPV)<br>
　-videoPlays (Total video plays)<br>
　-videoViewsTo25 (Video Views to 25%)<br>
　-videoViewsTo50 (Video Views to 50%)<br>
　-videoViewsTo75 (Video Views to 75%)<br>
　-videoViewsTo95 (Video Views to 95%)<br>
　-videoViewsTo100 (Video Views to 100%)<br>
　-averageRateVideoViewed (The average rate of video played, i.e. Average Duration of Video Viewed/Average longest duration of Video Viewed) <br>
　-averageDurationVideoViewed (Average Duration of Video Viewed(sec))<br>
    </p></td>
  </tr>
 <tr>
    <td><p>BulkService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'VIDEO' is added to 'EntityType'. <br>
    </p></td>
  </tr>
  <tr>
  <td colspan="3"><b>Support Yahoo! JAPAN DMP collaboration</b></td>
</tr>
  <tr>
    <td><p>RetargetingListService</p></td>
    <td><p>Only removing Custom Audience List is available.</p></td>
    <td><p>- 'CustomAudienceTargetList' (object of Target List to use users' visit/activity history from Yahoo! JAPAN DMP) is added.<br>
    - 'targetListTypes' of 'RetargetingListSelector' is changed to '0...5'. <br>
    - 'targetListType' is removed from 'RetargetingListOperation'. <br>
    - 'accountId' is newly added to 'RetargetingList'. <br>
    - 'CustomAudienceTargetList' is added to inherited on 'targetList' of 'RetargetingList'. <br>
    - type of 'reachPeriod' of 'RuleTargetList' is changed to 'int'. <br>
    </p></td>
  </tr>

  <tr>
  <td colspan="3"><b>Maintenance Release</b></td>
</tr>
  <tr>
    <td><p>StatsService</p></td>
    <td><p>No change.</p></td>
    <td><p>- Revised WSDL.<br>
    </p></td>
  </tr>
  <tr>
    <td><p>AdGroupTargetService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'searchKeywordListStatus' is deleted from 'SearchTarget'.  <br>
    'targetListStatus' is deleted from 'SiteRetargetingTarget'. <br>
    - Following Enums are deleted. <br>
    　-TargetListStatus<br>
    　-SearchTargetListStatus<br>
    - Revised WSDL.
    </p></td>
    </tr>
  <tr>
    <td><p>AuditLogService</p></td>
    <td><p>No change.</p></td>
    <td><p>- Revised WSDL.<br>
    </p></td>
  </tr> 
  <tr>
    <td><p>AccountAdProductService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'status' is deleted from 'AdProduct'. <br>
    - 'AdProductStatus' is deleted. </p></td>
  </tr>
  <tr>
    <td><p>AdGroupService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'NONE' is added to 'SmartDeviceCarrier'. </p></td>
  </tr>
  <tr>
    <td><p>AccountService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'CANCELED' is added to 'AccountStatus'. </p></td>
  </tr>
  <tr>
    <td><p>ReportDefinitionService</p></td>
    <td><p>No change.</p></td>
    <td><p>- 'ReportFilter' (object to retain filter definition) is added. <br>
    - 'FilterOperator' (operater to be specified by filter) is added. <br>
    - 'filterable' is added to 'ReportDefinitionField'. <br>
    - 'filters' is added to 'ReportDefinition'.
    </p></td>
  </tr>
</tbody>
</table>

## YDN API Reporting document updates
YDN API Reporting document has been updated. See the followings. 
 * [List of Report Fields](/docs/en/api_reference/appendix/reports.md)

## Sunset Date of YDN API Ver.5.3
YDN API Ver.5.3 is planned to sunset in July 2017 (JST). The date is to be decided.
