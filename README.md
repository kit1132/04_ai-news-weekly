# 04_ai-news-weekly

3リポ横断の AI ニュース週次サマリー集約リポジトリ。

## 概要
- 入力: `kit1132/01_ai-news-master`, `kit1132/02_ai-news-copilot`, `kit1132/03_ai-news-industry` の `digests/{YYYY}/{MM}/ai-news-YYYY-MM-DD.md` 直近7日分
- 出力: 本リポジトリの `weekly/{YYYY}/week-W{NN}.md`
- 実行: Claude Code Web Routines（毎週日曜 09:00 JST）
- デリバリ: `claude/weekly-summary-YYYY-WNN` ブランチ → Draft PR

## ディレクトリ
- `weekly/{YYYY}/week-W{NN}.md` — 週次サマリー出力
- `.claude/commands/weekly-summary.md` — 週次生成スラッシュコマンド
- `docs/routines-setup.md` — Routines 設定手順

## 関連リポジトリ
- [01_ai-news-master](https://github.com/kit1132/01_ai-news-master) — 入力源（master）
- [02_ai-news-copilot](https://github.com/kit1132/02_ai-news-copilot) — 入力源（copilot）
- [03_ai-news-industry](https://github.com/kit1132/03_ai-news-industry) — 入力源（industry）

## 不変条件
- 入力リポジトリ（01〜03）の `digests/` 配下を変更しない
- 既存の週次ファイル（`weekly/...`）は上書きしない
