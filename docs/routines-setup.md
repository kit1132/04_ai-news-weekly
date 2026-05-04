# Routines 設定手順 — 週次AIニュースサマリー

Claude Code Web Routines で週次サマリー生成を自動化する手順。

## 前提
- Claude Code Web へアクセス可能（https://code.claude.com）
- 以下 4 リポへの GitHub 連携済み
  - kit1132/01_ai-news-master
  - kit1132/02_ai-news-copilot
  - kit1132/03_ai-news-industry
  - kit1132/04_ai-news-weekly

## 設定値
| 項目 | 値 |
|---|---|
| Routine 名 | `weekly-ai-news-summary` |
| スケジュール | 毎週日曜 09:00 JST（= 日曜 00:00 UTC） |
| Cron 表記 | `0 0 * * 0`（UTC） |
| 接続リポ | 上記 4 リポすべて |
| 主作業リポ | `kit1132/04_ai-news-weekly` |
| 起動プロンプト | `/weekly-summary` |

## 設定手順
1. https://code.claude.com を開く
2. 左ナビ「Routines」→「New Routine」
3. Name: `weekly-ai-news-summary`
4. Schedule: Weekly, Sunday, 00:00 UTC（= 09:00 JST）
5. Repositories: 上記 4 リポをすべて追加。Primary は `kit1132/04_ai-news-weekly`
6. Prompt: `/weekly-summary`
7. Branch: `main`（読み取り起点）
8. Save & Enable

## パイロット実行
1. Routines 一覧から `weekly-ai-news-summary` を選択
2. 「Run now」で手動トリガ
3. 実行ログを確認
4. `kit1132/04_ai-news-weekly` で `claude/weekly-summary-YYYY-WNN` ブランチと Draft PR が作成されたか確認
5. 出力 `weekly/{YYYY}/week-W{NN}.md` の 4 セクション構成・欠損リスト・リポタグを確認

## 受け入れ条件
- 生成された週次ファイルに 4 セクション（ハイライト / カテゴリ別 / 来週注目 / 改善メモ）が揃う
- 入力 3 リポ（01〜03）の `digests/` 配下に diff が出ない
- 既存週次ファイルがある週は上書きされず PR にスキップ通知が出る
- 一部 daily 欠損時は冒頭に欠損リスト明記・部分生成
- 7 日全欠損時は生成スキップ（空ファイル / 空 PR を作らない）

## トラブルシュート
| 症状 | 原因候補 | 対処 |
|---|---|---|
| 401 / 403 | GitHub 連携の権限不足 | 4 リポすべてで contents / pull_requests の権限を再付与 |
| `digests/` ファイル取得失敗 | 月ディレクトリ未作成 / 日次未生成 | 入力リポの実態を確認。欠損として部分生成は期待される振る舞い |
| 週番号ズレ | ISO 8601 以外の仕様で計算されている | スラッシュコマンド内で `date +%G-W%V` を使用しているか確認 |
| Draft PR が作られない | ブランチ作成・プッシュ権限不足 | 04_ai-news-weekly への write 権限を確認 |
| 上書きされた | スキップロジック不作動 | `weekly/{YYYY}/week-W{NN}.md` 存在チェックがブランチ作成前に走っているか確認 |

## 関連
- スラッシュコマンド本体: `.claude/commands/weekly-summary.md`
- Routines 仕様: https://code.claude.com/docs/en/routines.md
- Claude Code on the Web: https://code.claude.com/docs/en/claude-code-on-the-web.md
