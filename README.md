# AI News Weekly Digest

3 リポ横断の AI ニュースを毎週日曜に集約し、日本語週次ダイジェストとして配信するシステム。

## 仕組み

- Claude Code on the web の Routines で毎週日曜 9:00 (JST) に実行
- 入力 3 リポの `digests/{YYYY}/{MM}/ai-news-YYYY-MM-DD.md` 直近 7 日分を読み取り
- カテゴリ別に統合・重複排除した Markdown 週次ダイジェストを `digests/{YYYY}/{MM}/ai-news-YYYY-MM-DD.md`（実行日の日曜日付）に生成
- `claude/weekly-summary-YYYY-WNN` ブランチで Draft PR として提出
- push 後、[統合ビューア](https://kit1132.github.io/01_ai-news-Master/#weekly)で閲覧可能

## ビューア

閲覧は [統合ビューア](https://kit1132.github.io/01_ai-news-Master/#weekly) に一本化されている。実体は 01_ai-news-Master/index.html にあり、このリポの `index.html` はそこへのリダイレクトなので編集不要。`files.json` が週次サマリーの一覧を保持し、生成のたびに先頭に追加される（この形式はビューアが前提にしているため変更しないこと）。

## 入力リポジトリ

- [kit1132/01_ai-news-master](https://github.com/kit1132/01_ai-news-master) — タグ `[master]`
- [kit1132/02_ai-news-copilot](https://github.com/kit1132/02_ai-news-copilot) — タグ `[copilot]`
- [kit1132/03_ai-news-industry](https://github.com/kit1132/03_ai-news-industry) — タグ `[industry]`

## 不変条件

- 入力 3 リポの `digests/` 配下を変更しない（読み取りのみ）
- 既存週次ファイルは上書きしない（スキップ通知）
- 7 日全欠損時は生成中止（空 PR を作らない）

## セットアップ手順

1. このリポジトリを Fork、または直接利用
2. GitHub Pages を有効化（Settings > Pages > Source: `main`, `/ (root)`）
3. Claude Code on the web で Routines を作成（詳細は `CLAUDE.md`）
   - Schedule: Weekly / Sunday / 00:00 UTC（= 日曜 09:00 JST）
   - Repositories: `kit1132/01_ai-news-master`, `02_ai-news-copilot`, `03_ai-news-industry`, `04_ai-news-weekly` の 4 つすべて
   - Primary: `kit1132/04_ai-news-weekly`
   - Prompt: `CLAUDE.md に従って週次ダイジェストを生成し、Draft PR を提出してください。`
4. 初回は `files.json` が `[]` の状態。最初の Run で先頭に追加される

## セキュリティ上の注意

- **GitHub Pages は常に Public 公開**: Private リポジトリでも Pages は外部からアクセス可能
- **Routines の権限**: 4 リポ（入力 3 + 本リポ）への適切な read / write 権限を付与する
- **入力リポへの書き込み禁止**: Routine 実行中に 01〜03 の `digests/` を変更しないこと（CLAUDE.md の不変条件）
