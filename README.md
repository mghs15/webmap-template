# webmap-template
ウェブ地図作る際のテンプレみたいなやつ

## 内容
* 背景地図の上にオリジナルのベクトルタイルを表示。
* オリジナルのベクトルデータをポチポチするとリストに追加。
* リストに入っている内容を表示。

## 使い方
* 作ってみたはいいものの、オリジナルのベクトルタイルの内容によって結構変更せねばならない（sourceのURL、source-layer名、地物の形状によるスタイルの記述方法、propertiesのキー名など）
* いらんなパターンに対応したテンプレを作るよりも、結局スクラッチした方が速そう。

## 出典
* 背景地図：地理院地図Vector（国土地理院）
* サンプルデータ：地図・空中写真閲覧サービス（国土地理院）
* 使っているライブラリはMapbox GL JS。
