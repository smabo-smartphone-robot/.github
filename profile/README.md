# smabo

本organizationでは、スマートフォンが入るロボット「smabo」に関するリポジトリを管理しています。

smaboには、以下のような特徴があります。
- 各パーツをブロックのように、完全工具不要でつけ外し可能
- お手持ちのスマホをロボットのセンサやコントローラとして使用可能

工具不要で組み立て可能なので、初学者の方にもピッタリなロボットです！



# リポジトリ

smaboに関するリポジトリは、以下の通りです。
- [smabo-app](https://github.com/smabo-smartphone-robot/smabo-app)
    - スマートフォンアプリ
    - スマホのセンサの使用、ロボットのコントローラとしての使用などを行う
- [smabo-esp32](https://github.com/smabo-smartphone-robot/sambo-esp32)
    - ESP32マイコンのファームウェア
    - ロボットのアクチュエータ（モータやサーボ）を制御
- [smabo-brain](https://github.com/smabo-smartphone-robot/smabo-brain)
    - PC（ラズパイなどのSBCでも可）搭載ソフト（オプション、必須ではない）
    - 画像処理など、スマホやESP32では処理が重いタスクを担当
<!-- 今後、ros対応予定
- [smabo-brain-ros](https://github.com/smabo-smartphone-robot/smabo-brain-ros)
    - smabo-brainのROS版
    - ROSの豊富なライブラリやツール（nav2, moveitなど）をsmaboで利用可能にする（オプション、必須ではない）
    - 一部コードはsmabo-brainをラップする形で実装されているため、smabo-brain-rosを使用する場合には、smabo-brainも必要
-->

# できること

smaboでは、「スマホ」「ESP32」「ブレイン用PC（ラズパイなどのSBCでも可）」を組み合わせることで、さまざまな機能を実現できます。


- smabo-app + smabo-esp32
    - 単純なロボットのコントローラ制御
- smabo-app + smabo-esp32 + smabo-brain
    - 高度な処理によるロボットの自律制御
<!--
- smabo-app + smabo-esp32 + smabo-brain-ros
    - nav2やmoveitなどのROSの豊富なライブラリを使用したロボットの自律制御
-->

ここでは、smaboでできることを紹介します。

※ 以下はあくまで一例で、組み合わせ次第でさまざまなことが可能です！

## smabo-app

### ロボットの顔として使う

face-modeで、smaboをロボットの顔として使用。

- smabo-app：画面上の顔を表示。目の色や形状は自由にカスタマイズ可能。また、外部からの通信で、目の動きや表情を変えることも可能。

## smabo-app + smabo-esp32

### 移動ロボットとして制御する

mobile-robot-controller-modeで、smaboを移動ロボットして手動制御。

- smabo-app：画面上のジョイスティックで、ロボットの並進、回転速度の送信
- smabo-esp32：受信した速度をもとに、ロボットのモータを制御

### ロボットアームとして制御する

arm-controller-modeで、smaboをロボットアームとして手動制御。
- smabo-app：画面上のジョイスティックで、ロボットアームの各関節の角度を送信
- smabo-esp32：受信した角度をもとに、サーボモータを制御


## smabo-app + smabo-esp32 + smabo-brain

### 物体認識で、移動ロボットを制御

スマホのカメラ情報をもとに、移動ロボットを制御。
- smabo-app：カメラから取得した画像の送信
- smabo-brain：受信した画像を処理し、制御値を送信
- smabo-esp32：受信した制御値をもとに、ロボットを制御

<!--
## smabo-app + smabo-esp32 + smabo-brain-ros

### nav2で自律移動

nav2パッケージを使用して、地図上の目的地まで自律移動。
- smabo-app：顔の表示（無くてもOK）
- smabo-brain-ros：nav2を使用して、ロボットの現在位置の推定、経路計画、制御値の送信
- smabo-esp32：受信した制御値をもとに、ロボットを制御
-->

<!--

## 一覧表

各組み合わせにて、できることをまとめると以下のようになります。

| 機能  | smabo-app | smabo-app + smabo-esp32 | smabo-app + smabo-brain + smabo-esp32 | 
| --- | --- | --- | --- | 
| ロボットの顔として使う | 〇 | 〇 | 〇 |
| 移動ロボットをコントローラ制御  | -  | 〇 | 〇 | 
| ロボットアームをコントローラ制御  | -  | 〇 | 〇 | 
| 物体認識で移動ロボットを制御 | -  | -  | 〇 | 
-->

<!--
| 機能  | smabo-app | smabo-app + smabo-esp32 | smabo-app + smabo-brain + smabo-esp32 | smabo-app + smabo-brain-ros + smabo-esp32 |
| --- | --- | --- | --- | --- |
| ロボットの顔として使う | 〇 | 〇 | 〇 | 〇 |
| 移動ロボットをコントローラ制御  | -  | 〇 | 〇 | 〇 |
| ロボットアームをコントローラ制御  | -  | 〇 | 〇 | 〇 |
| 物体認識で移動ロボットを制御 | -  | -  | 〇 | 〇 |
| nav2で自律移動 | -  | -  | -  | 〇 |
-->

