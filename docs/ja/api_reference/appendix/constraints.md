# 値の制限
各種数値の制限値は下記の通りです。  
### 各サービスの１リクエストとあたりの最大指定（取得）数
Web Service              | Operation            | 操作可能エレメント数 | Max. Responses | Paging
------------------------ | -------------------- | ---------- | -------------- | ------
AccountAdProductService  | get                  | -          | 500            | ○     
AccountService           | get                  | -          | 500            | ○     
||mutate(SET)              | 1                    | -          | -             
AdGroupAdService         | get                  | -          | 500            | ○     
||mutate(ADD)              | 200                  | -          | -             
||mutate(SET)              | 200                  | -          | -             
||mutate(REMOVE)           | 200                  | -          | -             
AdGroupService           | get                  | -          | 500            | ○     
||mutate(ADD)              | 200                  | -          | -             
||mutate(SET)              | 200                  | -          | -             
||mutate(REMOVE)           | 200                  | -          | -             
AdGroupTargetService     | get                  | -          | 500            | ○     
||mutate(SET)              | 20                   | -          | -             
BalanceService           | get                  | -          | 1              | -     
BulkService              | getBulkDownload      | -          | 1              | -     
||getBulkDownloadStatus    | -                    | 500        | ○             
||getUploadUrl             | -                    | 1          | -             
||getBulkUploadStatus      | -                    | 500        | -             
CampaignService          | get                  | -          | 500            | ○     
||mutate(ADD)              | 200                  | -          | -             
||mutate(SET)              | 200                  | -          | -             
||mutate(REMOVE)           | 200                  | -          | -             
ConversionTrackerService | get                  | -        | 1000           | ○     
||mutate(ADD)              | 20                   | -          | -             
||mutate(SET)              | 100                  | -          | -             
DictionaryService        | getDisapprovalReason | -          | 全件             | ○     
||getGeographicLocation    | -                    | 全件         | -             
||getInterestCatgeory      | -                    | 全件         | -             
||getSiteCategory          | -                    | 全件         | -             
||getColorSet              | -                    | 全件         | -             
LocationService          | get                  | -          | 1              | -     
MediaService             | get                  | -          | 500            | ○     
||mutate(ADD)             |  1                    | -          | -             
||mutate(SET)             |  200                  | -          | -             
||mutate(REMOVE)          |  200                  | -          | -             
PlacementUrlIdeaService  | get                  | -          | 500            | ○     
||mutate(ADD)              | 100                  | 100        | -             
||mutate(SET)              | 100                  | -          | -             
||mutate(REMOVE)           | 100                  | -          | -             
ReportDefinitionService  | get                  | -          | 500            | ○     
||getReportFields          | -                    | 1          | -             
||mutate(ADD)              | 1                    | -          | -             
||mutate(SET)              | 1                    | -          | -             
||mutate(REMOVE)           | 1                    | -          | -             
ReportService            | get                  | -          | 500            | ○     
||getClosedDate            | -                    | 1          | -             
||mutate(ADD)              | 20                   | -          | -             
||mutate(REMOVE)           | 20                   | -          | -             
||getDownloadUrl           | -                    | 20         | ○             
RetargetingListService   | get                  | -          | 200            | ○     
||mutate(ADD)              | 20                   | -          | -             
||mutate(SET)              | 20                   | -          | -             
||mutate(REMOVE)           | 20                   | -          | -             
RetargetingTagService    | get                  | -          | 全件             | ○     
SearchKeywordListService | get                  | -          | 500            | ○     
||mutate(ADD)              | 100                  | 100        | -             
||mutate(SET)              | 100                  | -          | -             
||mutate(REMOVE)           | 100                  | -          | -             
