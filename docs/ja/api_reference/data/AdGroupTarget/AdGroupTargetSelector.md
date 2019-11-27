

# AdGroupTargetSelector

AdGroupTargetSelectorオブジェクトは、getメソッドの検索条件（実行パラメータ）を保持します。

### Service

+ [AdGroupTargetService](../../services/AdGroupTargetService.md)

### Namespace

[AdGroupTargetService#Namespace](../../services/AdGroupTargetService.md#namespace)

| Field | Type | Description | response | get |
| ----- | ---- | ----------- | -------- | --------- |
| accountId | xsd:long | アカウントIDです。 | yes | Requirement | |
| campaignIds[0..1000] | xsd:long | キャンペーンIDです。 | yes | Optional | |
| adGroupIds[0..1000] | xsd:long | 広告グループIDです。 | yes | Optional | |
| targetTypes[0..7] | enum [TargetType](./TargetType.md) | ターゲティング種別です。 | yes | Optional | |
| paging | [Paging](../Common/Paging.md) | データの取得範囲です。 | yes | Optional | |

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
