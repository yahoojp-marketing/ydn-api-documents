# RuleTargetList
RuleTargetListオブジェクトは、ルール設定のリストを表します。
### Service
+ [RetargetingListService](../services/RetargetingListService.md)

| フィールド | データ型 | 説明 | ADD | SET | REMOVE | 
|---|---|---|---|---|---|
| TargetList(inherited)||||||
| targetListType| enum <a href="./TargetingListType.md">TargetingListType</a>| ターゲットリストの種類です。| Req| Req| — |
| RuleTargetList||||||
| retargetingTagId| xsd: string| サイトリターゲティングのタグIDです。| Req| —| — |
| isPreset| enum <a href="./IsPreset.md">IsPreset</a>| 過去の訪問履歴フラグです| Req| —| — |
| isOpen| enum <a href="./IsOpen.md">IsOpen</a>| ターゲットリストに対してリーチを蓄積するか否かを表すステータスです。| Req| targetListType=RULE：Opt<br>targetListType=DEFAULT_LIST：?| — |
| reachPeriod| xsd:long| クッキーの有効期間です。| Req| Opt| — |
| rules[]| <a href="./Rule.md">Rule</a>| ターゲットリストのルール情報です。| Req| Req| — |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
