# SearchKeywordList
SearchKeywordListオブジェクトは、サーチリストを表します。
### Service
+ [SearchKeywordListService](../services/SearchKeywordListService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| accountId| xsd:long| アカウントIDです。| Req| Req| Req |
| searchKeywordListId| xsd:long| サーチキーワードリストIDです。| -| Req| Req |
| searchKeywordListName| xsd:string| サーチキーワードリスト名です。| Req| Opt| - |
| searchKeywordListDescription| xsd:string| サーチキーワードリストの説明文です。| Opt| Opt| - |
| deliveryStatus| enum <a href="./DeliveryStatus.md">DeliveryStatus</a>| 配信状況です。| -| -| - |
| searchKeyword[]| <a href="./SearchKeyword.md">SearchKeyword</a>| サーチキーワードリストです。| Req| Opt| - |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
