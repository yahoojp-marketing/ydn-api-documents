# RetargetingTag
RetargetingTagオブジェクトは、サイトリターゲティングのタグ情報を表します。

### Service
+ [RetargetingTagService](../../services/RetargetingTagService.md)

### Namespace
[RetargetingTagService#Namespace](../../services/RetargetingTagService.md#namespace)

| フィールド | データ型 |maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| retargetingTagId| xsd:string|1|1|○|-|-|-| サイトリターゲティングのタグIDです。 |
| accountId| xsd:long|1|1|○|-|-|-| アカウントIDです。 |
| approvalStatus|enum <a href="RetargetingTagApprovalStatus.md">RetargetingTagApprovalStatus</a>|1|0|○|-|-|-|  サイトリターゲティングのステータスです。 |
| tag| xsd:string|1|0|○|-|-|-| サイトリターゲティングのタグ詳細です。 |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
