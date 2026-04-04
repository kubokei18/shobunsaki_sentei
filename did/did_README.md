# did/ フォルダ - DID（人口集中地区）GeoJSONデータ

## 概要
このフォルダには、DID（人口集中地区）のポリゴンデータをGeoJSON形式で格納します。
`index.html` が起動時に `index.json` を読み込み、記載されているファイルを全て自動読み込みして結合します。

## ファイル構成
```
did/
  index.json          ← 読み込むファイルの一覧（必須）
  01_hokkaido.geojson ← 北海道のDIDポリゴン
  20_nagano.geojson   ← 長野県のDIDポリゴン
  ...
```

## index.json の形式
```json
[
  "20_nagano.geojson",
  "21_gifu.geojson"
]
```
使用する都道府県のファイル名のみ記載してください。
ファイルが存在しない都道府県は除外してください。

## GeoJSONファイルの作成方法
1. e-Stat（https://www.e-stat.go.jp）にアクセス
2. 「地図」→「統計GIS」→「境界データダウンロード」
3. 「小地域」→「人口集中地区」→ 都道府県を選択してShapefileをダウンロード
4. mapshaper.org でShapefileをGeoJSONに変換
5. このフォルダに配置し、index.jsonにファイル名を追記

## 更新方法
GeoJSONファイルを差し替えてGitHubにpushするだけで全ユーザーに反映されます。
HTMLを修正する必要はありません。

## データの出典
国勢調査（e-Stat、総務省統計局）の人口集中地区境界データを使用。
5年ごとに更新されます（直近：令和2年国勢調査）。
