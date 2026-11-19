# サンプルデータ

## 配置先

`売上データ_研修用.xlsx` を次の場所へコピーします。

```text
C:\PowerBITraining\Excel\売上データ_研修用.xlsx
```

短縮版に同梱されている次のファイルを使用します。

```text
C:\PowerBITraining\Fallback\商品マスター.xlsx
C:\PowerBITraining\Fallback\店舗マスター.xlsx
C:\PowerBITraining\Fallback\販売目標.xlsx
```

SQL Serverを準備する場合は `SQLServer` フォルダー、SharePointリストを準備する場合は `SharePoint` フォルダーのファイルを使用します。

## 売上データ_研修用.xlsx

| 項目 | 内容 |
|---|---|
| シート名 | `売上データ` |
| Excelテーブル名 | `SalesTrainingTable` |
| 対象期間 | 2025年7月1日〜2026年6月30日 |
| 整形前 | 7,615行 |
| 整形後 | 7,612行 |

演習02のため、次の状態を意図的に含めています。

- 不要な `メモ` 列
- `商品カテゴリ` の前後空白と中間空白
- `店舗ID` が空白の行
- `売上金額` が負の行
- `売上明細ID` が重複する行

これらは誤りを当てる問題ではありません。手順書に従ってPower Queryの削除、フィルター、トリミング、値の置換、重複の削除を練習するためのデータです。
