# SearchKeywordList
SearchKeywordList object displays the search list.
### Service
+ [SearchKeywordListService](../services/SearchKeywordListService.md)

| Field | Data Type | Description | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| Account ID.| Req| Req| Req |
| searchKeywordListId| xsd:long| Search keyword list ID.| -| Req| Req |
| searchKeywordListName| xsd:string| Name of Search keyword list.| Req| Opt| - |
| searchKeywordListDescription| xsd:string| Description of Search keyword list.| Opt| Opt| - |
| deliveryStatus| enum <a href="./DeliveryStatus.md">DeliveryStatus</a>| Delivery status.| -| -| - |
| searchKeyword[]| <a href="./SearchKeyword.md">SearchKeyword</a>| Search keyword list.| Req| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
