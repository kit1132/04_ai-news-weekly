# AI News Weekly Summary

## 基本方針

- 出力は日本語
- 簡潔で実用的な情報を好む。冗長な説明は不要。定量的な根拠を重視
- kit1132/01_ai-news-Master, 02_ai-news-Copilot, 03_ai-news-industry の**直近1週間分**ダイジェストを集約した週次サマリー（日次統合は kit1132/05_ai-news-daily が担当）

## プロジェクト構成

- `weekly/YYYY/week-WNN.md` — 週次サマリー本体（NN は ISO 週番号）
- `.claude/commands/weekly-summary.md` — **生成手順の正本**（ルーチンはこのファイルに従う。フォーマット定義もここ）
- `index.html` — 統合ビューア（https://kit1132.github.io/01_ai-news-Master/ ）へのリダイレクト。実体は 01_ai-news-Master/index.html にある。**このファイルは編集不要**
- `files.json` — ビューアが参照するファイル一覧（新しい順、パスはルートからの相対）
- `.nojekyll` — GitHub Pages の Jekyll 処理を無効化

## 実行環境

- claude.ai リモートルーチン（Routines）で自動実行。**想定は毎週月曜 03:00 JST**（cron `0 18 * * 0` UTC）
  - 2026-07-26 変更。旧設定は「毎週日曜 09:00 JST（cron `0 0 * * 0` UTC）」だったが、**実際の実行日が日曜からズレて月曜・火曜になり、直近3週が連続で部分週になっていた**（W28/W29/W30）
  - 対策として `weekly-summary.md` の**対象週の定義を「直前に完結した ISO 週」に変更**した。これにより**実行日が何曜日にズレても部分週は発生しない**（ズレた日に走っても同じ週が対象になり、生成済みならスキップされる）
  - ⚠️ claude.ai Routines 側の設定変更は kit が行う必要がある（このリポジトリからは変更できない）。**未変更でも上記の仕組みで安全側に倒れる**
- **ブランチ運用**: `main` へ直接 commit & push する。feature ブランチ・PR は作らない（2026-06-12 に Draft PR 方式から変更）
- **日付**: JST（Asia/Tokyo, UTC+9）で判定する。`TZ=Asia/Tokyo date +%G-W%V` で ISO 週番号を取得

## 不変条件

- 入力3リポ（01_ai-news-Master / 02_ai-news-Copilot / 03_ai-news-industry）へは一切書き込まない
- main 以外のブランチへ push しない
- 既存の週次ファイルがあれば上書きせずスキップ通知のみ
