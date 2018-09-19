# エラーコードの再編について

## 概要
エラーコードの構成上の問題点を改善するために、エラーコードの再編を実施しました。

### 1．従来のエラーコードの問題点
#### 問題点1：冗長なエラーコード/メッセージが存在する
* エラーメッセージの内容は同じだが、UpperCase、LowerCaseの違いでエラーコードが異なる
* エラーが発生するServiceが異なるためにエラーコードが分かれている
* 仕様追加・変更に伴い使用されなくなったエラーコードが存在している

#### 問題点2：API利用者がエラー補足しづらい
エラーコードが細分化され、補足すべきエラーコードが多すぎる状況  
例：形式不正エラーの項目で「INVALID STRING FORMAT」、「INVALID NUMBER FORMAT」、「INVALID DATE FORMAT」が存在する


### 2．エラーコードの構成を見直し

* サービス共通のエラー項目をカテゴリに分類して、エラーコードを統一しました。
<table class="standard">
<tbody>
<tr>
<th>パターン</th>
<th>カテゴリ</th>
<th>エラーコード</th>
<th>エラーメッセージ</th>
<th>説明</th>
</tr>
<tr>
 <td valign="top" rowspan=2>1</td>
 <td valign="top" rowspan=2>形式不正</td>
 <td valign="top">F0001</td>
 <td valign="top">Invalid format.</td>
 <td valign="top">日付、数値、文字列の形式が不正です。</td>
</tr>
<tr>
 <td valign="top">F0002</td>
 <td valign="top">Invalid file format.</td>
 <td valign="top">アップロードファイルの形式が不正です。</td>
</tr>
<tr>
 <td valign="top">2</td>
 <td valign="top">必須</td>
 <td valign="top">R0001</td>
 <td valign="top">Require.</td>
 <td valign="top">必須項目が未指定です。</td>
</tr>
<tr>
 <td valign="top" rowspan=3>3</td>
 <td valign="top" rowspan=3>値不正</td>
 <td valign="top">V0001</td>
 <td valign="top">Invalid value.</td>
 <td valign="top">文字、日付、数値、ENUMで許可していない値です。</td>
</tr>
<tr>
 <td valign="top">V0002</td>
 <td valign="top">Empty file</td>
 <td valign="top">アップロードファイルサイズが0バイトです。</td>
</tr>
<tr>
 <td valign="top">V0003</td>
 <td valign="top">Over limit of the file</td>
 <td valign="top">アップロードファイルサイズが上限を超過しています。</td>
</tr>
<tr>
 <td valign="top" rowspan=2>4</td>
 <td valign="top" rowspan=2>配列不正</td>
 <td valign="top">L0001</td>
 <td valign="top">Lower list size.</td>
 <td valign="top">配列の要素数が下限値を下回っています。</td>
</tr>
<tr>
 <td valign="top">L0002</td>
 <td valign="top">Over list size.</td>
 <td valign="top">配列の要素数が上限値を超過しています。</td>
</tr>
<tr>
 <td valign="top" rowspan=2>5</td>
 <td valign="top" rowspan=2>URL</td>
 <td valign="top">L0001</td>
 <td valign="top">Url has expired.</td>
 <td valign="top">アップロードURL、またはダウンロードURLの有効期限が切れています。</td>
</tr>
<tr>
 <td valign="top">U0002</td>
 <td valign="top">Invalid url.</td>
 <td valign="top">アップロードURL、またはダウンロードURLが利用できない状態です<br>（URLが改ざんされているなど）。</td>
</tr>
<tr>
 <td valign="top">6</td>
 <td valign="top">ステータス不正</td>
 <td valign="top">S0001</td>
 <td valign="top">Invalid Status.</td>
 <td valign="top">無効なステータスです。変更または削除できません。</td>
</tr>
<tr>
 <td valign="top">7</td>
 <td valign="top">存在しないID</td>
 <td valign="top">I0001</td>
 <td valign="top">Deactivated Id.</td>
 <td valign="top">削除されているEntityのID、または存在しないIDが指定されています。</td>
</tr>
<tr>
 <td valign="top">8</td>
 <td valign="top">重複</td>
 <td valign="top">D0001</td>
 <td valign="top">Duplicate.</td>
 <td valign="top">・Entityを一意に識別する項目が重複しています。<br>
・すでに登録済みの名称と重複しています。<br>
・リクエストで指定したoperand内で名称が重複しています。</td>
</tr>
<tr>
 <td valign="top">9</td>
 <td valign="top">関連不正</td>
 <td valign="top">RL001</td>
 <td valign="top">Invalid relation.</td>
 <td valign="top">リクエストで指定する項目の関連性が矛盾しています<br> （開始＞終了の日付指定を行なっているなど）。</td>
</tr>
<tr>
 <td valign="top">10</td>
 <td valign="top">上限超過</td>
 <td valign="top">LT001</td>
 <td valign="top">Over limit.</td>
 <td valign="top">登録できるEntityの上限数を超過しています。</td>
</tr>
</table>

* サービス別のエラーコードについて、エラーメッセージが同一の場合のエラーコードを統合しました。
<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
<th>削除</th>
<th>統合先エラーコード</th>
</tr>
<tr>
 <td valign="top">210003</td>
 <td valign="top">A function is not permitted this account.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">220108</td>
 <td valign="top">Function is not permitted this account.</td>
 <td valign="top">○</td>
 <td valign="top">210003</td>
</tr>
<tr>
 <td valign="top">119999</td>
 <td valign="top">An internal error has occurred.</td>
 <td valign="top"></td>
 <td valign="top"></td>
</tr>
<tr>
 <td valign="top">220003</td>
 <td valign="top">Creating bulk downloadUrl is failed.</td>
 <td valign="top">○</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220110</td>
 <td valign="top">Creating media downloadUrl is failed.</td>
 <td valign="top">○</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">240007</td>
 <td valign="top">Creating report downloadUrl is failed.</td>
 <td valign="top">○</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220201</td>
 <td valign="top">Creating video downloadUrl was failed.</td>
 <td valign="top">○</td>
 <td valign="top">119999</td>
</tr>
<tr>
 <td valign="top">220204</td>
 <td valign="top">Creating video uploadUrl was failed.</td>
 <td valign="top">○</td>
 <td valign="top">119999</td>
</tr>
</table>


### 3．無効なエラーコードを削除
現在使用していない以下のエラーコードを削除しました。
<table class="standard">
<tbody>
<tr>
<th>エラーコード</th>
<th>エラーメッセージ</th>
</tr>
<tr>
 <td valign="top">110004</td>
 <td valign="top">Quota exceeded. service = %s , Quota = %s</td>
</tr>
<tr>
 <td valign="top">120021</td>
 <td valign="top">Insufficient search parameters.</td>
</tr>
<tr>
 <td valign="top">220001</td>
 <td valign="top">Over limit of uncompleted bulk download job.</td>
</tr>
<tr>
 <td valign="top">220002</td>
 <td valign="top">Over limit of bulk download job.</td>
</tr>
</table>

## エラーコード統廃合の状況一覧
エラーコードの統廃合状況一覧は以下のファイルをダウンロードしてご確認ください。<br>
[エラーコード統廃合（YDN API）](https://s.yimg.jp/images/promotionalads_edit/support/pdf/api_doc/error_codes_structure_YDN_ja.pdf)
