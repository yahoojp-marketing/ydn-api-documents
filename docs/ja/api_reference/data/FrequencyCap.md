# FrequencyCap
Campaignオブジェクトは、キャンペーン情報を表します。
### Service
+ [CampaignService](../services/CampaignService.md)

| フィールド | データ型 | maxOccurs | minOccurs | response | add | set | remove | 説明 | 
|---|---|---|---|---|---|---|---|---|
| level| enum <a href="./FrequencyLevel.md">FrequencyLevel</a>| 1| 0| ○| Opt ※1| Opt ※2| -| フリークエンシー制限の単位（キャンペーンor広告グループor広告）です。 |
| timeUnit| enum <a href="./FrequencyTimeUnit.md">FrequencyTimeUnit</a>| 1| 0| ○| Opt ※1| Opt ※2| -| フリークエンシーの単位時間（日別、週別、月別）です。 |
| impression| long| 1| 0| ○| Opt ※1| Opt ※2| -| 同一ユーザに対する広告の最大インプレッション数です。 |

※1 add時は全ての項目の指定が必須です。<br>
※2 set時は更新する項目のみのリクエストが可能です。<br>
※フリークエンシーキャップの解除方法は、以下の通りです：<br>
```xml
<ns1:frequencyCap>
　　　<ns1:impression>0</ns1:impression>
</ns1:frequencyCap>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
