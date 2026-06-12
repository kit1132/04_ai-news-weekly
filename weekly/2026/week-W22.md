# AI ニュース週次サマリー — 2026-W22（2026-05-25 〜 2026-05-31）

> 入力: 取得成功 20 / 21（欠損は下の表に列挙）
> 生成日時: 2026-06-12（JST・バックフィル生成）

## ⚠️ 欠損ファイル通知

| 日付 | 欠損リポジトリ | 影響 |
|---|---|---|
| 2026-05-31 | [master]（kit1132/01_ai-news-Master） | モデル / Claude Code 情報が不足の可能性（[copilot][industry] の同日分で部分補完） |

## 今週のハイライト

### 1. Claude Opus 4.8 リリース — 価格据置でコーディング/エージェント性能の首位を更新、Mythos 一般展開も予告

**事実**: Anthropic が 5/28 に Claude Opus 4.8 をリリース（Opus 4.7 から 41 日での更新）。SWE-Bench Pro 69.2%（4.7: 64.3% / GPT-5.5: 58.6%）、SWE-bench Verified 88.6%、OSWorld-Verified 83.4%（GPT-5.5: 78.7%）、USAMO 2026 96.7%。Super-Agent ベンチを全ケース end-to-end 完走した唯一のモデル。新機能として Dynamic Workflows（Research Preview、1 ワークフローあたり最大 1,000 サブエージェントを並列実行）と Effort Control を同時投入。API 価格は据置（$5/$25 per MTok）で Fast Mode は 3× 値下げ（$10/$50）。Claude.ai / API / Bedrock / Vertex / Foundry に即日展開され、GitHub Copilot（5/28 GA、Pro+/Business/Enterprise）と M365 Copilot（Cowork Frontier / Copilot Studio Early Release / Copilot Chat / Excel / PowerPoint）にも同週内に展開された。あわせて「Mythos クラスモデルを数週間以内に一般展開する」と表明。

**根拠**: Artificial Analysis のベンチで Elo 1890（GPT-5.5 比 +121、Opus 4.7 比 +137）。SWE-Bench Pro の同スコアを Opus 4.7 比ターン -15% / 出力トークン -35% で達成する効率改善。「honesty」改善により自作コードの欠陥を申告せず通過させる確率が前世代比 1/4。

**影響**: コーディング・コンピュータ操作領域での Anthropic リードが「誤差ではない」水準に拡大。Fast Mode 値下げは Claude Code ヘビーユーザーの実効単価を直接下げる。Mythos 一般展開予告により、フロンティアモデル投入サイクルがさらに加速する。

**行動指針**: Claude Code 利用者は v2.1.156 以降へ早めに更新する（Opus 4.8 の thinking blocks 改変による API エラーの hotfix を含むため）。Bedrock / Vertex でも即日利用可能なので、既存プロジェクトでは Opus 4.8 への切替検証と Fast Mode 新価格でのコスト再見積もりを行う。

- https://www.anthropic.com/news/claude-opus-4-8
- https://techcrunch.com/2026/05/28/anthropic-releases-opus-4-8-with-new-dynamic-workflow-tool/
- https://venturebeat.com/technology/anthropics-claude-opus-4-8-is-here-with-3x-cheaper-fast-mode-and-near-mythos-level-alignment
- https://www.marktechpost.com/2026/05/28/anthropic-ships-claude-opus-4-8-alongside-dynamic-workflows-and-cheaper-fast-mode-with-workflows-capped-at-1000-subagents/
- https://github.blog/changelog/2026-05-28-claude-opus-4-8-is-generally-available-for-github-copilot/

### 2. Anthropic Series H $65B クローズ・評価額 $965B — OpenAI を初めて逆転、初の四半期黒字も射程

**事実**: 週初（5/25-26）は「$30B 調達・$900B 評価・5/26 週クローズ見込み」の観測報道だったが、5/28 にクローズし、5/29-30 の確報で Series H $65B・post-money $965B に拡大していたことが判明。OpenAI の評価額を初めて上回り「世界で最も価値のある AI スタートアップ」となった。Co-lead は Altimeter / Dragoneer / Greenoaks / Sequoia / Capital Group / Coatue / D1。インフラ戦略パートナーとして Samsung / SK Hynix / Micron が初参加し、$65B のうち $15B は hyperscaler の事前コミット（Amazon の $5B を含む）。Run-rate revenue は $47B に到達。Q2 売上 $10.9B 見込み（Q1 $4.8B 比 +130%）で創業以来初の四半期営業黒字（$559M）見通し、コンピュート費用の売上比率は 71%→56% に改善。IPO は 10 月の NASDAQ 上場を Goldman Sachs / JPMorgan / Morgan Stanley と協議中。

**根拠**: Bloomberg / TechCrunch / CNBC / Axios が 5/28-29 に一斉確報。黒字化見通しは 5/20 CNBC 報道。なお比較対象の OpenAI 評価額は [master] が $730B、[industry] が $852B（3 月時点）と記述が分かれる（改善メモ参照）。

**影響**: AI 資本市場の重心が Anthropic に移動。メモリベンダー（Samsung / SK Hynix / Micron）の参加は DRAM/HBM 調達確保の含意があり、長コンテキスト・大規模推論の供給能力増強につながる。IPO 前最後のプライベートラウンドとみられ、OpenAI（9 月上場想定・機密 S-1 提出済み）との上場レースが本格化。

**行動指針**: Claude / Bedrock 依存のプロジェクトにとって供給面・継続性の安心材料。一方で Ramp Index が指摘する「トークン課金コスト」リスクは残るため、6/15 開始予定のエージェント利用向け月額クレジット付与（[industry] 5/29）を確認しておく。

- https://www.bloomberg.com/news/articles/2026-05-28/anthropic-raises-at-965-billion-valuation-eclipsing-openai
- https://techcrunch.com/2026/05/28/anthropic-raises-65-billion-nears-1t-valuation-ahead-of-ipo/
- https://www.cnbc.com/2026/05/28/anthropic-open-ai-startup-value.html
- https://www.cnbc.com/2026/05/20/anthropic-revenue-explosive-growth-ipo-profitable-quarter.html

### 3. Copilot Studio 5月大型更新 — Computer Use GA・新オーケストレーション層・音声エージェント GA、M365 Copilot は新デザインへ

**事実**: 5/26 公開の月次ブログで Copilot Studio の大型アップデートが発表された。(1) Computer Use エージェント GA（OpenAI CUA + Claude Sonnet 4.5 搭載、Azure Key Vault 資格情報管理、Purview 監査ログ。GA 自体は 5/13 に全商用リージョンで開始との報道もあり）、(2) ワークフロー体験刷新（Early Release、統合ビジュアルキャンバスに既存エージェントを「エージェントノード」として埋め込み可能、ノードレベルテスト対応）、(3) 新オーケストレーション層（評価性能約 20% 向上・トークン消費 50% 削減）、(4) リアルタイム音声エージェント GA（北米、Dynamics 365 Contact Center 経由）、(5) Work IQ REST API / CLI（Public Preview、リモート MCP サーバー接続対応）、(6) A2A（エージェント間通信）GA。さらに 5/28 には Mistral Medium 3.5 がモデルプロバイダーに追加（Experimental、EU 域内データ処理対応、M365 admin center + Power Platform admin center の 2 段階オプトイン、MC1325410）、GPT-5.5 Reasoning (Deep) / GPT-5.5 Instant も追加。同日 5/28 には M365 Copilot の UI 全面刷新も発表（ロード時間 50% 以上短縮、プロンプトバーがタスク対応ワークスペースに進化、Work IQ インテリジェンス層統合）。

**根拠**: Microsoft 公式の Copilot Studio ブログ（5/26、5/28）および M365 ブログ（5/28）。Word/Excel/PowerPoint での Copilot 利用が 27-43% 増加というデータも公表。

**影響**: Copilot Studio がエージェント基盤として「UI 操作（Computer Use）・ワークフロー・音声・マルチモデル」を揃え、エンタープライズの本命プラットフォームとしての形が完成しつつある。トークン消費 50% 削減はランニングコストに直結。Mistral 追加で Copilot Studio のモデル選択肢は OpenAI / Anthropic / xAI / Mistral のマルチベンダー体制に。

**行動指針**: Copilot Studio エージェント開発では新オーケストレーション層とワークフロー刷新（Early Release）を検証環境で確認する。Mistral Medium 3.5 は Experimental 指定のため非本番でテスト。5/31 GA 予定の Copilot Studio CLI で CI/CD 組み込みを検討する。

- https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/new-and-improved-computer-using-agents-a-new-workflows-experience-and-real-time-voice-experiences/
- https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/mistral-joins-copilot-studios-growing-lineup-of-model-providers/
- https://www.microsoft.com/en-us/microsoft-365/blog/2026/05/28/introducing-a-new-design-for-microsoft-365-copilot/
- https://techcommunity.microsoft.com/blog/copilot-studio-blog/computer-using-agents-in-microsoft-copilot-studio-are-now-generally-available/4519427

### 4. GitHub Copilot、6/1 従量課金移行へ最終週 — 個人プラン制限強化と Opus 4.8 即日対応

**事実**: 6/1 の全プラン従量課金（AI Credits、1 Credit = $0.01。コード補完・Next Edit は消費対象外）と GPT-4.1 廃止を前に、個人プランの変更が加速。Pro/Pro+/Student の新規サインアップを一時停止し、Pro プランから Opus モデルを削除（Pro+ は Opus 4.7 → 4.8 のみ）、利用上限を引き下げて VS Code / CLI に使用量表示を追加。エンタープライズ向けには組織単位でモデル可用性を制御する「Model Rules」（5/26、Business/Enterprise）と Copilot Memory の管理強化（5/26、リポジトリ単位オフスイッチ・CLI `/memory` コマンド）を投入。Copilot Chat on Web では Gemini 全モデル・GPT-5.2 Codex・GPT-5.4 nano を削除（5/20）。Claude Opus 4.8 にはリリース当日（5/28）に対応（6/1 まで 15X premium multiplier）。CLI は v1.0.52→v1.0.56-2 まで週間 10 超のリリース、Desktop App（5/14 テクニカルプレビュー）も継続展開中。

**根拠**: GitHub 公式ブログ・Changelog（5/20, 5/26, 5/28）と github/copilot-cli releases。変更理由は「エージェント型ワークフローによる計算コスト増大」と公式に説明。

**影響**: 個人開発者のコスト構造が 6/1 を境に変わる。Free/Student は CLI で Auto モデル選択に制限されるなど、エージェント利用の「無制限感」は終了へ。組織管理者には Model Rules によるモデル統制手段が揃った。

**行動指針**: 6/1 までに自分のプランの AI Credits 換算と月間利用量を確認する。GPT-4.1 依存のワークフローは移行する。組織利用では Model Rules と Copilot Memory のリポジトリ単位設定を確認する。

- https://github.blog/news-insights/company-news/changes-to-github-copilot-individual-plans/
- https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/
- https://github.blog/changelog/2026-05-26-target-copilot-models-to-organizations-with-model-rules/
- https://github.blog/changelog/2026-05-26-copilot-memory-has-more-controls-for-deletion-scope-and-the-copilot-cli/

### 5. Cognition（Devin）が $1B Series D・評価額 $26B — コーディングエージェントへの資金集中が継続

**事実**: 5/27、Cognition AI が $1B 超の Series D を完了し評価額 $26B に（約 8〜9 ヶ月前の Series C $10.2B から 2.5 倍超）。Lux Capital / General Catalyst / 8VC が共同リードし、Founders Fund / Ribbit Capital / Atreides Management も参加。累計調達額は $2.5B 超。ARR は $492M（前年同期 $37M から 13 倍超）、エンタープライズ利用は年初から 10 倍増で Mercedes-Benz / NASA / Goldman Sachs / Santander 等が顧客。自社コードの 89% が Devin により記述（2025 年 12 月時点では 13%）。同時に新モデル SWE-1.6（SWE-Bench Pro で前モデル比 11% 向上、950 tok/s 維持、Windsurf 対応）も発表。

**根拠**: TechCrunch（5/27）と Cognition 公式ブログ。Mercedes-Benz の「8 ヶ月のレガシーモダナイズを 8 日に短縮」事例も公表。

**影響**: Claude Code（Anthropic $965B）・GitHub Copilot（Microsoft）・Cursor・Devin と、コーディングエージェント主要プレイヤーすべてが巨額資金または収益成長を確保し、市場の独立第 4 極として Cognition が生き残りを確定させた格好。「自社コードの 89% をエージェントが書く」は開発組織の将来像のベンチマークになる。

**行動指針**: インシデント対応自動化を検討する際は、Devin の Auto-Triage（Datadog / Sentry / PagerDuty / Linear 連携で人間の割り当てなしに自動調査）が参考になる。エージェント比較検討の選択肢として v3 API 正式化もウォッチ。

- https://techcrunch.com/2026/05/27/ai-coding-startup-cognition-raises-1b-at-25b-pre-money-valuation/
- https://cognition.ai/blog/swe-1-6
- https://docs.devin.ai/release-notes/overview

## モデル・技術

### Sonnet 4.8 / Mythos ウォッチ — [master][copilot]

- **Sonnet 4.8: 公式発表なし継続**（5/28 時点も根拠は 3/31 の Claude Code npm パッケージ source map リーク文字列のみ。公式最新 Sonnet は 4.6 のまま）
- **Mythos**: 週前半は「Project Glasswing 経由の限定アクセスのみ・一般公開予定なし」だったが、Opus 4.8 発表（5/28）にあわせ「数週間以内に Mythos クラスを一般展開」へ方針転換。Anthropic は「現時点でいかなる企業も Mythos の悪用を防ぐ十分なセーフガードを持たない」と明言し、Opus 4.8 で先行投入したセーフガードを磨き込んでから順次解放するとした
- [copilot] は `claude-mythos-1-preview` のモデル ID が Claude Code 内で一時確認されたと報告。観測筋は Mythos 1 正式リリースを 6 月下旬〜7 月上旬と予測
- https://red.anthropic.com/2026/mythos-preview/
- https://www.theregister.com/security/2026/05/25/anthropic-to-release-mythos-class-models-to-the-public/5245596
- https://www.testingcatalog.com/anthropic-prepares-mythos-1-for-claude-code-and-claude-security/

### Mistral「AI Now Summit」: Le Chat → Vibe リブランド — [industry]

- 5/28 パリ開催。Le Chat を **Vibe** に改名し、Work Mode（長距離タスク実行）と Code Mode（リモートコーディングエージェント）を統合した統合エージェントプラットフォームへ
- デフォルトモデルは Mistral Medium 3.5（128B、SWE-Bench Verified 77.6%。5/2 リリース済みの既存モデル）
- 従業員 1,000 人、2026 年売上目標 €1B。フルスタック AI プロバイダーへの戦略転換
- https://mistral.ai/news/ai-now-summit-2026/

### DeepSeek V4-Pro、75% 値下げを恒久化 — [industry]

- 5/22-23 適用。$0.435/$0.87 per MTok（当初 5/31 終了予定のプロモ価格を永続化）。「長コンテキスト推論のコスト構造を変えた効率改善の還元」と説明
- 1.6T パラメータ（49B アクティブ）MoE、1M トークンコンテキスト、SWE-bench Verified 80.6%、MIT ライセンスで Hugging Face 公開済み
- $45B 評価額での資金調達交渉中。API 価格戦争がさらに激化
- https://www.engadget.com/2180062/deepseek-permanently-reduces-the-price-of-its-flagship-v4-model-by-75-percent/
- https://www.infoworld.com/article/4176709/deepseeks-steep-v4-pro-price-cut-escalates-ai-pricing-war.html

### Gemini 3.5 Flash が検索・アプリのデフォルトに — [industry][master]

- I/O 2026（5/19）発表分が 5/26 に全面適用。Gemini アプリと Google 検索 AI Mode の世界デフォルトモデルに
- $1.50/$9 per MTok、Artificial Analysis Intelligence Index 55、Opus 4.7 の約 1/3 価格・4 倍高速
- **Gemini 3.5 Pro は「6 月提供予定」のまま週を通じて変わらず**。Spark（24 時間稼働パーソナルエージェント）は AI Ultra 加入者向け先行展開中
- https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/
- https://techcrunch.com/2026/05/19/with-gemini-3-5-flash-google-bets-its-next-ai-wave-on-agents-not-chatbots/

### その他のモデル動向 — [copilot][industry]

- **Cursor Composer 2.5**（5/18）: Kimi K2.5 ベースの独自モデル。SWE-Bench Multilingual 79.8% で Opus 4.7 / GPT-5.5 と同等性能をコスト約 1/10 で実現（Standard $0.50/$2.50 per MTok） — https://cursor.com/blog/composer-2-5
- **Cerebras × Kimi K2.6**: IPO 直後の Cerebras が 1T パラメータ MoE の Kimi K2.6 を 981 tok/s で推論（GPU 比 6.7 倍速、Artificial Analysis 第三者検証済み）
- **MiniCPM5-1B**（5/26、OpenBMB）: CPU 動作可能な 1B オープンモデル。エッジ・組み込み向け
- **Thinking Machines「Interaction Model」**（5/11 プレビュー・今週把握）: 200ms マイクロターンのフルデュプレックス音声対話。FD-bench v1.5 で OpenAI Realtime 2 / Gemini 3.1 Flash Live を上回る
- **Qwen3.7-Max** が Apex Math Reasoning ベンチで首位（44.5 > DeepSeek V4-Pro Max 38.3 > Claude Opus-4.6 Max 34.5）

## 開発ツール（コーディングエージェント）

### Claude Code: 4日停滞から週後半に大型リリース連発 — [master][copilot]

- v2.1.150（5/23）から 4 日停滞ののち、Opus 4.8 と連動して週後半に集中リリース
- **v2.1.152（5/27、33 変更）**: `/code-review --fix`（レビュー指摘をワーキングツリーへ直接適用、`/simplify` を統合）、スキル/スラッシュコマンドの `disallowed-tools`、`/reload-skills`、`MessageDisplay` フック新設、**Auto モードの opt-in 同意撤廃**、`--fallback-model` 自動切替
- **v2.1.153 / v2.1.154（5/28、Opus 4.8 連動）**: Opus 4.8 で `/effort xhigh` 既定、**Dynamic Workflows**（`/workflows`、数十〜数百サブエージェントのオーケストレーション）、Fast Mode 新価格反映（標準の 2× 価格で 2.5× 速度）、Lean system prompt デフォルト化、`claude agents` の `!` シェル統合。セキュリティ強化: データ持出（リポジトリ一括転送）検知強化、`$HOME` 末尾スラッシュで `rm -rf` がブロックされない脆弱性修正、カスタム API ゲートウェイへ Anthropic OAuth トークンが送られる問題の修正
- **v2.1.156（5/29）**: Opus 4.8 で thinking blocks が改変され API エラーになる問題の hotfix（**Opus 4.8 利用者は要更新**）
- [copilot] は週間まとめとして v2.1.157 までと security-guidance plugin（脆弱パターンのリアルタイム検出）・ultracode 設定にも言及
- 廃止予告: `CLAUDE_CODE_OPUS_4_6_FAST_MODE_OVERRIDE` は 6/1 削除予定
- https://code.claude.com/docs/en/changelog

### GitHub Copilot CLI: 週間 10 超リリースで Opus 4.8 に最速追従 — [master][copilot]

- v1.0.52/53（5/23-24）: コンテキストウィンドウのティア選択（~200K / 1M）を end-to-end で強制、トークン使用量表示の明確化
- v1.0.54〜v1.0.55-7（5/24-27）: `/autopilot` コマンド、MCP 設定の専用画面分離、フック進捗のリアルタイムストリーミング、`--continue` での git コンテキスト再取得
- **v1.0.55 stable（5/28）**: **Claude Opus 4.8 サポート**、thinking トークンの usage 計上、Free/Student は Auto モデル選択に制限
- v1.0.56-1/-2（5/29）: `gh` CLI 利用時に GitHub MCP server の重複ツールを省略しトークン削減、diff ビュー連続スクロール + sticky ヘッダ、Web フェッチの Markdown 優先
- https://github.com/github/copilot-cli/releases

### GitHub Copilot Desktop App（テクニカルプレビュー・今週把握） — [copilot]

- 5/14 公開の GitHub ネイティブデスクトップクライアント（macOS/Windows/Linux）。Issue・PR・プロンプト・過去セッションからタスク開始
- **Agent Merge**: レビューコメント対応→チェック修正→条件を満たせばマージまで自動化（ブランチ保護ルールは維持）
- セッションごとに独立した git worktree・ブランチで並列実行。Pro/Pro+/Business/Enterprise 向け
- https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/

### OpenAI Codex — [master][industry]

- **Codex CLI v0.135.0**（5/28 stable）: `codex doctor` 診断強化、`/permissions` の named permission profiles、Vim text-object 編集、`/status` リモート接続詳細。v0.136.0-alpha.1（5/29）も継続
- **Codex モバイル対応**（5/14・今週把握）: ChatGPT モバイルアプリ（iOS/Android）から Codex セッションをリモート操作（差分レビュー・承認・モデル切替）。全プラン利用可、週間 4M ユーザー
- **自己改善する税務エージェント**（5/27、Thrive Holdings 共同開発）: 人間の修正フィードバックと本番トレースを Codex がループに取り込み 7,000 件処理・最大 97% 精度
- https://github.com/openai/codex/releases
- https://openai.com/index/work-with-codex-from-anywhere/
- https://openai.com/index/building-self-improving-tax-agents-with-codex/

### Cursor — [master][copilot]

- **3.6 Auto-review**（5/29）: Shell/MCP/Fetch ツール呼び出しを自動承認分類（許可リスト→即実行、サンドボックス→隔離実行、その他→分類サブエージェント判定）。長時間作業の承認プロンプトを大幅削減
- 3.5（5/20）補足: Automations の Agents Window 統合・マルチリポ・リポなし対応、Shared Canvases（ライブスナップショット共有）、Jira 統合（@Cursor メンションでクラウドエージェント起動）
- **Bugbot はシート課金（$40/席/月）を廃止し従量課金へ**（6/8 以降切替）
- https://cursor.com/changelog

### xAI / Grok — [master][industry]

- **Grok Build ベータ**: ターミナル型コーディングエージェント。最大 8 エージェント並列、SWE-Bench Verified 70.8%、2M トークンコンテキスト、AGENTS.md / プラグイン / MCP 対応。SuperGrok Heavy $300/月（導入価格 $99/月）。Claude Code / Codex / Copilot CLI に続く 4 番手参入（公開日は 5/14〜5/25 で報道に揺れ。改善メモ参照）
- **Grok Custom Skills**（5/26）: 再利用可能タスクを作成・日次運用できる自動化機能。Claude Code の Skills / Codex の Goal Mode と同系
- Musk が **V9-Medium（1.5T パラメータ、現行 Grok の 3 倍）** を 6 月中旬に公開と予告
- https://x.ai/news/grok-build-cli

### Devin（プロダクト面） — [copilot]

- **Devin 2.2**: Computer Use による自己検証（Linux デスクトップでアプリ実行・テスト、スクリーンレコーディング付き）で コード→テスト→修正のクローズドループを実現
- **Auto-Triage**: Datadog / Sentry / PagerDuty / Linear からバグ・インシデントを自動検知・調査し PR またはレポートを生成
- v3 API 正式化（RBAC・セッション帰属）、PR マージコンフリクト自動検出
- https://cognition.ai/blog/introducing-devin-2-2

### エージェント開発基盤・周辺ツール — [industry][master]

- **LangSmith Engine パブリックベータ**: 本番トレース（ツール失敗・タイムアウト・トークン爆発等）を監視し、障害パターンをクラスタリングして修正 PR とカスタム評価器を自動生成 — https://www.langchain.com/blog/introducing-langsmith-engine
- **Google Managed Agent API**: Gemini API のコール 1 発で Linux サンドボックス付き AI エージェントを起動。Markdown でカスタム指示 — https://www.publickey1.jp/blog/26/apigooglelinuxaimarkdownmanaged_agent_api.html
- **Raindrop「Workshop」**（OSS）: AI エージェントのローカルデバッグ・評価ツール。全トークン・ツールコール・判断をローカルダッシュボードに表示
- **Brave AgentStop**（5/28）: ローカル LLM/エージェントの過剰リソース消費をタスク完了検知で自動停止
- **Google Antigravity AGY 2.0**: 5/29 にバグ修正・安定化リリース（大型機能追加なし）
- **GitHub Trending**: AI エージェント「skills」系フレームワークがトレンドの 25% を占有。Karpathy 系 skills リポジトリが週間最大スター増

## エンタープライズ製品・M365

### M365 Copilot / Notebooks — [copilot]

- **Anthropic Claude モデルが Word 編集で利用可能に**（MC1296489、5 月中旬〜下旬展開）: EU/EFTA/UK 以外ではデフォルト有効。あわせて対象テナントで Claude モデルが opt-in からデフォルト有効へ転換
- **GPT-5.5 Instant** が M365 Copilot / Copilot Studio に展開。Copilot Cowork（Frontier）には Opus 4.8 を追加
- **Notebooks 5 月更新**: 会議の完全記録（トランスクリプト・チャット・共有ファイル）/ メールスレッド / Web リサーチの取込、Excel・インフォグラフィック出力、OneNote iPhone アプリのライブキャプチャ（音声+ホワイトボード+メモ→構造化ページ）
- Calendar Agent 展開中、Capacity Packs（月 25,000 メッセージのプリペイド）、共有エージェントの所有権移管、Microsoft Loop の Copilot 生成 Recaps 廃止（5 月末）
- ISO 42001 認証を Copilot ポートフォリオ全体に拡大、Apple CarPlay 対応
- **Agent 365 / M365 E7 が全チャネル（EA/EAS/CSP/MCA）で販売開始**（$15 / $99 per user/月）
- https://techcommunity.microsoft.com/blog/microsoft365copilotblog/what%E2%80%99s-new-in-microsoft-365-copilot--may-2026/4522010
- https://techcommunity.microsoft.com/blog/microsoft365copilotblog/what%E2%80%99s-new-in-notebooks--may-2026/4519838

### Copilot Studio / Power Platform（ハイライト以外） — [copilot]

- **Platform Build 2026.5.3**: 環境横断の分析概要（複数エージェントのセッション数・自律実行数・DAU）、カスタムメトリクス、MCP 対応コネクタのツール一覧プレビュー、ASR ドメイン言語モデルのデフォルト有効化。**Breaking Change: カスタム発音辞書が 500 エントリ上限に**
- **Question Themes Analysis GA**（5/29）: ユーザー質問を AI がテーマ別グループ化し、回答率・応答品質・フィードバックを可視化
- Power Apps v26052 全世界展開完了（5/27、ユーザー定義型 GA の安定化リリース）
- 今後: Purview DLP for Copilot Studio agents（プロンプト内機密データ検出・応答ブロック）
- https://learn.microsoft.com/en-us/power-platform/released-versions/copilotstudio/2026.5.3

### Anthropic のエンタープライズ基盤強化 — [copilot][industry]

- **Compliance API + 28 セキュリティ統合**（5/25）: Claude 活動データへのプログラマティックアクセスを提供。DLP / SASE / SIEM / eDiscovery 等のカテゴリで Cloudflare / CrowdStrike / Microsoft Purview / Netskope / Palo Alto Networks / Datadog / Okta / Wiz / Zscaler 等 28 社と統合 — https://www.helpnetsecurity.com/2026/05/25/anthropic-security-compliance-integrations-claude/
- **Claude Platform on AWS GA**（5/11・今週把握）: Bedrock を介さず既存 AWS アカウントから Anthropic ネイティブ API に直接アクセス。マネージドエージェント・コード実行・Web 検索・MCP 統合を含む全機能。IAM/CloudTrail で認証・監査、AWS Marketplace 課金、東京含む 17 リージョン — https://aws.amazon.com/about-aws/whats-new/2026/05/claude-platform-aws/
- **MCP Tunnels（リサーチプレビュー）+ Self-Hosted Sandboxes（パブリックベータ）**（5/19 Code with Claude London・今週把握）: ツール実行レイヤーを顧客インフラ（Cloudflare / Daytona / Modal / Vercel 等）で実行し、オーケストレーションは Anthropic 側に残す分離設計。MCP Tunnels は社内 DB・API をアウトバウンド暗号化接続でエージェントに安全公開 — https://thenewstack.io/anthropic-mcp-tunnels-sandboxes/

### その他エンタープライズ — [industry]

- **OpenAI Workspace Agents**: ChatGPT 上の共有エージェント（Codex 搭載）でレポート作成・コーディング・返信をバックグラウンド実行。Slack / Google Drive / Salesforce / Notion / Atlassian Rovo 統合。5/6 から従量課金 — https://openai.com/index/introducing-workspace-agents-in-chatgpt/
- **Writer**: プロンプト不要のイベント駆動 AI エージェント。Gmail / Slack / Gong 等を監視し自然言語ゴールを解釈して自律実行（行動しない判断も含む）。BYOE 暗号鍵・Datadog 連携同梱
- **富士通**: 自己進化マルチ AI エージェント技術を開発（5/25）。安全性検証済みの改善案のみ学習し、Takane の精度が平均 28pt 向上。「Kozuchi Enterprise AI Factory」に搭載予定 — https://global.fujitsu/ja-jp/pr/news/2026/05/25-01
- **Merck × Google Cloud**: 最大 $1B のエージェント AI パートナーシップ。創薬サイクル 1/3 短縮・コンプライアンス処理 80% 高速化。Mastercard も Agent Suite + Virtual C-Suite を展開
- **Lloyds Banking Group**: FTSE 上場企業初の AI 取締役会ツール導入

## 提携・資金調達・企業動向

### Anthropic の拡張（調達以外） — [industry][master]

- **SpaceX S-1 で $45B GPU 計算契約が判明**（5/20 開示・今週把握): Anthropic が 2029 年 5 月まで Colossus I/II（NVIDIA GPU 20 万基超）を専有利用、月額 $1.25B。AWS・Google Cloud だけでは推論需要を賄えず xAI 系インフラへ調達拡大 — https://techcrunch.com/2026/05/20/anthropic-will-pay-xai-1-25-billion-per-month-for-compute/
- **SDK 自動生成の Stainless を $300M 超で買収**（5/18・今週把握）: OpenAI / Google / Cloudflare も利用していたツールで、買収後はホスト型サービスを終了し Anthropic 専用化。競合の SDK 生成基盤を取り上げる戦略的含意 — https://techcrunch.com/2026/05/18/anthropic-has-acquired-the-dev-tools-startup-used-by-openai-google-and-cloudflare/
- **Andrej Karpathy が Anthropic 事前学習チームに入社**（5/19・今週把握）: Claude 自身を使って事前学習研究を加速する新チームを立ち上げ — https://techcrunch.com/2026/05/19/openai-co-founder-andrej-karpathy-joins-anthropics-pre-training-team/
- **ゲイツ財団と $200M パートナーシップ**（5/14・今週把握）: グローバルヘルス・教育向けに 4 年間（助成金 + Claude クレジット + 技術支援）
- **ミラノ・ソウルオフィス開設**（5/26-27）: 韓国は人口比 Claude 利用率 3.5 倍超。IPO 前のグローバル基盤整備
- Bloomberg「テック業界で最も求められる雇用主」（5/28）: $250K+ パッケージが頻繁と人材集中を報道

### OpenAI: IPO 準備と展開体制 — [master][industry]

- **機密 S-1 提出済み**・最大 $1T 評価で Q4 2026 上場想定の解説記事が週を通じて流通。Microsoft との非独占化（4/27 既報）の深掘り記事も継続
- **Deployment Company 発足**（$4B+ 初期資本、TPG 主導、Advent / Bain Capital / Brookfield 共同リード）: AI コンサル Tomoro を買収し FDE 約 150 名を確保、顧客組織に常駐派遣する Palantir 型モデル — https://openai.com/index/openai-launches-the-deployment-company/
- **Frontier Governance Framework 公開**（5/29）。Gartner は 5/27 に OpenAI をエンタープライズコーディングエージェント部門のリーダーに選定

### その他調達・IPO — [industry]

- **OpenRouter**: $113M Series B（評価額 $1.3B、CapitalG 主導）。400+ モデルのルーティング基盤で週 25T トークン処理（半年で 5 倍） — https://techcrunch.com/2026/05/26/openrouter-more-than-doubles-valuation-to-1-3b-in-a-year/
- **Cerebras IPO**（5/14-15・今週把握）: NASDAQ 上場で $6.38B 調達・評価額 $95B。2026 年最大のテック IPO。ウェハースケールチップで NVIDIA 一極集中に風穴
- **DeepSeek**: $45B 評価額で資金調達交渉中

## 業界動向・市場

### 企業 AI 導入率で Anthropic が OpenAI を初逆転（Ramp AI Index） — [industry]

- Anthropic 34.4%（前月比 +3.8pt） vs OpenAI 32.3%（-2.9pt）。全体の AI 導入率は 50.6%
- 牽引役は Claude Code: GitHub 公開コミットの 4% が Claude Code 経由（1 ヶ月で倍増）。Uber 事例: 2026 年 AI 予算を 4 ヶ月で消化、エンジニア 84% が利用、コミットの 70% が AI 生成
- リード喪失リスク 3 点: トークン課金による高コスト / 稼働安定性 / OSS 推論基盤との価格差
- https://venturebeat.com/technology/anthropic-finally-beat-openai-in-business-ai-adoption-but-3-big-threats-could-erase-its-lead

### チャットボット市場シェアの多極化（Similarweb 2026 年 3 月） — [industry]

- ChatGPT 56.7%（低下継続）、Gemini 25.5%（1 年で約 4.5 倍）、Claude 6.0%（前年比 +770%）、DeepSeek 3.7%、Grok 3.4%
- OpenAI 一強からマルチプレイヤー時代へ市場構造が変化
- https://www.similarweb.com/blog/marketing/geo/gen-ai-stats/

### Microsoft 社内の Claude Code ライセンス撤回 — [copilot][industry]

- **6/30 期限**で社内の Claude Code 利用を終了し GitHub Copilot CLI へ集約。Experiences and Devices 部門（Windows / M365 / Outlook / Teams / Surface）で先行実施
- 社内で「Copilot CLI より Claude Code」の声が広がり自社製品が浸食されたことが背景。Claude モデル自体は Copilot CLI 経由で利用継続可。Anthropic への $5B 出資・Azure $30B 契約は維持
- https://www.developer-tech.com/news/microsoft-claude-code-github-copilot-cli/
- https://the-decoder.com/microsoft-pulls-claude-code-licenses-and-pushes-developers-back-toward-its-own-ai-tool/

### AI と雇用 — [industry]

- 経営幹部の 99% が 2 年以内の AI 関連人員削減を予想。一般社員で「人機協働の最適化が可能」と考えるのは 32% にとどまり、経営層と現場の認識ギャップが鮮明 — https://gigazine.net/news/20260527-vast-majority-executives-expect-ai-layoffs/
- Cloudflare: Q1 売上が過去最高（$639.8M、+34%）でも「エージェンティック AI 時代の再定義」として 1,100 人（20%）削減（5/8・今週把握）。社内 AI 利用は 3 ヶ月で 600% 増

### 料金・プラットフォーム — [industry]

- **Google AI サブスク 3 ティア刷新**: AI Plus $7.99 / AI Pro $19.99 / AI Ultra $99.99（旧 $250 から値下げ）。日次プロンプト上限を廃止し従量モデルへ
- **日本円建て移行が加速**: ChatGPT Go/Pro が円建てに、Google「AI Plus」月 1,200 円新設。主要 8 サービス中 6 つが円建て対応
- **Apple**: iOS 27「Extensions」でサードパーティ AI（Gemini / Claude 等）を Siri / Writing Tools に選択可能へ。WWDC（6/8）前に genai.apple.com サブドメインを準備 — https://www.engadget.com/2165451/apple-intelligence-will-reportedly-let-you-choose-third-party-ai-models-in-ios-27/
- クラウドインフラ Q1 2026（Synergy Research）: AWS 28% / Azure 21% / GCP 14%、市場全体 +35%
- IDC: 2026 年半導体市場 $1.29T（+52.8%）、AI 主導で DRAM 収益 3 倍（HBM 牽引）

### 言説・トレンド — [master][industry]

- 「Cursor / Claude Code / Codex は単一勝者ではなく層構造で併用される AI コーディングスタック」論が継続流通（オーケストレーション / 実行 / レビューで使い分け）
- Notion External Agents API 経由で Claude Code / Cursor / Codex がワークスペースに「ネイティブ AI エージェント」として参加する実利用フェーズ報道
- ローマ教皇レオ 14 世が AI 時代の人間の尊厳保護をテーマにした回勅「Magnifica Humanitas」を発表（5/25、Anthropic 共同創業者 Christopher Olah が同席）
- Trump 大統領が AI 大統領令の署名を「米国の競争力を損なうリスク」として突如撤回

## セキュリティ・政策・規制

### OpenAI、TanStack サプライチェーン攻撃で内部コードの一部流出 — [industry]

- 5/11 発覚（今週把握）。npm/PyPI を標的とした「Mini Shai-Hulud」キャンペーンで従業員 2 名の macOS 端末が侵害され、限定的な内部リポジトリから認証情報が窃取。ユーザーデータ・本番環境・知財への影響なし
- **6/12 に macOS アプリのコード署名証明書を全面失効予定**。Mistral AI・UiPath 等も被害
- https://openai.com/index/our-response-to-the-tanstack-npm-supply-chain-attack/

### AI 生成ゼロデイ・AI レッドチームの実用化 — [industry]

- **Google GTIG が初の AI 生成ゼロデイ（2FA バイパス）を野生で検出**: LLM が OSS 管理ツールの信頼仮定を突くエクスプロイトを生成（教育的 docstring・幻覚 CVSS スコアが残存）。「コンセプトから動作エクスプロイトまで数時間」と警告。パッチ済み — https://thehackernews.com/2026/05/hackers-used-ai-to-develop-first-known.html
- **Microsoft MDASH**: 100+ の専門 AI エージェントを相互攻撃させ Windows 脆弱性 16 件（うち Critical RCE 4 件）を自動発見。5 月 Patch Tuesday で修正済み。CyberGym ベンチ 88.45% で首位 — https://thehackernews.com/2026/05/microsofts-mdash-ai-system-finds-16.html
- **Pentest Agent Suite が OSS 公開** — [master]: 50 の専門セキュリティエージェント・26 スラッシュコマンドを Claude Code / Codex / Gemini / Cursor 等 7 プラットフォーム横断で導入できる自律バグバウンティフレームワーク

### OpenAI Rosalind Biodefense — [master]

- 5/29 発表。ライフサイエンス特化モデル **GPT-Rosalind** を「信頼できる開発者」に提供するバイオ防衛プログラム。疫学モデリング・早期検出・パンデミック準備向け
- パートナー: Lawrence Livermore National Laboratory / Johns Hopkins APL / CEPI。ホワイトハウスと連邦機関にブリーフィング済み
- メディアは「Anthropic の Project Glasswing 対抗」と位置付け（OpenAI 公式は否定）
- https://openai.com/index/strengthening-societal-resilience-with-rosalind-biodefense/

### 規制・ガバナンス — [industry]

- **中国が AI 人材へ海外渡航制限を拡大**（5/26）: DeepSeek / Alibaba 等の民間 AI 企業の創業者・研究者・幹部に政府承認を義務付け。AI 人材を「国家安全保障資産」扱いへ — https://www.bloomberg.com/news/articles/2026-05-26/china-expands-travel-curbs-to-top-ai-talent-at-private-firms
- **arXiv がワンストライク制導入**: 幻覚参照や LLM プロンプト残存が発覚した著者に 1 年間の投稿禁止。AI 利用自体は禁止せず責任を著者に帰属
- **DataGrail レポート**: AI 機能を宣伝するベンダーの 63.6% が法的文書で AI サブプロセッサ未開示。AI 機能を持つシステムの 32.8% が高リスク活動を伴う。ベンダーデューデリジェンスの要注意項目

## 来週の注目予定

- **5/31（対象週末日）**: Copilot Studio CLI GA 予定（週内のダイジェストでは「予定」のまま終了。GA 確認は翌週分で）
- **6/1**: GitHub Copilot 全プラン従量課金（AI Credits、1 Credit = $0.01）開始 / GPT-4.1 廃止 / Code Review の Actions minutes 消費開始
- **6/1**: Claude Code `CLAUDE_CODE_OPUS_4_6_FAST_MODE_OVERRIDE` 環境変数の削除予定
- **6/2-3**: Microsoft Build 2026（サンフランシスコ）— 独自コーディング特化モデル、Windows Agent Framework API / Agent Store の発表見込み
- **6/2 頃**: M365 Copilot Release Notes の更新公開（5/19 以降分）
- **6/8**: Apple WWDC 2026 基調講演 — iOS 27「Extensions」（サードパーティ AI 選択）の正式発表見込み
- **6/8 以降**: Cursor Bugbot が従量課金へ切替
- **6/12**: OpenAI macOS アプリのコード署名証明書を全面失効（TanStack 攻撃対応。未更新クライアントはブロック）
- **6/15**: Anthropic、エージェント利用への月額クレジット付与開始
- **6 月中旬**: xAI V9-Medium（1.5T パラメータ）公開見込み
- **6 月中旬〜下旬**: M365 Planner Agent GA
- **6 月**: Gemini 3.5 Pro 提供予定
- **6 月（数週間以内）**: Anthropic Mythos クラスモデルの一般展開（観測筋は Mythos 1 を 6 月下旬〜7 月上旬と予測）
- **6/30**: Microsoft 社内の Claude Code 利用終了期限

## 改善メモ

### ソース取得（3 リポ共通の傾向）

- **WebFetch 403 継続**: learn.microsoft.com 系 / mc.merill.net / techcommunity.microsoft.com / anthropic.com / developers.openai.com / cursor.com / devin（docs） / x.ai / releasebot.io / changepilot.cloud、および [industry] の全 RSS フィード。WebSearch プライマリ運用を継続
- **有効な代替手段（今週確立）**: Microsoft Learn MCP の `microsoft_docs_fetch` が learn.microsoft.com 配下に安定動作（[copilot] 5/31 に成功）。403 ソースの代替として継続活用を推奨
- **WebFetch 安定の一次ソース**: Claude Code Changelog（code.claude.com）、GitHub releases ページ（github/copilot-cli・anthropics/claude-code・openai/codex）。Codex CLI 情報は `developers.openai.com` ではなく GitHub releases を一次ソースに固定すべき
- **取りこぼし対策**: チェック間隔が空く場合は前回チェック日の数日前まで遡って確認する（Copilot Desktop App 5/14 等が週末跨ぎで漏れた実績）。GitHub Copilot CLI の日次 pre-release（`-N` サフィックス）は安定版とまとめて 1 項目に集約する運用でよい
- **検索インデックスが過去リリース（Codex-Spark / Claude Sonnet 4.5 等）を「最新」として返す**問題が継続。日付が曖昧な項目は公式ページの日付で必ず裏取りする
- 週末（特に日曜）は公式ソースの更新が皆無に近い。日曜分は「特筆事項なし + 直近 1 週間の整理」スタイルで簡略化してよい
- xAI 一次情報（x.ai/news / docs.x.ai/developers/release-notes）の WebFetch 疎通が未確認のまま。`daily-sources.md` の xAI 取得方法欄の整備が必要（複数日継続の課題）

### リポ間の矛盾・表記揺れ（今週検出）

- **Opus 4.8 の API 価格**: [master][industry] および [copilot] 5/30 は「$5/$25 per MTok 据置」、[copilot] 5/31 のみ「$15/$75 per MTok」。多数ソースは $5/$25。[industry] 内の DeepSeek 比較倍率の揺れ（約 11 倍 vs 入力 35 倍・出力 86 倍）もこの価格前提の違いに由来するとみられる
- **逆転対象の OpenAI 評価額**: [master] は $730B、[industry] は $852B（3 月時点）と記述が分かれる。両論併記とした
- **Grok Build のベータ公開日**: 5/14 [master] / 5/17 [industry 5/27] / 5/25 [industry 5/28] と 3 説あり。要一次確認
- **Mistral Medium 3.5**: [industry] 5/30 が「新規公開」と記載したが、W19 サマリー時点で 5/2 リリース済みの既存モデル。AI Now Summit（5/28）はデフォルト化・リブランドの発表
- **Claude Code v2.1.152 の日付**: [master] は 5/27、[copilot] 5/30 は 5/26 と表記揺れ。また [copilot] 5/31 は v2.1.157 まで言及（[master] の最終把握は v2.1.156）
- **Copilot Studio Computer Use の GA 日**: 5/13 全商用リージョン GA（[industry] 5/29）と 5/26 発表（月次ブログ）が混在 → 「5/13 GA・5/26 ブログ告知」と整理
- **Cognition Series C からの経過期間**: 8 ヶ月 / 9 ヶ月の揺れ（本文は「約 8〜9 ヶ月」と記載）
