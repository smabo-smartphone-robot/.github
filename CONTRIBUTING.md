# smabo への貢献 / Contributing to smabo

*日本語 / [English](#english)*

smabo に興味を持っていただきありがとうございます。不具合の報告、機能の提案、ドキュメントの修正、プルリクエスト、どれも歓迎です。

## Issue

- 不具合は「不具合の報告」、アイデアは「機能の提案」のテンプレートから作成してください。
- どのリポジトリに出せばよいかわからないときは、[smabo-brain](https://github.com/smabo-smartphone-robot/smabo-brain) に出してください。
- ログやスクリーンショットに Wi-Fi のパスワードやペアリングのトークンが含まれていないか確認してください。

## プルリクエスト

1. リポジトリをフォークし、`main` から作業用のブランチを作ります（例: `fix/drive-timeout`、`feat/scan-view`）。
2. 変更したら、そのリポジトリのテストを通します（各 README の「テスト」や CI の設定を参照してください）。
3. テンプレートの「概要」「変更点」「確認」を書いて、プルリクエストを出します。

### 複数のリポジトリにまたがる変更

smabo はリポジトリが分かれています。トピックやメッセージの形を変えるときは、次の順で進めてください。

1. [smabo-protocol](https://github.com/smabo-smartphone-robot/smabo-protocol) の `protocol.json` を直し、`python3 gen.py` で各リポジトリの写しを作り直す
2. 影響を受ける各リポジトリにプルリクエストを出す
3. **各リポジトリのブランチ名をそろえる**。smabo-brain と smabo-protocol の CI は、同じ名前のブランチがあればそれを取得して、プロトコルの写しが一致しているかを確かめます

## 参考

- [製作ガイド・設計書](https://smabo-smartphone-robot.github.io/)
- [リポジトリの一覧](https://github.com/smabo-smartphone-robot)

---

## English

Thanks for your interest in smabo. Bug reports, ideas, documentation fixes and pull requests are all welcome.

- **Issues:** use the bug report or feature request template. Not sure which repository? Open it in [smabo-brain](https://github.com/smabo-smartphone-robot/smabo-brain). Please remove Wi-Fi passwords and pairing tokens from logs.
- **Pull requests:** branch from `main`, run the repository's tests, and fill in the template (summary, changes, how it was tested).
- **Changes across repositories:** edit `protocol.json` in [smabo-protocol](https://github.com/smabo-smartphone-robot/smabo-protocol), run `python3 gen.py`, then open a pull request in each affected repository **with the same branch name**, so the CI of smabo-brain and smabo-protocol checks them together.
- Guides and design docs: <https://smabo-smartphone-robot.github.io/>
