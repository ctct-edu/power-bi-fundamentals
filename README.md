# Power BI 初学者向け1日研修 演習ガイド

この演習では、架空企業「みらいリテール株式会社」の売上データを使い、取り込み、整形、データモデル、DAX、可視化、Power BI Serviceでの共有までを体験します。

操作画面はPower BI Desktopの更新や組織の設定によって多少異なります。ボタンが見つからない場合は、同名のメニューをリボン、［ファイル］、［…］から探してください。

## 演習一覧

| 演習 | 内容 | 時間 | 主なデータソース |
|---|---|---:|---|
| [01](01-create-first-report-from-excel.md) | Excelから複数ビジュアルの簡易レポートを作成 | 30分 | Excel |
| [02](02-transform-data-with-power-query.md) | Power Queryでデータを整形 | 25分 | Excel |
| [03](03-data-modeling-and-dax.md) | 複数データのモデル化とDAX | 45分 | Excel、SQL Server、SharePoint |
| [04](04-report-visualization.md) | グラフ・表・マトリクスで可視化 | 35分 | 演習03のモデル |
| [05](05-sharing-with-power-bi-service.md) | Power BI Serviceで共有 | 25分 | Power BI Service |

合計の標準演習時間は160分です。講義時間と休憩を加えて1日研修とします。

## 使用環境

- Windows版 Power BI Desktop
- 演習ファイルを保存できるローカルフォルダー
- 演習03の標準経路: SQL Serverへの読み取り接続、SharePoint Onlineサイト
- 演習05: Power BI Serviceへサインインできる職場または学校アカウント

SQL ServerまたはSharePointを利用できない場合も演習を継続できます。各手順にある「Excelフォールバック」を選択してください。

## ファイルの配置

このリポジトリをZIPで取得した場合は、短いローカルパスへ展開してください。

```text
C:\PowerBITraining\
├─ LabManual\
└─ SampleData\
```

ネットワークドライブやOneDrive同期フォルダーより、ローカルフォルダーを推奨します。フォルダー結合で各受講者のパスが異なるため、講師の画面と自分の画面でパスが違っても問題ありません。

## 保存するPBIX

演習の開始時に、前のPBIXを［名前を付けて保存］してから操作します。

```text
PowerBI演習01_最初のレポート.pbix
PowerBI演習02_PowerQuery.pbix
PowerBI演習03_モデルとDAX.pbix
PowerBI演習04_完成レポート.pbix
```

演習05では `PowerBI演習04_完成レポート.pbix` をPower BI Serviceへ発行します。

## 標準経路とフォールバック

| データ | 標準経路 | 利用できない場合 |
|---|---|---|
| 売上明細 | `SampleData/Excel/MonthlySales` | 同じ経路を使用 |
| 商品・店舗 | SQL Server | `SampleData/Fallback/商品マスター.xlsx` と `店舗マスター.xlsx` |
| 販売目標 | SharePointリスト | `SampleData/Fallback/販売目標.xlsx` |
| 共有 | Power BI Service | 講師デモを確認し、PBIX保存までで完了 |

フォールバックは標準経路と同じ列名・キー・レコードを持ちます。接続方法だけが異なり、以後のモデリングとDAXは共通です。

## 完了状態

最終的に、次の2ページを持つレポートを作成します。

- ページ1「売上サマリー」: 売上、粗利益、目標達成率、月別推移、地域比較
- ページ2「店舗・商品分析」: 店舗別、商品カテゴリ別、商品別の詳細

## 困ったときの共通確認

1. 画面左下で現在のビュー（レポート、テーブル、モデル）を確認します。
2. フィールド名が見つからないときは、右側の［データ］ペインでテーブルを展開します。
3. 操作を戻す前に、Power Queryの［適用したステップ］を確認します。
4. 接続エラーでは、資格情報を繰り返し入力せず講師へ連絡します。
5. 5分以上進めない場合は、章末の完了条件まで講師のPBIXを使って継続します。

## 公式リファレンス

- [Power BI Desktopでデータを取得する](https://learn.microsoft.com/ja-jp/power-bi/connect-data/desktop-data-sources)
- [Power BI DesktopからPower BI Serviceへ発行する](https://learn.microsoft.com/ja-jp/power-bi/create-reports/desktop-upload-desktop-files)
- [Power BIのワークスペース](https://learn.microsoft.com/ja-jp/power-bi/collaborate-share/service-new-workspaces)

> 本資料は2026年7月時点のPower BIを前提にしています。プレビュー機能は必須操作にしていません。
