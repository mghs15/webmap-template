# webmap-template
ウェブ地図作る際のテンプレみたいなやつ

## 内容
サンプル　https://mghs15.github.io/webmap-template/

* 背景地図の上にオリジナルのベクトルタイルを表示。
* 上乗せのベクトルデータをポチポチすると選択リストに追加。
* 選択リストに入っている内容を表示。

## 使い方
### 設定
変更を想定する部分を記載。
* GUI による入力条件用の設定（JSON）
* Mapbox Style Spec 形式の上乗せデータ表示設定（`metadata`、`sources`、`layers`）（JSON）
  * `metadata`では、各 `sources` ごとに、各地物を識別する ID となる属性値を記述する。
  * `layers`では、データの取得を行うスタイルレイヤ（`isMainLayer`:`true`）と選択時用のスタイルレイヤ（`isSelectedLayer`:`true`）を設定し、メタデータ（レイヤ設定内の　`metadata`）に記述する。
* 入力条件変更時の挙動（JavaScript 関数、`refleshAll()`）
* 入力条件に対するフィルタリング条件式（JavaScript 関数、`makeFilter()`）
* ポップアップの表示内容（JavaScript 関数、`makePopupHtml()`）
* 選択地物リストの表示内容（JavaScript 関数、`makeListHtml()`）

### 前提
想定している上乗せデータ（ベクトルタイル又は GeoJSON）は、以下の通り。
  * 各地物は ID となる属性を持っている（→上述の上乗せ用 style 設定 の `metadata` に記載）

## 感想
* いろんなパターンに対応したテンプレを作るよりも、結局スクラッチした方が速そう。
* ということで、設定項目は、かなり自由度の高い方法（拡張 style.json、JavaScript 関数）を採用。
* 何らかのツールで、この自由度の高い（＝複雑な）設定項目の作成を支援するのが良いだろう。
* 現在、入力条件フィルタで、最初に設定する各スタイルレイヤの `filter` 条件をつぶしてしまう。

## 出典
* 背景地図：地理院地図Vector（国土地理院）
* サンプルデータ：地図・空中写真閲覧サービス（国土地理院）
* 使っているライブラリは MapLibre GL JS
  * 2023/09/02 Mapbox GL JS から移行 
