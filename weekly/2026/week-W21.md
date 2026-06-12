# AI ニュース週次サマリー — 2026-W21（2026-05-18 〜 2026-05-24）

> 入力: 取得成功 21 / 21（欠損なし）
> 生成日時: 2026-06-12（JST・バックフィル生成）

---

## 今週のハイライト

### 1. Google I/O 2026 — Gemini 3.5 Flash GA・Spark・Antigravity 2.0 で「agentic Gemini era」宣言

**事実**: 5/19-20 開催の Google I/O 2026 で大量発表。**Gemini 3.5 Flash が即日 GA**（Gemini アプリ / Search / Antigravity 2.0 / Gemini API）。常駐型汎用エージェント **Gemini Spark**（ベータ、来週から AI Ultra に先行提供）、動画生成 **Gemini Omni**、エージェント開発基盤 **Antigravity 2.0**（デスクトップアプリ / CLI / SDK）、**Managed Agents in Gemini API**（単一 API コールで隔離 Linux 環境のエージェントを起動、AGENTS.md / SKILL.md でスキル定義）、Search AI Mode の全世界展開、Daily Brief、AI Ultra の新価格帯（$100/月）を一斉投入。Gemini 3.5 Pro は来月提供予定。

**根拠**: Gemini 3.5 Flash は Flash クラスで 3.1 Pro を上回り、Terminal-Bench 2.1 76.2% / MCP Atlas 83.6%、出力速度は他フロンティアモデル比 4 倍、料金は入力 $1.50 / 出力 $9.00（per 1M tok）。エージェントベンチでは GPT-5.5 超え（コーディング単体では劣後）。Antigravity CLI は Gemini CLI を完全置換。Pichai は「agentic Gemini era の始まり」と位置付け、Google のトークン処理量は月 3.2 京（2 年前比 330 倍）。

**影響**: 週初のリーク（Spark / 3.2 Flash 価格 / Cappuccino）はほぼ的中したが、実際に出たのは 3.5 Flash だった。コーディングエージェント市場で「3-6 ヶ月遅れ」と評されてきた Google が、価格・速度・エージェント基盤で一気に巻き返す構図。一方 Spark はリーク段階から「ユーザーに確認せず情報共有・購入を実行する場合がある」という fine print が論争になっており、消費者がエージェントに日常タスクを委任する習慣を持つかは未知数（TechCrunch 分析）。

**行動指針**: Managed Agents in Gemini API は「1 コールでエージェント実行環境を起動する」点で Bedrock AgentCore Runtime と直接競合する概念。AGENTS.md / SKILL.md のスキル定義は Claude Code Skills と類似しており、マルチベンダーで通用するスキル設計の参考になる。Gemini CLI 利用者は Antigravity CLI への統合に伴う移行影響を確認。

- https://9to5google.com/2026/05/19/google-io-2026-news/
- https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5/
- https://blog.google/innovation-and-ai/technology/developers-tools/managed-agents-gemini-api/
- https://techcrunch.com/2026/05/19/google-launches-antigravity-2-0-with-an-updated-desktop-app-and-cli-tool/
- https://www.cnbc.com/2026/05/19/google-ai-ultra-gemini-spark-omni.html

### 2. Anthropic、評価額・収益・企業採用の「三冠」週 — OpenAI をビジネス採用率で初逆転

**事実**: 今週 Anthropic 関連の大型ニュースが集中した。(1) **$900B〜$950B 評価で $30-50B の調達交渉**（Sequoia / Greenoaks / Altimeter / Dragoneer が各 $2B+ 出資、5/26 週クローズ見込み）。(2) 投資家向け資料で **Q2 売上 $10.9B（Q1 $4.8B から倍増）・創業初の四半期営業黒字 $559M を予測**。(3) **Ramp AI Index で企業導入率 34.4%（+3.8pt）vs OpenAI 32.3%（-2.9pt）と史上初の逆転**。(4) **CNBC Disruptor 50 で初の 1 位**（OpenAI は 2 位に後退）。(5) SpaceX の S-1 で **xAI Colossus 1 の対価が月 $1.25B（2029 年 5 月まで、年間ランレート $15B）** と判明。(6) **Andrej Karpathy（OpenAI 共同創業者・元 Tesla Autopilot 責任者）が Pre-training チームに入社**。

**根拠**: ARR は $30B 超（2025 年末 $9B から）。Claude Code はローンチ 6 ヶ月で ARR $1B 超を達成し最大の成長ドライバー。年間 $1M 以上支出する法人顧客は 1,000 社超。GitHub 公開コミットの 4% が Claude Code 生成との分析も。

**影響**: 調達成立なら OpenAI（$852B）を超え世界最高評価の AI 企業に。ただしコンピュート支出が極大（SpaceX 年 $15B + AWS Trainium2 $100B/10 年 + Microsoft Maia 200 交渉中）で、Ramp の比較では Claude は標準評価ワークロードで最高コスト（$4,811 vs ChatGPT $3,357、GLM $544）。Programmatic Credit Pool（6/15 発効、ワークロードにより 12x-175x の実効値上げとの試算）への開発者反発も継続しており、企業需要の強さと価格圧力が同居する。

**行動指針**: 6/15 の Programmatic Credit Pool 発効は Agent SDK / `claude -p` / GitHub Actions / サードパーティフレームワーク利用者に直接影響（Pro $20 / Max 5x $100 / Max 20x $200 相当の月次クレジット、繰越なし）。サブスクで Claude Code をプログラマティック運用している場合は消費量を事前見積もりすること。Bedrock 等 API 経由の利用は対象外。

- https://www.cnbc.com/2026/05/20/anthropic-revenue-explosive-growth-ipo-profitable-quarter.html
- https://www.cnbc.com/2026/05/19/2026-cnbc-disruptor-50-rankings-anthropic-no-1.html
- https://venturebeat.com/technology/anthropic-finally-beat-openai-in-business-ai-adoption-but-3-big-threats-could-erase-its-lead
- https://techcrunch.com/2026/05/20/anthropic-will-pay-xai-1-25-billion-per-month-for-compute/
- https://techcrunch.com/2026/05/19/openai-co-founder-andrej-karpathy-joins-anthropics-pre-training-team/

### 3. OpenAI、SEC に IPO 用 S-1 を機密提出 — Musk 訴訟の全面勝訴で障害除去

**事実**: OpenAI が 5/22 までに **SEC へ confidential S-1 を提出**（引受: Goldman Sachs / Morgan Stanley / JPMorgan）。想定評価額は最大 $1T（直近私募 $852B）。直前の 5/19 には **Musk の営利転換訴訟（$150B 損害賠償請求）がカリフォルニア連邦陪審の全会一致で棄却**（全請求が 3 年の出訴期限超過、審理 2 時間未満）され、IPO の法的障害が除去された。Musk は控訴を表明。

**根拠**: 上場時期は報道で「2026 年 9 月」〜「Q4 2026（Labor Day〜Thanksgiving）」と幅がある。1 月に SoftBank から $40B 調達済みで、既存投資家への流動性提供が主目的との見方。同週に **ChatGPT Ads Manager を US で全面開放**（CPC ビディング追加・最低出稿額撤廃・Dentsu/Omnicom/Publicis/WPP 連携、広告売上目標 2026 年 $2.5B → 2030 年 $100B）し、収益多角化も加速。

**影響**: Anthropic も 10 月 IPO を視野に入れており、フロンティア AI 2 社がほぼ同時に資本市場フェーズへ。「年 $10B+ のコンピュート支出」を私募だけで賄えない段階に入ったことを意味する（W19 の Musk 裁判開廷 → 今週の棄却 → S-1 提出という流れ）。広告事業の本格化で ChatGPT は ad-supported モデルへ大きく舵を切った。

**行動指針**: ベンダー選定では IPO 後の価格・提供方針の変化リスクを織り込む。OpenAI / Anthropic とも上場前後で API 価格やプラン構成が動き得るため、Bedrock 上の複数モデル等マルチプロバイダー構成を維持しておくのが安全。

- https://fortune.com/2026/05/22/openai-ipo-filing-1-trillion-may-finally-answer-these-big-questions/
- https://www.cnbc.com/2026/05/20/openai-ipo-filing.html
- https://www.npr.org/2026/05/18/nx-s1-5822366/musk-altman-openai-jury-verdict-claims-dismissed
- https://openai.com/index/new-ways-to-buy-chatgpt-ads/

### 4. Code with Claude London — Managed Agents / Claude Code に 16 新機能、Sonnet 4.8 は出ず

**事実**: 5/19-20 にロンドンで開催。**「Bring Your Own Compute」**（Managed Agents のコード実行先として Cloudflare / Daytona / Modal / Vercel を first-class サポート）、**Self-hosted Sandboxes（Public Beta）**（ツール実行を自社インフラ内で実行、オーケストレーションのみ Anthropic 側）、**MCP Tunnels（Research Preview）**（プライベートネットワーク内の MCP サーバーへインバウンド開放なし・E2E 暗号化で到達）、Claude Code の **Auto Mode / Background Sessions**（スケジュール・GitHub webhook・外部 API からの自動起動）、**Work Tree Isolation**、**Auto Memory**（コーディングスタイルや設計判断を `memory.md` に自動保存）など計 16 機能を発表。同日 **KPMG とのグローバルアライアンス**（全世界 276,000 名に Claude 展開、Azure 上の「KPMG Digital Gateway Powered by Claude」、税務・PE 領域から開始）も公表。

**根拠**: 週前半に最有力視されていた **Sonnet 4.8 GA は London でも発表されず**。5/24 時点でも Anthropic 公式の現行ラインは Sonnet 4.6 のままで、リークは npm source map 由来の非公式情報のみ（[master] は「公式リリースまで保留扱い」に訂正）。

**影響**: Self-hosted Sandboxes / MCP Tunnels は「ファイル・リポジトリ・クレデンシャルを外に出さない」というエンタープライズのデータ境界要件への回答。今週は Codex（Goal Mode GA）、Cursor（Automations 拡張）、Devin（Managed Devins）も含め、各社の「長時間自律タスク」「バックグラウンド実行」「PR レビュー統合」機能が同時並行で進化した週となった。

**行動指針**: MCP Tunnels は社内 DB・プライベート API をエージェントのツール化する際の新しい選択肢で、AgentCore Gateway との設計比較に値する。Auto Memory / Work Tree Isolation は複数セッション並列運用の標準装備になりつつあるため、Claude Code の運用手順（worktree 運用・メモリ管理）を見直す好機。次回イベントは Code with Claude Tokyo（6 月、日付はリポ間で不一致 → 改善メモ参照）。

- https://claude.com/blog/claude-managed-agents-updates
- https://www.anthropic.com/news/anthropic-kpmg
- https://claude.com/code-with-claude/london

### 5. Microsoft、社内の Claude Code ライセンスを 6/30 で打ち切り — Copilot CLI へ一本化

**事実**: Microsoft の Experiences & Devices 部門（Windows / M365 / Outlook / Teams / Surface 担当、約 12,000 名）が **Claude Code の社内利用を 6/30 期限で終了**し、GitHub Copilot CLI へ移行する。Claude Code が社内で「人気になりすぎた」ことと会計年度末のコスト削減が背景と報道。Anthropic モデル自体は Copilot CLI / M365 Copilot / Foundry 経由で利用継続可能で、外部顧客向けサービスには影響なし。

**根拠**: Windows Central / The Decoder が内部情報として報道（[industry] で 5/18 から 3 日連続トップ級扱い）。開発者からは Copilot CLI との機能差への不満も。

**影響**: 同週、GitHub Copilot 側は **GPT-5.3-Codex を Business / Enterprise の基本モデルに昇格**（GitHub 初の LTS モデル、2027/2/4 までサポート保証、Terminal-Bench 2.0 64.0%→77.3%）、**Web 版から Gemini モデルを全削除**（OpenAI / Claude に集約）、6/1 からの全プラン従量課金移行と「自社スタック集約」を加速。一方 M365 Copilot 側では Claude モデルを Word / Excel / PPT で default-on 化しており、「開発ツールは Copilot に統一、モデルはマルチベンダー」という Microsoft の二面戦略が鮮明になった。

**行動指針**: GitHub Copilot 利用者は 6/1 の AI Credits 従量課金開始・GPT-4.1 廃止・Code Review の Actions minutes 消費開始に備える。Individual プランは新規サインアップ停止・Pro からの Opus 削除など条件が流動的なため、5 月中に請求影響を確認しておくこと。

- https://www.windowscentral.com/microsoft/microsoft-cancels-claude-code-licenses-shifting-developers-to-github-copilot-cli-a-move-likely-driven-by-financial-motives
- https://the-decoder.com/microsoft-pulls-claude-code-licenses-and-pushes-developers-back-toward-its-own-ai-tool/
- https://github.blog/changelog/2026-05-17-gpt-5-3-codex-is-now-the-base-model-for-copilot-business-and-enterprise/

---

## モデル・プラットフォーム動向

### GPT-5.5 Instant がデフォルト化、GPT-5.6 の足音 — [master]
- **GPT-5.5 Instant が ChatGPT のデフォルトモデルに**（5/5〜順次展開）: GPT-5.3 Instant 比でハルシネーション 52.5% 削減（医療・法律・金融の高リスクプロンプトで計測） https://openai.com/index/gpt-5-5-instant/
- **GPT-5.6 が Codex バックエンドの内部ログに一瞬出現**: コンテキスト 1.5M tok（GPT-5.5 比 +43%）。Polymarket では 6/30 までの公開確率 92%。GPT-6 本体は Q3-Q4 2026 へ延期観測

### Claude Opus 4.7 Fast Mode / Claude Design — [master][copilot]
- **Fast Mode が Opus 4.7 に対応**（5/13-14）: 出力トークン/秒が最大 2.5 倍、品質・1M コンテキストは同一。料金は $30/$150 per 1M tok（標準の 6 倍）。Claude Code の `/fast` デフォルトも Opus 4.7 に変更
- **Claude Design**: デザイン・プロトタイプ・スライド等の視覚的成果物を協働作成する Anthropic Labs 製品（Opus 4.7 と同時ローンチ）

### オープンウェイト・推論基盤 — [industry]
- **Cohere「Command A+」公開**: エージェント向け Sparse MoE（総 218B / アクティブ 25B）。自社環境デプロイ可能でデータ主権重視のエンタープライズ向け https://gigazine.net/news/20260522-cohere-command-a-plus/
- **Cerebras が 1T パラメータ Kimi K2.6 を 981 tok/s で推論**: GPU クラウド最速比 6.7 倍。エージェント型リクエスト（10K 入力→500 出力）を 5.6 秒で完了。NVIDIA 以外の推論選択肢として存在感 https://venturebeat.com/technology/cerebras-says-its-chips-run-a-trillion-parameter-ai-model-nearly-7-times-faster-than-gpu-clouds
- **ローカル LLM の進化**: Qwen3.5（3 月）・Gemma 4（4 月）でダウンロード可能モデルの実用性が急上昇
- **中国発「Ring-2.6-1T」**: GPT-5.4 / Gemini 3.1 Pro を一部ベンチで上回るオープンモデル

### Thinking Machines「Interaction Models」 — [master]
- Mira Murati 率いる Thinking Machines がリアルタイム音声/動画/テキスト同時解釈・継続インタラクションのモデル群を公表。フロンティア各社の「modalities + real-time」戦線が拡大

---

## コーディングエージェント・開発ツール

### Claude Code 週間リリース v2.1.143 → v2.1.150 — [master][copilot]

| バージョン | 主な変更 |
|-----------|---------|
| v2.1.143（5/15） | プラグイン依存関係の強制、`/plugin` にコンテキストコスト（トークン見積）表示、`worktree.bgIsolation: "none"`、PowerShell に `-ExecutionPolicy Bypass` 既定付与 |
| v2.1.144（5/19） | `/resume` がバックグラウンドセッション対応、`/model` がセッション限定変更（`d` でデフォルト保存）、起動時 API ハング 75 秒→15 秒 |
| v2.1.145（5/19） | `claude agents --json`、OTEL に `agent_id`/`parent_agent_id`、**環境変数ベア代入の権限プロンプトバイパス脆弱性を修正**、プラグイン Discover 画面の事前内容表示 |
| v2.1.147（5/21） | **`/simplify` → `/code-review` リネーム**（effort 引数・`--comment` で GitHub PR にインラインコメント投稿）、Pinned Background Sessions（`Ctrl+T`）、auto-updater リトライ改善 |
| v2.1.148（5/22） | v2.1.147 の「Bash が全コマンド exit code 127」リグレッションを hotfix |
| v2.1.149（5/22） | **`/usage` に per-category 内訳**（skills / subagents / plugins / MCP サーバー別）、**PowerShell 権限バイパス脆弱性修正**、GFM タスクリスト描画、`allowAllClaudeAiMcps` 管理設定 |
| v2.1.150（5/23） | 内部インフラ改善のみ |

- ソース: https://code.claude.com/docs/en/changelog
- 関連: **週次上限 50% 増（〜7/13）** が Pro/Max/Team/座席型 Enterprise で継続中（5/13 発表、Codex 2 ヶ月無料への対抗とみられる）。**Programmatic Credit Pool（6/15 発効）には「downgrade dressed up as a feature」と批判記事が一斉公開**されるバックラッシュが継続 — [master]
- **Claude Code デスクトップアプリ再設計**: 並列タスク実行、セッションサイドバー、統合ターミナル/ファイルエディタ、Mac SSH 対応 — [copilot]

### OpenAI Codex — Appshots / Goal Mode GA / ロック中 Mac 操作 — [master][industry]
- **Appshots（macOS）**: 両 Command キー同時押しでフォアグラウンドアプリの画面+テキストを Codex に即添付（5/21-22）
- **Goal Mode GA**: 目標と成功基準を定義すると数時間〜数日にわたり達成まで自走。アプリ / IDE 拡張 / CLI で一般提供
- **ロック中の Mac でも Computer Use が動作**（5/22）: スマホからタスク投入→自宅 Mac で実行する非同期ワークフローが現実化。キーボード/マウス検知で即ロック復帰。**EEA/UK/スイスでは利用不可**（規制対応）で地域格差が顕在化 https://www.macrumors.com/2026/05/22/codex-use-mac-apps-when-locked/
- **Codex モバイル対応**（5/14-15）: iOS/Android の ChatGPT アプリから監視・承認・タスク起動。Free 含む全プラン。**週次アクティブ開発者 4M+**
- **OpenAI × Dell**（5/19）: Dell AI Data Platform と接続し Codex をハイブリッド・オンプレ環境に展開 https://openai.com/index/dell-codex-enterprise-partnership/
- Windows サンドボックス（firewall 駆動ネットワークブロック）、Enterprise の HIPAA 対応も追加

### xAI「Grok Build」— CLI コーディングエージェント市場に 4 社目の本格参戦 — [master][industry]
- 5/14-15 ベータ公開。自然言語からの計画立案・ファイル編集・shell 実行、**最大 8 並列サブエージェント**、基盤は Grok 4.3 beta（2M context）。Plan Mode で事前レビュー
- SuperGrok Heavy（$299-300/月）向け。$99/月 × 6 ヶ月の導入価格で早期獲得攻勢。Anthropic / OpenAI / Google に対し 1 年以上の後発だが、Colossus の GPU 資源を背景にした価格戦略が注目点
- https://x.ai/news/grok-build-cli

### Cursor — Composer 2.5・3.5 Automations・Bugbot 従量課金 — [master][copilot][industry]
- **Composer 2.5**（5/18 詳報）: Moonshot AI の Kimi K2.5（修正 MIT）ベースに RL ファインチューニング。SWE-Bench Multilingual 79.8% で Opus 4.7（≈80%）同等、**価格は入力 $0.50/M tok と Opus 4.7 の 1/30**。xAI 提携で Colossus 2 を使った独自大規模モデルも訓練中
- **Cursor 3.5（5/20）**: Automations を Agents Window に統合、マルチリポ / リポなし Automations、PR レビュー体験刷新（Reviews/Commits/Changes タブ）
- **Cursor 3.4（5/13）**: クラウドエージェント開発環境（マルチリポ・Dockerfile ベース・監査ログ）、フルスクリーンタブ
- **Bugbot**: 席料（$40/seat）廃止→従量課金へ。6/8 以降の更新で適用。Jira / Microsoft Teams から `@Cursor` でクラウドエージェント起動も追加
- **2026 Gartner Magic Quadrant for Enterprise AI Coding Agents で「Leader」評価**（5/22）
- https://cursor.com/changelog

### GitHub Copilot — LTS モデル導入とプラン再編 — [copilot][master]
- **GPT-5.3-Codex が Business/Enterprise の基本モデルに**（5/17）: GitHub 初の LTS モデル（2027/2/4 まで 12 ヶ月保証）。エージェントコーディングで 25% 高速化。GPT-4.1 は 6/1 廃止
- **GitHub Copilot App（Technical Preview、5/14）**: エージェント駆動開発特化のスタンドアロンデスクトップアプリ（Win/macOS/Linux）。並列セッション（独立 worktree）、Agent Merge、Inbox 型 UI
- **Web 版モデル整理（5/20）**: Gemini モデル全削除、GPT-5.2 Codex / GPT-5.4 nano も削除
- **Individual プラン変更**: Pro/Pro+/Student の新規受付停止、Pro から Opus 削除（Pro+ は継続）。6/1 から全プラン AI Credits 従量課金
- **Copilot CLI v1.0.49〜v1.0.51**: `/chronicle search`、`/rubber-duck`（独立批評）、`--session-id` 再開、`/security-review`（実験的）、ステータスライン表示
- **Cloud Agent 設定監査 REST API（5/18）** / JetBrains IDEs に CLI エージェント統合（5/13）

### Devin — 価格大幅改定と Managed Devins — [copilot][master]
- **価格改定: Pro $500→$20/月、Max $200/月**。PR マージ率は年次比較で 34%→67% に向上
- **Managed Devins**: メインセッションから複数 Devin を並列起動し、コーディネーター役が進捗監視・コンフリクト解消・結果統合 https://cognition.ai/blog/devin-can-now-manage-devins
- **Devin Cloud**（ローカル計画→クラウド実行、デフォルトモデル SWE-1.5）、v3 API GA（RBAC）、Datadog Remote MCP Server、Okta IdP グループ管理

### 新興ツール・OSS・コミュニティ — [industry]
- **VS Code「Agent Window」プレビュー**: エージェントごとに独立ウィンドウを割り当て並行開発のコンテキストを分離 https://www.publickey1.jp/blog/26/vs_codeaiagent_window.html
- **Raindrop「Workshop」**: AI エージェント向け OSS ローカルデバッガ（MIT）。全トークン・ツールコール・判断をリアルタイム表示、15+ フレームワーク対応。Claude Code がトレースを読んで eval を自動作成する自己回復ループも構築可能
- **OpenHuman**: ローカルファーストの個人 AI アシスタント。Product Hunt #1、GitHub 8,000+ スター
- **Browser-Use**: ブラウザ自動操作 OSS（81,200+ スター、WebVoyager 89.1%）
- **GitHub Trending**: 「skills」を含むリポジトリがトップ 20 中 5 つ。mattpocock/skills が急伸（+1,696★/週）、OpenClaw 210K+★・Hermes Agent 105K+★ が継続トップ
- **Product Hunt**: Contextberg（MCP 対応 AI メモリ）、PollyReach（エージェントに電話機能）等、エージェント周辺ツールがトレンド継続

---

## Microsoft 365 Copilot / Copilot Studio / Power Platform

### Copilot Chat ライセンス変更が 5/16 実施 — [copilot]
- 2,000 シート超の組織で、未ライセンスユーザーの Word/Excel/PowerPoint/OneNote 内 Copilot Chat が利用不可に。小規模組織は standard access に格下げ。「Copilot Chat (Basic)」「M365 Copilot (Premium)」の二層ラベルを導入。Outlook のメール・カレンダーアシスタンスはライセンス不問で継続
- https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-licensing

### Office 365 コネクタの Teams 統合が完全廃止（5/18-22 ロールアウト） — [copilot][master]
- 5/18 から全テナントで順次無効化。Workflows webhook 未移行のコネクタは動作停止。MessageCard・プライベートチャネルは Workflows 対応済み、インタラクティブボタンは Adaptive Cards への移行が必要（MC1181996、SFI の一環）

### リリース管理・モデル提供の変更 — [copilot]
- **三層リリースモデル（Frontier / Standard / Deferred）開始**: Copilot の機能展開を 3 段階管理。Deferred は最大 30 日遅延、100 ユーザーまで例外指定可。admin center > Copilot > Settings で設定
- **Claude モデルが Word/Excel/PPT でデフォルトオンに**: 従来のオプトインから変更。Word での GA は 5 月下旬予定
- **Researcher「Critique & Council」**: GPT 起草→Claude レビュー（Critique）、両モデル回答の横並び比較（Council）。Frontier で提供
- **Word Legal Agent（Frontier、米国）**: 契約レビュー・赤線入れ・プレイブック照合を Copilot in Word で実行
- **Copilot Calendar Agent**: 自然言語ルール（「1on1 は全承認」等）でカレンダー操作を自動実行する真のエージェント型機能
- そのほか: Outlook メールグラウンディング、Copilot Chat 内 PDF 直接表示、SharePoint「AI Charts」「File Actions with AI」世界展開、Planner 統合

### Edge for Business「Browsing with Copilot」限定パブリックプレビュー（5/20） — [copilot]
- Copilot がサイト操作・フォーム入力・マルチステップタスクを自動実行するエージェント型ブラウジング。管理者ポリシーで対象サイトをスコープ制御、Purview DLP 適用。パスワード/カード入力時は自動停止。GA は 2026 年下半期
- https://blogs.windows.com/msedgedev/2026/05/20/new-in-edge-for-business-ai-for-work-safe-from-day-one/

### Copilot Studio — Computer Use GA・音声エージェント運用 — [copilot]
- **Computer Use が全商用リージョンで GA**: ビジョン+推論でブラウザ・デスクトップアプリの UI を直接操作。レイアウト変更に自動適応し、API のないレガシーシステム自動化を簡素化 https://techcommunity.microsoft.com/blog/copilot-studio-blog/computer-using-agents-in-microsoft-copilot-studio-are-now-generally-available/4519427
- **リアルタイム音声エージェントの大規模運用ガイド公開（5/19）**: ビルダー→ビルド→リリース→ランタイム→ライフサイクルの 5 段階ガバナンスフレームワーク。Hold & Resume（通話保留・再開）も追加
- **GPT-5.5 Reasoning (Deep) を実験モデルとして追加**、GPT-5.5 Instant も展開中
- A2A（Agent-to-Agent）プロトコル GA、REST API 経由のエージェント評価（CI/CD 統合）、マルチターン会話テスト（Preview）、Bing Custom Search のナレッジソース対応
- 予定: Question Themes Analysis GA（5/29）、Voice Agent Evaluation GA（5/31）、CLI GA（5/31）

### Agent 365 — May 2026 アップデート — [copilot]
- 概要ダッシュボード（登録エージェント数・リスクシグナル等）が利用可能に。**AWS Bedrock / Google Cloud との Registry Sync** でマルチクラウドのエージェントを自動検出・インベントリ管理。Microsoft Defender によるエージェント脅威のランタイム検出。6 月に Context mapping・Intune/Defender Public Preview 予定
- https://techcommunity.microsoft.com/blog/agent-365-blog/what%E2%80%99s-new-in-agent-365-may-2026/4516340

### Power Platform May 2026 Feature Update（5/14 公開） — [copilot]
- **Power Fx User Defined Types GA**（v3.26044、新規アプリでデフォルト有効）
- **カスタム MCP ツール + Fluent UI ウィジェット（Public Preview）**: モデル駆動アプリに MCP 駆動の対話を統合
- **InfoPath → Canvas Apps 移行支援 GA**: Canvas Authoring MCP Server + PowerCAT Skill で GitHub Copilot / Claude Code 等から AI 支援マイグレーション
- Data Grid Modern Control（Public Preview、10 万件以上対応）、Grid Container GA、Generative Pages 強化、Power Automate Self-Healing（Preview）、Desktop Flow Testing GA、ソリューションインポート最大 40% 高速化、Copilot-ready 環境テンプレート、**Entra Agent Users（Preview、エージェント専用認証 ID）**
- Power Pages が GitHub Copilot CLI / Claude Code プラグインによるサイト作成に対応
- https://www.microsoft.com/en-us/power-platform/blog/2026/05/14/whats-new-in-power-platform-may-2026-feature-update/

---

## エンタープライズAI・提携

### Anthropic の提携網が一気に拡大 — [master][copilot][industry]
- **KPMG**（5/19、ハイライト 4 参照）: 276,000 名展開・Digital Gateway・PE 向け優先パートナー
- **SAP Business AI Platform**（SAP Sapphire）: Joule エージェントに Claude の推論を統合。S/4HANA / SuccessFactors / Ariba 横断のマルチステップワークフロー、MCP 経由で SAP ビジネスコンテキストにアクセス https://news.sap.com/2026/05/sap-anthropic-to-bring-claude-sap-business-ai-platform/
- **PwC 拡大**（5/14）: Joint Center of Excellence 設立、30,000 人の Claude 認定プログラム
- **Gates Foundation**（5/14）: グローバルヘルス・教育・経済モビリティに 4 年 $200M（助成金+クレジット+技術支援）
- **Claude for Small Business**（5/13）: QuickBooks / PayPal / HubSpot 等に接続する 15 ワークフロー・15 スキル・8 コネクタ。追加料金なし、全米 10 都市ワークショップツアー
- **Apple iOS 27**: Apple Intelligence にサードパーティモデル選択機能を導入へ。Google（Gemini）と Anthropic との連携をテスト中、今秋リリース予定 — [industry]
- **Microsoft Maia 200 チップ利用を交渉中**（5/21 CNBC）: AWS Trainium2（$100B/10 年）・SpaceX Colossus 1 に続く計算資源多角化。交渉は初期段階 — [industry]

### OpenAI のエンタープライズ・コンシューマ展開 — [master][industry]
- **Workspace Agents**: ChatGPT Business/Enterprise/Edu 向けの常時稼働チーム自動化エージェント（Slack 統合・スケジュール実行・承認フロー）。5/6 からクレジットベース課金
- **ChatGPT for Personal Finance**（5/15、Pro プレビュー）: Plaid 経由で米 12,000+ 金融機関に接続し支出分析・資産計画
- **ChatGPT for PowerPoint ベータ**: スライド自動生成・編集。Copilot for PowerPoint との競合領域が拡大 — [industry]
- **ChatGPT for Excel / Google Sheets** グローバル展開、**OpenAI Deployment Company** 設立（企業の AI 構築・デプロイ支援）

### 業務エージェントの導入と現実 — [industry][copilot]
- **Salesforce Agentforce Operations GA**（4/29〜）: バックオフィス業務をエージェント駆動ワークフロー化。サイクルタイム最大 70% 短縮・手動作業 80% 削減を主張
- **Workday Sana Self-Service Agent in M365 Copilot**: HR/Finance タスク（休暇申請・経費確認）を Copilot Chat 内から自然言語で実行。追加ライセンス不要
- **Starbucks が AI 在庫管理ツールを 9 ヶ月で廃止**: 計数エラー多発で手動回帰。Writer 調査では「有意な ROI を報告できた企業は 29%」— AI 導入が必ずしも ROI を生まない実例 https://gigazine.net/news/20260522-starbucks-abandons-ai-inventory-tool/
- **Notion Developer Platform**（5/13）: Workers / External Agent API / `ntn` CLI でワークスペースを「エージェントのハブ」に再定義 — [master]
- **Dell「Deskside Agentic AI」**: NVIDIA GB10/GB300 搭載のローカルエージェント実行専用デスクトップ PC。エッジ AI エージェントの新カテゴリ — [industry]

---

## 資金調達・M&A・市場・雇用

### Anthropic、Stainless を $300M+ で買収 — SDK/MCP 生成基盤の囲い込み — [master]
- 各社の公式 SDK・CLI・MCP サーバを自動生成してきた Stainless を買収（5/19-20 公表）。**9/1 で Stainless プラットフォームを閉鎖**し、OpenAI（Python/Node/Java/Go/Ruby クライアントが Stainless 生成）・Google・Cloudflare 等は代替手段の構築を迫られる。既存生成 SDK の所有権・改修権は顧客に残る
- The Register 等は「使うためでなく、敵に使わせないための買収」と評価。MCP コネクタの更新速度・品質で実質的な参入障壁を築く動き
- https://www.anthropic.com/news/anthropic-acquires-stainless

### AI インフラ・スタートアップへの大型資金流入 — [industry]
- **AI エージェント向け検索**: Exa Labs が $250M（評価額 $2.2B、a16z 主導）、Parallel Web Systems（元 Twitter CEO Parag Agrawal 創業）が $100M（評価額 $2B、Sequoia 主導）。Tavily 等も含めエージェントのウェブアクセス・インフラ層が VC の注目分野に https://techcrunch.com/2026/05/20/ai-search-startups-are-blowing-up/
- **Recursive Superintelligence**: 元 You.com 創業者 Richard Socher 率いる自己改善 AI スタートアップが $650M 調達でステルス解除（評価額 $4.65B、GV/Greycroft 主導、NVIDIA・AMD 参加）

### AI 起因の雇用再編が加速 — [industry]
- **Meta が 8,000 人（約 10%）解雇 + 7,000 人を AI 職へ配置転換**（5/20 通知開始）: 未充足 6,000 ポジションも凍結。2026 年 CapEx を最大 $145B に上方修正。マウストラッキング導入には従業員 1,000 人超が反対署名
- **Cloudflare 1,100 人（20%）・Upwork 145 人（24%）削減**: Cloudflare は社内 AI 利用が 3 ヶ月で 600% 増加し「AI が 1,100 の職を不要にした」と明言。5 月前半だけで AI 関連レイオフ 38,000 人超
- **Microsoft AI CEO Suleyman「18 ヶ月以内にほぼ全てのホワイトカラー業務が AI 自動化される」**: 一方 METR 調査では AI ツール使用で開発タスクが 20% 長くなったとの結果もあり乖離を指摘する声

### 市場データ — [industry]
- **Similarweb 3 月データ**: ChatGPT のチャットボットシェアが 56.72% に低下（2025 年初頭 77.43%）、Gemini は 25.46% に急伸。AI 検索リファラルは月 13 億回
- **McKinsey 調査: CAIO 設置率が 26% → 76% に急増**（2025→2026）
- **生成 AI 料金早見表（5 月版）**: 主要 8 サービスの標準プランは $20 前後で横並び。Google AI Plus（月 1,200 円）新設、6 サービスが円建て価格を採用。選択基準は「価格」から「用途との相性」へ

---

## セキュリティ

### GitHub 内部 3,800 リポジトリ流出 — VS Code 拡張「Nx Console」改ざんが原因 — [industry]
- 5/18 に Nx Console（220 万インストール）のトロイの木馬版が VS Code Marketplace に 18 分間公開され、**1Password・Claude Code 設定・npm・GitHub・AWS 認証情報を窃取**するペイロードを実行。GitHub 内部 3,800 リポジトリが流出し、脅威アクター TeamPCP が販売を試行。OpenAI・Grafana Labs への影響可能性も報道。該当バージョン削除・シークレットローテーション済み
- 開発マシンの拡張機能サプライチェーンが AI 開発のクレデンシャル（Claude Code 設定等）を直撃した事例。拡張の自動更新ポリシーとシークレット管理の見直しを推奨
- https://www.bleepingcomputer.com/news/security/github-confirms-breach-of-3-800-repos-via-malicious-vscode-extension/

### AI による脆弱性発見の「産業化」が進行 — [master][copilot][industry]
- **Anthropic Project Glasswing 初月成果（5/22）**: Claude Mythos Preview + 約 50 パートナーで**高〜致命的脆弱性 10,000+ 件を発見**。Cloudflare 約 2,000 件（高/致命的 400）、Mozilla は Firefox 150 で 271 件を特定・修正。米政府含む「critical partners」への追加展開を計画 https://www.anthropic.com/research/glasswing-initial-update
- **Claude Security パブリックベータ**: Opus 4.7 でコードベースをスキャンし修正提案。ローンチ 3 週間で 2,100+ 件の脆弱性を修正 — [copilot]
- **OpenAI Daybreak**（5/12 公表）: Codex Security + GPT-5.5 で脅威モデル構築→検出→パッチ提案を自動化。Akamai / Cisco / CrowdStrike / Palo Alto 等 8 社が Trusted Access パートナー。Mythos との差別化として「一般公開」を強調 — [industry]
- **Microsoft MDASH**: 100 超の専門 AI エージェント群で Windows 脆弱性を自動検出。5/12 Patch Tuesday で 16 件（うち Critical 4 件）を発見 — [industry]

### Claude Code の権限バイパス脆弱性 2 件が同週修正 — [master][copilot]
- v2.1.145: 非許可リスト環境変数のベア代入が auto-approve される権限プロンプトバイパスを修正
- v2.1.149: PowerShell の権限バイパス（prefix/wildcard allow rules 含む）を修正。`PWD`/`OLDPWD`/`DIRSTACK` 追跡の権限解析ギャップも解消
- 利用者は最新版への早期アップデート推奨（v2.1.147 利用者は Bash リグレッションのため v2.1.148+ 必須）

---

## 研究・規制

### OpenAI 内部モデルが 80 年未解決の Erdős 予想を自律的に反証 — [industry]
- Paul Erdős が 1946 年に提起した平面単位距離問題で、内部推論モデルが代数的整数論を用いた無限構成族を発見し予想を反証（5/20）。Fields 賞受賞者 Tim Gowers が「AI の数学的マイルストーン」と評価、著名数学者が独立検証済み。2025 年 10 月の「Erdős 問題解決」誤報からのリベンジ
- https://openai.com/index/model-disproves-discrete-geometry-conjecture/

### Jack Clark（Anthropic 共同創業者）のオックスフォード講演 — [industry]
- 予測: (1) 12 ヶ月以内に AI がノーベル賞級発見に貢献 (2) 18 ヶ月以内に AI のみで運営される企業が数百万ドル売上 (3) 2028 年末までに AI が後継モデルを自律訓練する確率 60% 超。「変化は不可避、自律性は不可避ではない」

### 学術・規制の引き締め — [industry]
- **Arxiv**: LLM 出力を未検証のまま論文に含めた著者に 1 年間の投稿禁止処分
- **EU**: AI 生成コンテンツ透明性義務の実装猶予を 6→3 ヶ月に短縮、期限は 2026/12/2
- **Linux Foundation「AGNTCon + MCPCon Japan」が 9/10-11 に渋谷で開催決定**: エージェント / MCP 専門カンファレンスのアジア拠点。CFP 受付中 https://events.linuxfoundation.org/agntcon-mcpcon-japan/

---

## 来週の注目予定

- **5/25**: Outlook Lite（Android）完全廃止（MC1276508）
- **5/26 週**: Anthropic $30B 調達ラウンドのクローズ見込み
- **5/26**: Google Forms ヘッダー画像オプション Scheduled Release 展開開始
- **5/29**: Copilot Studio Question Themes Analysis GA 予定
- **5 月下旬**: M365 Copilot 三層リリースモデル適用開始 / Claude in Word GA 予定
- **5/31**: Copilot Studio CLI GA 予定（Power Platform CLI 拡張）/ Voice Agent Evaluation GA 予定
- **6/1**: GitHub Copilot 全プラン従量課金（AI Credits）開始・GPT-4.1 廃止・Code Review の Actions minutes 消費開始
- **6 月**: Gemini 3.5 Pro 提供予定 / Agent 365 の Context mapping・Intune/Defender Public Preview
- **6/5-6 または 6/10**: Code with Claude Tokyo（リポ間で日付が不一致 → 改善メモ参照）
- **6/8**: Cursor Bugbot 従量課金への移行適用開始
- **6/15**: Anthropic Programmatic Credit Pool 発効 / M365 Agent Registry API 旧版停止（MC1297981）
- **6/30**: Microsoft E+D 部門の Claude Code 社内利用期限
- **7/13**: Claude Code 週次上限 50% 増の終了予定日（恒久化か縮小かは未表明）
- **9/1**: Stainless プラットフォーム閉鎖（OpenAI / Google 等の SDK 生成が停止）
- **9/10-11**: AGNTCon + MCPCon Japan（東京・渋谷）
- **9 月〜Q4 2026**: OpenAI IPO 想定時期（報道に幅あり）/ 2026 年下半期: Edge for Business「Browsing with Copilot」GA
- **10 月**: Anthropic IPO 視野

---

## 改善メモ

### 3 リポ共通
- **WebFetch 403 が引き続き恒常化**（2026-04-02〜）: Anthropic / OpenAI / Google / Cursor / Releasebot / RSS 全般に加え、今週は **learn.microsoft.com・techcommunity・GitHub Blog にも 403 が拡大**（[copilot] 5/20-24 で確認）。3 リポとも WebSearch プライマリ運用が常態化しており、各 `daily-sources.md` の備考を「恒常」表記へ簡略化・WebSearch のプライマリ格上げ提案が複数回出ている（反映閾値到達）
- **Claude Code Changelog（code.claude.com/docs）は唯一 WebFetch 安定**。最優先ソースとして信頼性が高い

### リポ別の引き継ぎ
- [master] **5/9〜5/19 の日次収集が停止**し、5/20 ダイジェストで一括カバーした（5/18-19 は個別生成あり）。収集タスクの死活監視を改めて推奨
- [master] **Sonnet 4.8 はリーク報道のみで公式未発表**（5/24 時点、公式現行は Sonnet 4.6）。リーク情報は「公式発表前」と明示し、公式リリースまで保留扱いとする運用を徹底
- [master] xAI 専用の監視セクション追加、「金融・調達ニュース系」ソースのサブセクション追加が 2 回以上提案済み（`rules` 反映候補）
- [copilot] Agent 365 ブログ（techcommunity.microsoft.com/blog/agent-365-blog）を daily-sources.md に追加検討。Tech Community「What's New in M365 Copilot | May 2026」は 5/24 時点で未公開、月末にフォローアップ
- [industry] Snap × Perplexity $400M 提携破談の報道は詳細未確認のまま、次回フォロー推奨

### リポ間の矛盾（要確認）
- **Code with Claude Tokyo の開催日**: [master] は「6/10」、[copilot] は「6/5-6」と記載が分かれる。公式ページでの確認が必要
- **OpenAI IPO の目標時期**: [master] は「Q4 2026（Labor Day〜Thanksgiving）」、[industry] は「2026 年 9 月」。本サマリーは「9 月〜Q4」と幅を持たせて記載
- **ChatGPT 広告の撤廃された最低出稿額**: [master] は「当初 $200K」、[industry] は「$50K」。撤廃された事実は一致
- **Google AI Ultra の価格改定**: [master] は「$100/月ティアを新設し旧 $250 プランは $200 に値下げ」、[industry] は「$250→$100/月に値下げ」。$100/月の新価格帯が出た点は一致するが旧プランの扱いが不一致
- **Anthropic Q2 業績の時制**: [industry] 5/24 は「初の四半期営業黒字を達成」と記載するが、5/23 の両リポでは「投資家向け資料での予測」。Q2 は未了のため本サマリーは「予測」として記載
- Claude Code のバージョン誤記（[master] 5/22 の v2.1.146 → 実際は v2.1.147）は 5/23 ダイジェストで訂正済み。本サマリーは訂正後の番号で記載
