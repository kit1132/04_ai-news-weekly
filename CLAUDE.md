# AI News Weekly Summary

## 基本方針

- 出力は日本語
- 簡潔で実用的な情報を好む。冗長な説明は不要。定量的な根拠を重視
- kit1132/01_ai-news-Master, 02_ai-news-Copilot, 03_ai-news-industry の**直近1週間分**ダイジェストを集約した週次サマリー（日次統合は kit1132/05_ai-news-daily が担当）

## プロジェクト構成

- `weekly/YYYY/week-WNN.md` — 週次サマリー本体（NN は ISO 週番号）
- `.claude/commands/weekly-summary.md` — **生成手順の正本**（ルーチンはこのファイルに従う。フォーマット定義もここ）
- `index.html` — サマリーの HTML ビューア（marked.js 使用、GitHub Pages で公開）
- `files.json` — ビューアが参照するファイル一覧（新しい順、パスはルートからの相対）
- `.nojekyll` — GitHub Pages の Jekyll 処理を無効化

## 実行環境

- claude.ai リモートルーチン（Routines）で毎週日曜 09:00 JST（cron `0 0 * * 0` UTC）に自動実行
- **ブランチ運用**: `main` へ直接 commit & push する。feature ブランチ・PR は作らない（2026-06-12 に Draft PR 方式から変更）
- **日付**: JST（Asia/Tokyo, UTC+9）で判定する。`TZ=Asia/Tokyo date +%G-W%V` で ISO 週番号を取得

## 不変条件

- 入力3リポ（01_ai-news-Master / 02_ai-news-Copilot / 03_ai-news-industry）へは一切書き込まない
- main 以外のブランチへ push しない
- 既存の週次ファイルがあれば上書きせずスキップ通知のみ
