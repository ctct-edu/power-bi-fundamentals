# Power BIによる業務データ分析入門 ラボマニュアル（短縮版）

## はじめに

本マニュアルは、CTCテクノロジー主催「[Power BIによる業務データ分析入門](https://www.school.ctc-g.co.jp/course/P618.html)」のラボマニュアルです。Power BIを初めて操作する方を対象としています。

## ラボシナリオ

あなたは、小売企業「みらいリテール」の営業企画部に配属されたデータ分析担当者です。営業責任者から、月ごとの売上実績と目標達成状況を、商品カテゴリ・地域・店舗の観点で確認できるレポートの作成を依頼されました。

Excel、SQL Server、SharePointに分かれているデータをPower BIで統合し、営業責任者や店舗責任者が利用できるレポートとしてPower BI Serviceへ公開します。

## ラボ一覧

| ラボ | 内容 | 時間 | 主なデータソース |
|---|---|---:|---|
| [01](./LabManual/01-create-first-report-from-excel.md) | Excelから簡易レポートを作成 | 15分 | Excel |
| [02](./LabManual/02-transform-data-with-power-query.md) | 同じ売上データをPower Queryで整形 | 20分 | Excel |
| [03](./LabManual/03-data-modeling-and-dax.md) | 複数データのモデル化とDAX | 35分 | Excel、SQL Server、SharePoint |
| [04](./LabManual/04-report-visualization.md) | 2ページの業務レポートへ拡張 | 35分 | ラボ03のモデル |
| [05](./LabManual/05-sharing-with-power-bi-service.md) | Power BI Serviceで発行・共有 | 15分 | Power BI Service |

## ラボの進め方

ラボ01で保存した `みらいリテール_売上実績分析.pbix` を、ラボ05まで続けて使用します。ラボの途中で新しいPBIXは作成しません。

各ラボの冒頭に、ラボ概要、実施項目、所要時間を記載しています。操作後は「ラボの完了」で作業結果を確認してから、次のラボへ進んでください。

## ラボ用ファイルの配置

講師から配布された演習用仮想マシンに、次の構成でファイルを配置します。サインインに必要なアカウント情報は講師の案内を確認してください。

```text
C:\PowerBITraining\
├─ Excel\
│  └─ 売上データ_研修用.xlsx
├─ Fallback\
│  ├─ 商品マスター.xlsx
│  ├─ 店舗マスター.xlsx
│  └─ 販売目標.xlsx
├─ SharePoint\
│  ├─ SharePointリスト準備手順.md
│  └─ 販売目標_リスト作成用.xlsx
└─ SQLServer\
   ├─ setup_powerbi_training.sql
   └─ 接続情報テンプレート.md
```

SQL ServerとSharePoint Onlineリストは研修環境へ接続します。接続できない場合だけ `Fallback` のExcelを使用します。

## 最終的に作成するレポート

| 成果物 | 名称 |
|---|---|
| PBIXファイル | `みらいリテール_売上実績分析.pbix` |
| Power BI Serviceのレポート | `みらいリテール 売上実績分析` |
| ダッシュボード | `売上・目標達成KPI` |
| アプリ | `みらいリテール 営業分析ポータル` |

### 売上サマリー

- 売上合計カード
- 商品カテゴリ別売上の集合縦棒グラフ
- 月別売上の折れ線グラフ
- 売上達成状況のKPI
- 年月・地域スライサー

### 地域・店舗分析

- 都道府県別売上を示すAzure Maps
- 地域、都道府県、店舗名を展開できるマトリクス
- 売上サマリーと同期する年月・地域スライサー
