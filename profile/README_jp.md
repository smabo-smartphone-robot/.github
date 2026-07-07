# smabo

*[English](./README.md) / 日本語*

本organizationでは、スマートフォンが入るロボット「smabo」に関するリポジトリを管理しています。

smaboには、以下のような特徴があります。
- 各パーツをブロックのように、完全工具不要でつけ外し可能
- お手持ちのスマホをロボットのセンサ、顔として使用可能

工具不要で組み立て可能なので、初学者の方にもピッタリなロボットです！

詳しくは、[smabo紹介サイト](https://smabo-smartphone-robot.github.io)をご覧ください。

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
- [smabo-smartphone-robot.github.io](https://github.com/smabo-smartphone-robot/smabo-smartphone-robot.github.io)
    - smaboのサイトの管理（概要、セットアップ手順、設計書など）
