# webmap-template
ウェブ地図作る際のテンプレみたいなやつ

## 内容
サンプル　https://mghs15.github.io/webmap-template/index2.html

* 背景地図の上にオリジナルのベクトルタイルを表示。
* オリジナルのベクトルデータをポチポチすると選択リストに追加。
* 選択リストに入っている内容を表示。

## 使い方
### 設定
index2.htmlでは変更を想定する部分をある程度独立させた。
* GUIによる入力条件用の設定（JSON）
* Mapbox Style Spec形式の上乗せデータ表示設定（`sources`と`layers`。どちらもmetadata属性を用いて拡張）（JSON）
  * `sources`では、各地物を識別するIDとなる属性値をメタデータに記述する。
  * `layers`では、データの取得を行うスタイルレイヤ（`isMainLayer`:`true`）と選択時用のスタイルレイヤ（`isSelectedLayer`:`true`）を設定し、メタデータに記述する。
* 入力条件変更時の挙動（JavaScript関数、`refleshAll()`）
* 入力条件に対するフィルタリング条件式（JavaScript関数、`makeFilter()`）
* ポップアップの表示内容（JavaScript関数、`makePopupHtml()`）
* 選択地物リストの表示内容（JavaScript関数、`makeListHtml()`）

### 前提
想定しているベクトルタイルは、以下の通り。
  * 各地物はIDとなる属性を持っている（上乗せ用style.jsonの`sources`で指定時にメタデータに記載）

## 感想
* いろんなパターンに対応したテンプレを作るよりも、結局スクラッチした方が速そう。
* ということで、設定項目は、かなり自由度の高い方法（拡張style.json、JavaScript関数）を採用。
* 何らかのツールで、この自由度の高い（＝複雑な）設定項目の作成を支援するのが良いだろう。
* 現在、入力条件フィルタで、最初に設定する各スタイルレイヤの`filter`条件をつぶしてしまうので、何とかしたい。

## 出典
* 背景地図：地理院地図Vector（国土地理院）
* サンプルデータ：地図・空中写真閲覧サービス（国土地理院）
* 使っているライブラリはMapbox GL JS。
