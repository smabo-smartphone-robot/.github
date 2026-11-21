# smabo

*[English](./README.md) / 日本語*

本organizationでは、スマートフォンが入るロボット「smabo」に関するリポジトリを管理しています。

smaboには、以下のような特徴があります。
- 各パーツをブロックのように、完全工具不要でつけ外し可能
- お手持ちのスマホをロボットのセンサ、顔として使用可能

工具不要で組み立て可能なので、初学者の方にもピッタリなロボットです！

詳しくは、[smabo紹介サイト](https://smabo-smartphone-robot.github.io)をご覧ください。


# できること

| 機能 | 内容 | 必要な構成 |
|---|---|---|
| [顔と表情](https://smabo-smartphone-robot.github.io/guides/smabo_face/) | スマホの画面が smabo の顔になり、表情や視線を変えられる | smabo-app |
| [音声処理](https://smabo-smartphone-robot.github.io/guides/audioproc/) | ウェイクワードで話しかけると音声認識し、好きな文章を話す | smabo-app + smabo-brain |
| [画像処理](https://smabo-smartphone-robot.github.io/guides/imgproc/) | カメラで AR マーカー・色・顔・QR を認識し、目や首、走行で追いかける | smabo-app + smabo-brain |
| 手動操作 | ブラウザのジョイスティックで走行、スライダーでサーボを操作 | smabo-web + smabo-esp32 |
| [ナビゲーション](https://smabo-smartphone-robot.github.io/guides/nav/) | LiDAR で地図を作り（SLAM）、指定した場所まで自律移動 | smabo-brain-ros |
| [動作計画](https://smabo-smartphone-robot.github.io/guides/plan/) | MoveIt 2 でアームの動きを計画して実行 | smabo-brain-ros |

実機がなくても、[smabo-sim](https://github.com/smabo-smartphone-robot/smabo-sim) で smabo-brain(-ros) と smabo-web を試せます。

# しくみ

```
 smabo-app (phone)        smabo-web (browser)
 face, sensors, voice     control, visualization
        |                          |
        +-------- WebSocket -------+
                     |
     smabo-brain (or smabo-brain-ros)
     relay, odometry, image / speech
     processing, Nav2, MoveIt 2
                     |
                 WebSocket
                     |
     smabo-esp32 (or smabo-sim)
     motors, servos, encoders, LiDAR
```

すべての機器は smabo-brain（または smabo-brain-ros）につながり、そこでメッセージが中継されます。

# リポジトリ

smaboに関するリポジトリは、以下の通りです。
- [smabo-app](https://github.com/smabo-smartphone-robot/smabo-app)
    - スマートフォンアプリ
    - スマホをロボットのセンサ、ロボットの顔として使用
- [smabo-esp32](https://github.com/smabo-smartphone-robot/smabo-esp32)
    - ESP32マイコンのファームウェア
    - ロボットのアクチュエータ（モータなど）を制御
- [smabo-brain](https://github.com/smabo-smartphone-robot/smabo-brain)
    - smaboの各コンポーネントからの通信を中継するハブ
    - 画像処理、AIなど高度な処理の担当
- [smabo-brain-ros](https://github.com/smabo-smartphone-robot/smabo-brain-ros)
    - smabo-brainの通信部分をweb socketからROS2通信（DDS）にラップ
    - ROSの豊富なライブラリやツール（nav2, moveitなど）をsmaboで利用可能にする（オプション、必須ではない）
- [smabo-web](https://github.com/smabo-smartphone-robot/smabo-web)
    - smaboの設定変更、手動操作、センサ情報の可視化などをweb上で可能とする補助ツール
- [smabo-hardware](https://github.com/smabo-smartphone-robot/smabo-hardware)
    - smaboの組み立て手順を記載
    - 各パーツのstl, stepファイルを管理
- [smabo-sim](https://github.com/smabo-smartphone-robot/smabo-sim)
    - smabo-esp32の代わりに動くシミュレータ（MuJoCo）
    - 実機がなくても、smabo-brain(-ros)とsmabo-webをそのまま試せる
- [smabo-protocol](https://github.com/smabo-smartphone-robot/smabo-protocol)
    - リポジトリ間の通信の決めごと（トピックと型）の正本
    - 各リポジトリで使う定義ファイルを生成
- [smabo-smartphone-robot.github.io](https://github.com/smabo-smartphone-robot/smabo-smartphone-robot.github.io)
    - smaboのサイトの管理（概要、セットアップ手順、設計書など）

# はじめかた

1. [smabo紹介サイト](https://smabo-smartphone-robot.github.io) の組み立てガイドで、3Dプリントした部品を組み立てる（部品のデータは [smabo-hardware](https://github.com/smabo-smartphone-robot/smabo-hardware)）
2. [起動手順](https://smabo-smartphone-robot.github.io/guides/startup/) に沿って、smabo-brain・smabo-web・smabo-app・smabo-esp32 を起動してつなぐ

# 貢献

不具合の報告、機能の提案、プルリクエストを歓迎しています。各リポジトリの Issue から、テンプレートに沿って作成してください。
進め方は [CONTRIBUTING.md](https://github.com/smabo-smartphone-robot/.github/blob/main/CONTRIBUTING.md) を見てください。

# ライセンス

すべてのリポジトリは [MIT ライセンス](https://opensource.org/license/mit) です。
