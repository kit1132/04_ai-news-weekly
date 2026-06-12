# AI ニュース週次サマリー — 2026-W23（2026-06-01 〜 2026-06-07）

> 入力: 取得成功 21 / 21
> 生成日時: 2026-06-12（JST・バックフィル生成）

## 今週のハイライト

### 1. GitHub Copilot 従量課金が全面施行 — 「請求ショック」で定額制ツールへの移行検討が拡大

**事実**: 6/1 に GitHub Copilot 全プランが Usage-Based Billing（AI Credits 制、1 クレジット = $0.01）へ移行した。月額は据え置き（Pro $10 / Pro+ $39 / Business $19 / Enterprise $39）で同額相当のクレジットを付与し、コード補完・Next Edit Suggestions は消費対象外。同日付で GPT-4.1 が Copilot 全体験から廃止（推奨後継 GPT-5.5）、Code Review は GitHub Actions 分数消費に変更された。Pro / Pro+ / Student / Max の新規申込は「エージェントワークフローによるコンピュート需要急増」を理由に週末時点でも停止が続いた。

**根拠**: 週初の施行から反発が日を追って拡大した。GitHub 公式 Discussion に 900+ downvote / 400+ コメント、TechCrunch「What a joke」・The Register「Angry devs vow to flee」・Visual Studio Magazine「Copilot Billing Shock」（6/4）と続報が連鎖。実コスト事例は「Pro+ ユーザーが 2 時間で月間クレジットの 8% 消費」「エージェントセッション 1 回で $30〜40」「5 日間で $906.71」「月 $29 → $750 / $50 → $3,000 の試算」など。エージェントモードがルーチン作業（全リクエストの 60% 超）に高額推論モデルを適用する構造が根本原因と分析されている。

**影響**: エージェント中心のヘビーユーザーは 10〜50 倍のコスト増になり得る。定額制の Claude Code / Devin Desktop、無料系の Continue.dev / Cline、OpenRouter 等への移行ガイド記事が急増し、「Copilot 代替」が定点テーマ化。8 月の Project Polaris 既定モデル化と合わせて「料金とモデル両面の不確実性が高い」との評価が定着しつつある。Cursor Bugbot（6/8〜）も従量課金化するなど、AI コーディングツール全体が従量課金へ向かう流れの中で、定額制を維持する Claude Code との TCO 比較が業界共通の論点になった。

**行動指針**: Copilot を継続利用する場合は、追加支出上限（$0 設定で超過課金なし）とユーザーレベル予算設定（GA 済み）を必ず構成する。エージェントモードを使うルーチン作業のモデル選択を見直し、Claude Code Max 等の定額制と TCO を再計算しておく。

- https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/
- https://techcrunch.com/2026/05/30/what-a-joke-github-copilots-new-token-based-billing-spurs-consternation-among-devs/
- https://visualstudiomagazine.com/articles/2026/06/04/copilot-billing-shock-hits-developers.aspx
- https://www.theregister.com/ai-and-ml/2026/06/02/github-copilot-users-threaten-exit-as-metered-billing-kicks-in/5249826

### 2. Microsoft Build 2026 — Project Polaris と「Windows = エージェント OS」化で脱 OpenAI が実装段階に

**事実**: 6/2-6/3 に San Francisco で開催。中心テーマは「Windows は人間ユーザーだけのプラットフォームではない、Agents が first-class citizen」。主要発表は、(1) **Project Polaris** — Microsoft 自社開発のコーディングモデル（MoE）。2026 年 8 月から GitHub Copilot の既定モデルを GPT-4 Turbo から置換、3 ヶ月間は旧モデルへフォールバック可能。「Claude Code への直接対抗」を公言。(2) **MAI モデル群** — 初の自社推論モデル MAI-Thinking-1（35B、蒸留なし）、MAI-Code-1-Flash（VS Code の model picker に rollout 開始）、MAI-Image-2.5 等 計 7 モデル。(3) **GitHub Copilot Workspace GA / Copilot Multi-Agent for VS Code GA / Copilot App（デスクトップ）テクニカルプレビュー**。(4) **Windows Agent Framework v1.0 の MIT オープンソース化、WSL 3（GPU/NPU passthrough）、Foundry Local GA、Aion 1.0 Plan（14B、Windows 同梱）**。(5) **Azure Agent Mesh**（Azure / AWS / GCP / オンプレを統一ガバナンスで連携、Q4 2026 GA 目標）、**MXC**（AI エージェント向け OS レベルサンドボックス、OpenAI / NVIDIA が採用パートナー）、**Project Solara**（エージェント特化デバイスプラットフォーム、Target / CVS / Best Buy がパイロット）、**Microsoft Scout**（常時稼働の「Autopilot」エージェント、Private Preview）、**Work IQ APIs**（6/16 GA 予定）。

**根拠**: 公式ブログ・基調講演と各社報道（Engadget / Tom's Guide / CNBC / VentureBeat 等）。MAI-Thinking-1 は blind eval で Sonnet 4.6 超えと自社主張。Foundry のモデルカタログは 3,000〜11,000+ モデル規模で OpenAI / Anthropic / OSS を同等扱い。

**影響**: GPT-4.1 廃止 + Polaris + MAI + Gemini 3.x 追加で、Copilot の「OpenAI 一強脱却」がモデル選択肢ベースで実装段階に入った。AWS の OpenAI 受け入れ（ハイライト 4）と同週に起き、AI コーディング市場は「Anthropic vs OpenAI vs Cognition vs Microsoft」の 4 極化が鮮明化。一方で週末には MAI モデルの学習データに非ライセンス Web データ（Common Crawl 等）の使用が判明し、「エンタープライズグレードのクリーンデータのみ」という従来主張との矛盾が報じられた。

**行動指針**: Copilot 利用組織は 8 月の Polaris 自動切替に備え、3 ヶ月のフォールバック期間をテスト計画に組み込む。ローカル AI は WSL 3 + Foundry Local の組み合わせで「Windows 上のローカル LLM」が現実解になったため、検証環境の選択肢として把握しておく。

- https://chatforest.com/builders-log/microsoft-build-2026-recap-windows-agent-platform-project-polaris-copilot-workspace/
- https://www.techtimes.com/articles/317596/20260602/github-copilot-replaces-gpt-4-project-polaris-ships-multi-agent-vs-code-build.htm
- https://devblogs.microsoft.com/foundry/foundry-local-ga/
- https://www.geekwire.com/2026/inside-microsofts-project-solara-a-new-platform-for-devices-that-run-ai-agents-instead-of-apps/
- https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/02/introducing-microsoft-scout-your-always-on-personal-agent/
- https://the-decoder.com/microsoft-pulls-claude-code-licenses-and-pushes-developers-back-toward-its-own-ai-tool/

### 3. Anthropic が IPO 用 S-1 を機密申請 — 評価額 $965B・ARR $47B で「$1T 級 IPO レース」を先行

**事実**: 6/1、Anthropic が SEC に Form S-1 を機密提出した。5/28 完了の Series H $65B 調達（post-money $965B）で OpenAI を評価額で逆転した直後の動き。年間収益ランレートは $47B（前年約 $10B から約 5 倍）。株数・価格帯・時期は未定だが、報道では「目標評価額 $1.75〜1.8T・最大 $75B 調達」の観測や「10 月上場視野」「SpaceX 方式なら 8 月中旬上場も可能」とのシナリオが出ている。

**根拠**: CNBC / Fortune / TechCrunch / Washington Post / Anthropic 公式。週中には Polymarket で「Anthropic が OpenAI より先に IPO する確率 78%」。企業導入面でも Ramp AI Index（5 月）で Anthropic 34.4% vs OpenAI 32.3% と初逆転、Similarweb 4 月で Claude のトラフィックシェアが 6.02% → 8.2% に上昇しており、Claude Code 等エンタープライズツールが収益を牽引している。

**影響**: OpenAI・SpaceX も機密申請を控えるとされ、「同年に 3 社が $1T 超評価で上場」という史上初のシナリオが現実味を帯びた。週内の Anthropic は IPO 申請に加え、Project Glasswing 拡大（セキュリティ）、Partner Network 階層化（GTM）、「pause button」提案（政策）と矢継ぎ早に動き、「商用 + 政府/重要インフラ + パートナー網 + 安全規制」のフルスタック戦略として読まれている。

**行動指針**: 利用者側の直近の実務イベントは 6/15 の Programmatic Credit Pool 施行と Claude Sonnet 4 / Opus 4 の API 退役。Agent SDK / `claude -p` / Claude Code GitHub Actions を使うワークフローは、サブスクとは別の月次クレジットプール（Pro $20 / Max 5x $100 / Max 20x $200、API レート従量・繰越なし）で消費される前提に組み替えておく。

- https://www.cnbc.com/2026/06/01/anthropic-ipo-s1-prospectus.html
- https://fortune.com/2026/06/01/anthropic-confidentially-files-ipo-965-billion-valuation/
- https://www.anthropic.com/news/confidential-draft-s1-sec
- https://ramp.com/leading-indicators/ai-index-may-2026

### 4. OpenAI モデルと Codex が Amazon Bedrock で提供開始 — 「Bedrock = Claude 専用窓口」の前提が崩壊

**事実**: 6/1 発表（6/2-3 で展開報道）。GPT-5.5 / GPT-5.4 / Codex が Amazon Bedrock で GA。料金は OpenAI ファーストパーティと同額（マークアップなし）で AWS 既存コミットメントに充当可能、Commercial / GovCloud 両リージョン対応。Codex の App / CLI / IDE すべてを Bedrock 推論にルーティングでき、IAM / VPC isolation / 暗号化が AWS 標準で適用される。将来計画としてサイバー防御向け「Daybreak」（Codex Security）も Bedrock 提供予定。

**根拠**: OpenAI / AWS / Amazon 公式発表。GPT-5.5 は同週に Microsoft Foundry でも GA（$5/M 入力・$30/M 出力）しており、OpenAI はクラウド配信網を一気に広げた。

**影響**: AWS Bedrock の「Anthropic 単独パートナー」体制が崩れ、エンタープライズは Claude / GPT-5.5 / Codex を同一 IAM・VPC・課金で並列調達できる構図になった。Anthropic = AWS/GCP、OpenAI = Azure + AWS という構図から「OpenAI の 3 大クラウド全制覇」へ。Anthropic の IPO 直前というタイミングもあり、AWS 顧客の AI 予算配分が動く可能性が指摘される。

**行動指針**: Bedrock 利用者はモデル選定を「Claude 前提」から「同一ガバナンス下のマルチモデル比較」へ更新する。Claude Code 側も v2.1.166 で `fallbackModel`（最大 3 段フォールバック）が入り、マルチモデル前提の resilience 設計が現実的になった。

- https://openai.com/index/openai-frontier-models-and-codex-are-now-available-on-aws/
- https://aws.amazon.com/blogs/aws/get-started-with-openai-gpt-5-5-gpt-5-4-models-and-codex-on-amazon-bedrock/
- https://www.aboutamazon.com/news/aws/bedrock-openai-models

### 5. Anthropic「When AI builds itself」公開 — 自社コードの 80% 超を Claude が執筆、「pause button」を提案

**事実**: 6/4-5、Anthropic Institute が recursive self-improvement（AI が自身の後継を設計・訓練する段階）が「予想より早く来る可能性」を主張する長文ポジションペーパーを公開。根拠データとして、2026 年 5 月時点で Anthropic にマージされるコードの 80% 超を Claude が執筆（2025 年初は一桁台）、エンジニア当たりコード量は 8 倍、Mythos Preview 利用の社内 130 名調査で生産性約 4 倍、を提示。政策提案として「政府 + 主要 AI ラボが協調して停止できる『pause button』体制の準備」を求めつつ、「人間がゴール設定・評価を担う」「不可避ではない」と限界も明記した。

**根拠**: anthropic.com/institute 原文と Bloomberg / Fortune / Axios / Engadget 報道。同週に Anthropic は 1 年分の AI サイバー脅威分析（832 停止アカウントを MITRE ATT&CK にマッピング、中高リスク行為者の AI 利用率 33% → 56%）も公開しており、データ裏付けを伴う発信が続いた。

**影響**: IPO 提出済みの Anthropic が「商用最強」と「安全規制リーダー」を同時に主張する戦略文書と位置付けられ、Build 直後に商用攻勢をかける Microsoft / OpenAI との「政策 × 商用」の主導権争いが今週の主軸になった。AI 生成コード比率の高さは Anthropic 固有ではなく、Remote（提出コードの 85%+ が AI 生成）、Uber（コミットの 70% が AI 起源）、Cognition（Devin がコードベースの 89% を執筆）と業界横断で報告されている。

**行動指針**: AI 生成コードが多数派になる前提で、コードレビュー・セキュリティ検証パイプラインの再設計（自動セキュリティレビュー、レビュー体制の人間側ボトルネック解消）を検討する。生産性指標も「人が書いた行数」ベースから見直しが必要になる。

- https://www.anthropic.com/institute/recursive-self-improvement
- https://www.bloomberg.com/news/articles/2026-06-05/anthropic-calls-for-ai-pause-button-to-let-humans-take-stock
- https://fortune.com/2026/06/05/anthropic-ai-pause-development-recursive-self-improvement/
- https://www.anthropic.com/news/AI-enabled-cyber-threats-mitre-attack

## 開発ツール（AI コーディング）

### Claude Code 週間アップデート（v2.1.158 → v2.1.167） — [master][copilot]

今週は 8 リリース（v2.1.159 は内部基盤改善のみ）。セキュリティ強化とエンタープライズガバナンス機能が中心。

| バージョン | 日付 | 主な変更 |
|-----------|------|---------|
| v2.1.158 | 5/30 | Auto mode が Bedrock / Vertex / Foundry でも利用可能に（Opus 4.7/4.8、`CLAUDE_CODE_ENABLE_AUTO_MODE=1`） |
| v2.1.160 | 6/2 | シェル起動ファイル（`.zshenv` 等）・`~/.config/git/` 書込みにプロンプト追加、`acceptEdits` でもビルド設定ファイル書込みに確認、`workflow` → `ultracode` リネーム、grep 単一ファイル実行で read-before-edit 要件を充足 |
| v2.1.161 | 6/2 | `OTEL_RESOURCE_ATTRIBUTES` のメトリクスラベル化・初期化前 OTel イベントドロップ修正、`claude mcp` の `${VAR}` シークレット平文表示修正、並列 Bash の独立化 |
| v2.1.162 | 6/3 | `claude agents --json` に `waitingFor`、Remote Control のフッターピル常時表示、`/ide` メニューの Windsurf → Devin Desktop リネーム反映 |
| v2.1.163 | 6/4 | Managed Settings に `requiredMinimumVersion` / `requiredMaximumVersion`（範囲外バージョンの起動拒否）、`/plugin list`、Stop/SubagentStop hooks の `additionalContext` 返却 |
| v2.1.165 | 6/5 | バグ修正・信頼性改善のみ |
| v2.1.166 / 167 | 6/6 | **`fallbackModel`（最大 3 段フォールバック + ターン 1 回自動リトライ）**、deny rule の tool-name glob（`"*"` で全ツール拒否）、**cross-session messaging ハードニング（`SendMessage` 中継メッセージから user authority を剥奪、中継 permission request 拒否・auto mode ブロック）**、`MAX_THINKING_TOKENS=0` / `--thinking disabled` での thinking 無効化 |

- cross-session ハードニングはマルチセッション / マルチエージェント運用時の権限昇格対策で、`SendMessage` を活用するチームに即時影響
- https://code.claude.com/docs/en/changelog
- 関連: Anthropic が Claude API 向け CLI クライアント「ant CLI」をリリース（Claude Code とのネイティブ統合、API リソースの YAML バージョニング）

### GitHub Copilot CLI / Copilot App — [master][copilot]

- **CLI v1.0.56 → v1.0.60**: Build 2026 連動の大型リフレッシュ（6/2）で Rubber Duck デフォルト ON、**Voice input GA**（音声処理はローカルのみ）、prompt scheduling（`/every` / `/after`）、issue/PR/gist タブ付き実験 TUI。v1.0.60（6/5）で **Anthropic モデルの max reasoning effort が全プラン提供**、HTTP/1.1 が default transport に
  - https://github.blog/changelog/2026-06-02-copilot-cli-improved-ui-rubber-duck-prompt-scheduling-and-voice-input/
- **Copilot App（デスクトップ）テクニカルプレビュー**が Windows / Mac / Linux で公開、週後半に Pro / Pro+ / Business / Enterprise 全顧客へ拡大。「My Work」ビューで複数リポ横断のセッション / issue / PR を一元化し、**Canvases**（plan / PR / browser session / terminal 等を人間と agent の双方向 work surface として可視化)を追加
  - https://github.blog/news-insights/product-news/github-copilot-app-the-agent-native-desktop-experience/

### Cursor 3.6 / 3.7 — Auto-review と Design Mode、Composer 2.5 の詳細公開 — [master][copilot]

- **Cursor 3.6（5/29）**: 新 run mode「Auto-review」。allowlist 即時実行 / sandbox 実行 / classifier subagent 判定の 3 段で承認プロンプト最小化と安全実行を両立。「夜間バッチ運用に耐える」と評価
- **Cursor 3.7（6/4-5）**: **Design Mode in canvases**（canvas 上で UI 要素を直接選択・注釈して編集指示、音声対応）、**Context Usage Report**（system prompt / tool definitions / rules / skills 毎のトークン内訳を可視化）、SDK 大型更新（独自関数の tool 化、subagent の任意深度ネスト、`npm install @cursor/sdk` / `pip install cursor-sdk`）
- **Composer 2.5 詳細**: Moonshot Kimi K2.5 ベース、SWE-Bench Multilingual 79.8%（Opus 4.7 / GPT-5.5 同等水準）、入力 $0.50/M（競合の約 1/10）。Artificial Analysis Coding Agent Index 3 位
- **Enterprise Organizations GA**（複数チームの一元管理）、Teams は Standard 席の含有使用量増 + Premium 席新設（7/1〜）、**Bugbot は 6/8 以降 renewal で従量課金化**（PR 1 件 $1.00〜1.50）、Automations が Agents Window に統合（multi-repo / no-repo 対応）
- https://cursor.com/changelog / https://cursor.com/blog/composer-2-5

### Devin / Cognition — Windsurf を「Devin Desktop」にリブランド — [master][copilot]

- **Devin Desktop 正式ローンチ（6/2）**: 旧 Windsurf IDE をリブランドし Devin ブランドを 4 サーフェス（Desktop / Cloud / CLI / Review）に統一。**Agent Command Center**（ローカル/クラウド全エージェントの Kanban 管理）、**Spaces**（エージェント間コンテキスト共有）、**Agent Client Protocol（ACP）対応**で Codex / Claude Agent / OpenCode をエディタ内実行可能。旧 Cascade は Rust 書き直しの「Devin Local」へ（トークン効率 +30%）
  - https://cognition.ai/blog/introducing-devin-desktop / https://devin.ai/blog/windsurf-is-now-devin-desktop
- **Personal Automations**（自分の identity で実行、専用権限モデル）、**v3 API がベータ卒業し primary API 化**（RBAC / セッション帰属）、Datadog MCP 公式提供、クラシック環境セットアップは **6/30 廃止**（宣言型 blueprints へ移行）
- 背景: Cognition は 5/27 に $1B 調達（$26B post-money）、ARR $492M、Devin 自身が Cognition コードベースの 89% を執筆

### OpenAI Codex — 「コーディング特化」から「業務 OS」へピボット — [master][industry]

- **Annotations / Sites / 6 業界別プラグイン（6/2）**: ドキュメントのピンポイント編集、アイデアを Web サイト / 社内アプリに即変換して URL 共有、営業・データ分析・投資銀行等 6 ロール向けプラグイン（Snowflake / Figma / Salesforce 等 62 アプリ + 110 スキル）。週間 5M WAU のうち**非開発者が 20%**で採用速度はエンジニアの 3 倍。ChatGPT 本体への Codex 統合を「数週間以内」に予告
  - https://venturebeat.com/orchestration/openais-codex-update-lets-agents-build-interactive-enterprise-workspaces-via-sites-and-role-specific-plugins
- **Codex CLI**: stable v0.137.0 + v0.138.0-alpha.2。TUI 改善、`codex archive`、Windows 管理者向け `codex sandbox setup --elevated`、Windows Computer Use 対応
- **課金・廃止**: Container 課金を「20 分一律」から分単位（5 分最小）に変更。**Reusable Prompts / Evals プラットフォームの廃止予告（6/3）** — プロンプトはコード側管理・評価は外部エコシステムへというスタンス
- ChatGPT workspace agents が Business workspaces に段階 rollout 開始

### その他開発ツール — [master][industry]

- **Docker Gordon AI エージェント GA**: Docker Desktop 4.74+、全アカウント無料（Gordon Plus $20/月でキャパシティ 2 倍）
- **Grok Build**: v0.2.20 で image-to-video / reference-to-video ツール、6/5 に worktrees サポート + コアモデル改善（Musk 投稿）。Composer 2.5 が SuperGrok / X Premium+ に追加
- **Gemini CLI / Gemini Code Assist IDE 拡張は 6/18 にサービス終了**（Antigravity CLI へ移行）
- **GitHub Trending**: コードを対話型ナレッジグラフに変換する「Understand-Anything」が 1 位（47.9K★）
- **Rolldown 1.0**: Rust 製 JS バンドラが Vite 8.0 に正式採用、ビルド 10-30 倍高速化

## モデル・技術

### 新モデルリリース — [industry][master]

- **MiniMax M3（6/1）**: SWE-bench Pro 59.0% で GPT-5.5（58.6%）超え（Opus 4.8 の 69.2% には届かず）。MSA（MiniMax Sparse Attention）で 1M トークン時デコード 15.6 倍高速、ネイティブマルチモーダル、入力 $0.60/M。10 日以内にオープンウェイト公開予定
  - https://venturebeat.com/technology/minimax-m3-debuts-eclipsing-gpt-5-5-and-gemini-3-1-pro-on-key-benchmark-performance-for-just-5-10-of-the-cost
- **NVIDIA Nemotron 3 Ultra（6/1 発表・6/4 公開）**: 550B（55B アクティブ）Mamba-Transformer MoE、1M コンテキスト、AA Intelligence Index 48 で米国オープンウェイト最高（中国 Kimi K2.6 の 54 には 6pt 差）。OpenMDW-1.1 ライセンス
  - https://developer.nvidia.com/blog/nvidia-nemotron-3-ultra-powers-faster-more-efficient-reasoning-for-long-running-agents/
- **Google Gemma 4 12B（6/3）**: Apache 2.0、テキスト・画像・音声・動画対応のデコーダ専用構成、16GB ラップトップで動作
- **Alibaba Qwen3.7-Plus（6/1 GA）**: マルチモーダルエージェントモデル、入力 $0.40/M・出力 $1.60/M の低価格 API（ウェイト非公開）
- **xAI Grok Imagine 1.5**: 画像→動画生成（720p・ネイティブ音声付き）で Artificial Analysis Video Arena I2V 首位（Elo 1404）。Quality Mode がエンタープライズ提供開始。Grok V9-Medium（1.5T params）は 6 月中旬公開予定を維持
- **OpenAI Realtime 2 / Realtime Translate / Realtime Whisper**: 音声エージェント向け新リアルタイムモデル群

### モデル運用・退役 — [master][copilot]

- **ChatGPT「Dreaming V3」メモリ刷新（6/4〜 Plus/Pro US）**: 手動 saved-memories を廃止し、バックグラウンド合成プロセスが過去会話から記憶を自動更新。事実想起率 41.5% → 82.8%、サービング計算コスト約 1/5、メモリ容量 2 倍 + reviewable summary ページ。Free / Go へも数週間内に拡大予定
- **GPT-5.5 が Microsoft Foundry で GA（6/3）**: $5/M 入力・$30/M 出力（Pro は $30/$180）
- **退役スケジュール**: Claude Sonnet 4 / Opus 4 が 6/15 に API 退役（→ Sonnet 4.6 / Opus 4.7）、GPT-4.5 が 6/27・o3 が 8/26 に ChatGPT 退役、GPT-4.1 は Copilot 全体験から廃止、Copilot Studio の Claude Sonnet 4.5 は評価期間後に 4.6 へ自動マイグレーション
- **Gemini**: 3.5 Flash が 6/8 から Gemini Enterprise app で既定有効化（管理者トグル廃止・OFF 不可）。3.5 Pro は 6 月後半 GA 観測。Gemini Spark（24/7 パーソナルエージェント）が US AI Ultra ユーザーに silent launch

## M365 / Copilot Studio / Google Workspace（管理者向け）

### M365 Copilot — 新デザイン展開と自動インストール再開 — [copilot]

- **新デザイン 6 月ロールアウト**: チャット中心 UI、プロンプトラインのタスク認識型ワークスペース化、Word/Excel/PowerPoint の Dynamic Action Button、Copilot Notebooks 刷新（OneNote 同期・Teams 会議参照・インフォグラフィック生成は 6 月下旬〜）
- **Windows PC への自動インストール 6 月再開**: 新ポリシー「AutoInstall M365 Copilot App」がデフォルト有効（テナント単位で OFF 可）
- **Federated Copilot Connectors GA**: MCP 経由でサードパーティデータにリアルタイム接続（M365 Chat / Researcher / Excel Agent Mode）。データの取り込み・インデックス化なし。ポリシーベースのエージェントライフサイクル管理も GA
- **エージェント評価**: Release Notes（6/2）でテストケースの手動追加・インポートと複数採点方式（Exact / Similarity / Compare Meaning 等）の Grader Framework を追加
- **Planner Agent GA（6 月中旬〜下旬）**、Office 365 Copilot の Agent Mode 既定化（6 月下旬ロールアウト）
- 利用率: 5 月末アップデート後 Word +27% / Excel +33% / PowerPoint +43% / Outlook +30%
- https://www.microsoft.com/en-us/microsoft-365/blog/2026/05/28/introducing-a-new-design-for-microsoft-365-copilot/

### M365 価格改定・パッケージング（7/1 発効） — [copilot]

- M365 E3 +8%（$36→$39）、E5 +5%、Business Basic +16%、Business Standard +12%、Office 365 E3 +13%。既存顧客は更新時まで現行価格
- バンドル強化: Defender for Office 365 P1、Intune Suite 系機能、Exchange Online +50GB、Copilot Chat 強化。6 月中旬から展開開始、8/1 までに完了予定（Message Center で 30 日前通知）
- https://www.microsoft.com/en-us/licensing/news/2026-m365-packaging-pricing-updates

### Copilot Studio — Build 2026.5.3 / 2026.5.4 と 6 月末マイルストーン — [copilot]

- **Platform Build 2026.5.4 展開開始（6/4〜）**: 多言語音声エージェントの言語別 TTS 設定、マルチエージェント分析インベントリ、Safe Sharing Governance、SharePoint 検索レート制限の HTTP 500→429 修正。**2026.5.3 は日本含む全主要リージョンに展開完了**（環境全体分析・カスタムメトリクス・MCP ツーリング・音声 ASR デフォルト化）
  - https://learn.microsoft.com/en-us/power-platform/released-versions/copilotstudio/2026.5.4
- **CLI GA（5/31）**: Power Platform CLI 統合でエージェント定義のデプロイ・更新を CLI から実行可能
- **6 月の GA / 廃止予定**: マルチターン会話評価 GA、脅威保護強化 GA、感度ラベル表示 GA（6/30）、M365 最適化エージェント作成 Preview、**Teams 内クラシックエージェント作成の廃止（6/30）**
- **Frontier Tuning（Private Preview）**: 組織固有の用語・スタイル・業務プロセスをモデルに反映するファインチューニング
- **Work IQ APIs**: メール・会議・ファイル等を意味インデックス化しエージェントに提供。数百 API を 10 個の汎用ツール（MCP 経由）に集約、トークン消費 80% 削減。6/16 に A2A + Remote MCP + REST が同時 GA
- Defender XDR に AgentsInfo テーブル（Preview、旧 AIAgentsInfo は 7/1 廃止）
- Teams: Together Mode が 6 月末で廃止完了、会議 UI リフレッシュは 7 月 Targeted Release / 8 月 GA

### Google Workspace — Gmail × Drive 横断 RAG が GA — [master]

- **Gmail を「Ask Gemini in Drive」のソースにする機能が GA**（メール + ファイル + フォルダ横断の根拠付き回答）、Drive「Organize My Files」GA（7/15 までプロモ上限緩和）
- **DLP for Google Calendar GA**、Device Bound Session Credentials（DBSC）が Chrome on Windows で GA（セッション窃取耐性）
- Workspace Studio: リスト反復ループ、Ask Gemini ステップの Response format 追加。促進的使用量上限は 6/1 で終了
- Gemini app の chat / canvas / 生成メディアを Google Drive 経由で共有可能に（既定 ON、Admin console 管理）
- https://workspaceupdates.googleblog.com/

## エンタープライズ AI 導入・市場動向

### 企業 AI 導入で Anthropic が OpenAI を初逆転、利用シェアも上昇 — [industry]

- **Ramp AI Index（5 月）**: 企業導入率 Anthropic 34.4%（前月比 +3.8pt）vs OpenAI 32.3%（-2.9pt）。1 年前は OpenAI 32% vs Anthropic 8% 未満。技術職での採用が牽引、全体の AI 導入率は 50.6%
- **Similarweb AI Tracker（4 月）**: ChatGPT 54.7% / Gemini 27.4% / Claude 8.2%（3 月 6.02% から上昇）/ DeepSeek 4.1% / Grok 2.8%
- **MAU**: ChatGPT が史上最速で 10 億 MAU 突破（Sensor Tower 推計）。Claude は 56M MAU ながら前年比 +640% 成長（ChatGPT は +62%）
- https://venturebeat.com/technology/anthropic-finally-beat-openai-in-business-ai-adoption-but-3-big-threats-could-erase-its-lead

### AI コーディングのコスト管理が業界共通課題に — [industry]

- **Uber**: Claude Code / Cursor の利用急増で 2026 年度 AI 予算を 4 ヶ月で消化、エンジニア 1 人月 $500〜2,000 の API 費用に月 $1,500 キャップを導入。エンジニアの 95% が AI ツールを月次利用、コミットコードの 70% が AI 起源。COO は「ツール投資と消費者向けイノベーションの因果関係はまだ見えない」と発言
  - https://fortune.com/2026/05/26/uber-coo-ai-spending-tokens-claude-code/
- **Microsoft が社内 Claude Code ライセンスを 6/30 で廃止**: Experiences + Devices 部門（約 1.2 万人規模の部門、対象は数千名規模のエンジニアとの報道も）が GitHub Copilot CLI へ移行。「人気になりすぎた」ことによるコスト増と、自社製品を販売しながら社内が Claude Code に流出する戦略的矛盾が背景。Anthropic への投資契約・Azure 利用契約は維持
  - https://www.windowscentral.com/microsoft/microsoft-cancels-claude-code-licenses-shifting-developers-to-github-copilot-cli-a-move-likely-driven-by-financial-motives
- **Remote（給与計算 SaaS）**: 全社 AI 導入で従業員 1 人当たり収益 +50%、提出コードの 85% 以上が AI 生成、人員増なしで $300M ARR 達成
- **帝国データバンク調査（3 月、10,312 社）**: 生成 AI 活用企業 34.5%、うち 86.7% が効果実感。課題は「情報の正確性」50.4%

### Anthropic の GTM / エンタープライズ強化 — [master]

- **Claude Partner Network「Services Track」「Partner Hub」発表（6/3）**: パートナーを Select / Preferred / Global Premier の 3 階層に正式化（認定者数・本番デプロイ顧客数・公開事例で判定）。発足以降 40,000 社が応募・10,000 名超が Claude Certification 取得。昇格レビューは年 2 回（7/1・1/1、初年度のみ 10/1 追加）
  - https://www.anthropic.com/news/services-track-partner-hub
- **Claude Enterprise の Custom Roles に admin 権限の粒度設定を追加**: Owner 化せずに billing / Identity & Access / privacy 等を個別委譲可能
- **Code with Claude Tokyo（6/10）+ Extended（6/11）**: SF・London に続く第 3 都市として APAC 初開催。Extended は独立開発者・早期創業者向けワークショップ

### プラットフォーム各社の動き — [master][industry]

- **Mistral**: Le Chat を「Vibe」にリブランドし AI 統合エージェントとして再ポジショニング。Work Mode（Workspace / Outlook / SharePoint / Slack / GitHub 連携）、Remote Coding Agents のクラウド実行化、新料金（Free / Pro $14.99 / Team $24.99 / Student $5.99）。Slack 連携 Code Mode は 6 月中提供予定。ウィーン拠点 Emmi AI（物理シミュレーション）買収も
- **Snowflake Summit 2026（6/2）**: AI コーディングエージェントを「CoCo」にリブランドし 26 新機能（Automations / Cloud Agents / Skill Catalog）。エージェント向けコンテキスト層「Horizon Context」+「Cortex Sense」を発表。なお Snowflake は Q1 FY27 決算で売上 $1.39B（+33% YoY）、株価 +38% 急騰（5/29-30）
- **SAP Sapphire 2026**: SAP BTP / Business Data Cloud / Business AI を統合した「Business AI Platform」で自律型エンタープライズ構想。Anthropic Claude を主要推論モデルとして採用
- **Writer**: プロンプト不要のイベント駆動型自律エージェントを発表（経営層 2,400 名調査: 97% が過去 1 年でエージェント導入、79% が導入課題を報告）
- **OpenAI Altman CEO**: 「プロアクティブ AI」をチャット・エージェントの次のフェーズに位置付け
- **Microsoft 社内の混乱**: Scout を巡る「中毒化 → エージェンティックプラットフォーム」3 フェーズ計画メモを Nadella CEO が即座に否定（The Information 報道）

## ハードウェア・ローカル AI（Computex 2026）

### NVIDIA Computex 2026 基調講演（6/1） — [industry]

- **DGX Station for Windows**: GB300 搭載、20 PFLOPS FP4・748GB メモリでデスクサイドの 1 兆パラメータモデル実行。Microsoft 共同開発のオープンソースエージェントランタイム「NVIDIA OpenShell」同梱。Dell / HP / ASUS 等から Q4 出荷予定
- **RTX Spark**: ノート PC 向け AI SoC。128GB 統合メモリ・1 PFLOPS、最大 80W。Surface Laptop Ultra / Dell XPS 16 等で今秋出荷
- **Vera Rubin 量産開始**: FP4 推論 50 PFLOPS（Blackwell 比 5 倍）、HBM4 採用。マルチギガワット級 AI データセンター向け
- **Cosmos 3**: Physical AI オムニモデル（視覚推論・世界生成・行動予測を単一モデル統合）。ロボティクスベンチ 7 部門 1 位、Super / Nano は Hugging Face + NIM で公開
- https://blogs.nvidia.com/blog/nvidia-gtc-taipei-computex-2026-news/

### ローカル / ハイブリッド推論の潮流 — [industry][master]

- **Perplexity ハイブリッドローカル・クラウド推論（7 月提供予定）**: ローカル LLM が「トラフィックコップ」となり機密データはオンデバイス、高負荷タスクはクラウドへルーティング。Intel Core Ultra Series 3 でデモ
- **Dell「Deskside Agentic AI」**: NVIDIA GB10 / GB300 搭載、クラウド非依存のローカルエージェント実行用デスクトップ PC 群
- **Vector Core Compute**: Vista Equity Partners + Cambium Capital の推論特化クラウド。Intel Xeon 6 + SambaNova RDU + NVIDIA Blackwell でワークロード動的分割、SambaNova へ $3.5B 投資コミット
- Build 2026 の WSL 3（GPU/NPU passthrough）+ Foundry Local GA と合わせ、「Windows / デスクトップでのローカル LLM 実行」が今週一気に現実解へ
- Huawei は「Tau Scaling Law」（信号伝送時間短縮シフト）を発表

## 政策・規制・セキュリティ

### 米国の AI 規制が「規制緩和一辺倒」から転換 — [industry]

- **トランプ大統領が AI 大統領令に署名（6/2）**: フロンティアモデルのリリース 30 日前に政府への早期アクセス提供を任意ベースで要請。政府機関がサイバー・国家安全保障リスクを評価する枠組みを構築
  - https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/
- **超党派「Great American AI Act」discussion draft（6/4、269 ページ）**: 州 AI 規制の 3 年間プリエンプション + 連邦基準策定。年間売上 $500M 超の企業に安全フレームワーク公表・重大インシデント報告・半年毎の第三者監査を義務化、CASI に年 $100M 予算。ただし 36 州の司法長官が広範なプリエンプションに反対する連合を結成済み
- **OpenAI「Frontier Safety Blueprint」（6/3）**: 州法のコンセンサスを連邦法に集約する「逆連邦主義」を提案、CASI を評価中核機関に位置付け（配備の承認・阻止権限は持たせない）。5/29 公開の Frontier Governance Framework（CA TFAIA / EU AI Act 対応）と連動
- **AI 企業 CEO 4 名（Altman / Amodei / Hassabis / Suleyman）が合成 DNA 検査の法制化を米議会に連名要請（6/4）**: 危険配列スクリーニングと記録保持の義務化を要求。OpenAI は生命科学防衛応用の「Rosalind Biodefense Initiative」も開始

### AI を使う攻撃・AI を守る対策 — [master][copilot][industry]

- **Anthropic Project Glasswing を約 150 組織追加・15+ ヶ国に拡大（6/2）**: Samsung・NATO を含む計約 200 組織に Claude Mythos アクセスを提供（電力・水道・医療・通信等）。初回 50 組織で 10,000 件超の高/重大度脆弱性を発見済み。Mythos 一般公開は「数週間以内」予告を維持
  - https://www.anthropic.com/news/expanding-project-glasswing
- **Sysdig が初の「自律型 LLM エージェントによるサイバー侵入」を文書化**: CVE-2026-39987（Marimo WebSocket RCE）起点に AWS 認証情報奪取 → SSH 鍵 → PostgreSQL データを 2 分で窃取。公開から 9 時間 41 分で武器化と、人間の N-day ワークフローより高速
  - https://www.sysdig.com/blog/ai-agent-at-the-wheel-how-an-attacker-used-llms-to-move-from-a-cve-to-an-internal-database-in-4-pivots
- **PyTorch Lightning サプライチェーン攻撃**: 悪意ある v2.6.2-2.6.3 が PyPI に公開され、ブラウザ認証情報・GitHub Token・クラウド資格情報を窃取するワーム型ペイロードを確認（隔離済み、v2.6.1 以前の利用確認を推奨）
- **ChatGPT セキュリティ機能**: Active sessions（セッション一覧・不審セッションのサインアウト）、Trusted Contact（深刻な safety signal の信頼連絡先通知）、**Lockdown Mode**（Web / 外部サービスアクセスを制限し prompt injection 経由のデータ流出を低減、全ログインユーザに opt-in 提供開始）
- **Microsoft MXC**: Windows カーネルレベルで AI エージェントの権限を宣言的制御する OS レベルサンドボックス（Process / Session の 2 段分離、OpenAI・NVIDIA・Manus・Copilot CLI が採用パートナー、Early Preview）

## サービス障害・信頼性

### Claude で 6 月に 2 回の障害 — [copilot]

- **6/2**: サブエージェントの無限ループによるトークン消費スパイクが原因の大規模障害（06:04 UTC 調査開始 → 11:49 UTC 解決）
- **6/5**: 15:08 UTC に全モデルでエラー率上昇を検知（claude.ai / Claude API / Claude Code / Claude Cowork に影響）。Opus 4.6 → Sonnet 4.6 → Opus 4.8 → Opus 4.7 → Opus 4.5 の順で約 2 時間半かけて復旧。Claude for Government は両日とも影響なし
- AI のインフラ化に伴う信頼性課題として分析記事も出ており（Thoughtworks）、Claude Code v2.1.166 の `fallbackModel` 追加はこの文脈でも有効打
- https://status.claude.com/history

## 来週の注目予定

- **6/8（月）**: Apple WWDC26 キーノート（iOS 27 / macOS 27、Siri をスタンドアロンチャットボットアプリに大改修、外部モデル選択対応の観測） / Cursor Bugbot 従量課金化（renewal から適用） / Gemini 3.5 Flash が Gemini Enterprise app で既定有効化（管理者トグル廃止）
- **6/10（水）**: Code with Claude Tokyo 開催（APAC 初、日英バイリンガル）
- **6/11（木）**: Code with Claude Tokyo Extended（独立開発者・早期創業者向け）
- **6/15（月）**: Anthropic Programmatic Credit Pool 施行（Agent SDK / `claude -p` / GitHub Actions が別クレジットプールへ） / Claude Sonnet 4・Opus 4 が API 退役 / Entra Conditional Access リソース除外ポリシーの強制適用変更
- **6/16（火）**: Microsoft Work IQ APIs GA（A2A + Remote MCP + REST 同時提供）
- **6 月中旬**: M365 パッケージング更新の展開開始（Defender P1 / Intune 等） / Grok V9-Medium（1.5T params）公開予定 / Planner Agent GA（〜下旬）
- **6/18（木）**: Gemini CLI / Gemini Code Assist IDE 拡張サービス終了（Antigravity CLI へ移行）
- **6/25**: gemini-3.1-flash-image-preview / gemini-3-pro-image-preview 廃止
- **6/27**: GPT-4.5 が ChatGPT から退役
- **6/30**: Copilot Studio の Teams クラシックエージェント作成廃止・感度ラベル表示 GA / Devin クラシック環境セットアップ廃止（blueprints 移行） / Microsoft 社内 Claude Code ライセンス終了 / Teams Together Mode 廃止完了 / Security Copilot E5 展開完了
- **6 月後半**: Gemini 3.5 Pro GA 観測 / Mistral Vibe の Slack 連携 Code Mode 提供
- **7/1**: M365 価格改定発効（E3 $36→$39 等） / Cursor Teams 新価格適用 / Devin Cascade 完全廃止 / Claude Partner Network 初回階層昇格レビュー / Defender XDR 旧 AIAgentsInfo テーブル廃止
- **7 月**: Perplexity ハイブリッド推論ローンチ / Teams 会議 UI リフレッシュ Targeted Release / 7/15 Workspace「Organize My Files」プロモ上限終了
- **8 月**: GitHub Copilot で Project Polaris 既定モデル化（3 ヶ月フォールバック付き） / Azure Agent Orchestrator プレビュー / Teams 会議 UI GA
- **8/26**: OpenAI Assistants API 廃止 / o3 退役
- **9/10-11**: AGNTCon + MCPCon Japan（東京・渋谷、Linux Foundation）
- **10/1**: Claude Partner Network 追加昇格レビュー(初年度限定)
- **12/1**: 旧 GPT Image モデル API 廃止
- **Q4 2026**: Azure Agent Mesh GA 目標 / NVIDIA DGX Station for Windows 出荷

## 改善メモ

- **WebFetch 403 が広範囲で継続**: Anthropic 公式 news（2026-04-02 以降 60 日超連続）、OpenAI / Google / Cursor / Devin 公式、mc.merill.net、Microsoft Learn 各ページ、[industry] の全 RSS フィード（Google News / GIGAZINE / The Decoder / VentureBeat / Publickey / hnrss / Product Hunt / GitHub Trending）。WebSearch プライマリ + Microsoft Learn MCP フォールバック運用が 3 リポとも定着
- **`code.claude.com/docs/en/changelog` のみ WebFetch が安定稼働**。今後もプライマリ維持（[master]）
- **daily-sources.md への追加提案（[master] で繰り返し提起、未反映）**: GitHub Copilot CLI Releases の独立ソース化（3 回目）、Build / I/O / DevDay 等の大型イベント当日の追加検索手順の明文化（3 回目）、AWS News Blog（クラウドパートナー発表用）、Anthropic Institute（政策・研究系の取りこぼし防止）、GitHub Copilot Changelog ラベルページ、`x.ai/build/changelog`、Codex CLI changelog、サードパーティ集約ページ（claudeupdates.dev 等）
- **M365 Copilot Release Notes は 18,000 行超で WebFetch タイムアウト** → Microsoft Learn MCP + grep 差分検出方式が定着（[copilot]）
- **Copilot Studio Released Versions はリージョン展開状況の変化が速く、毎日確認の価値あり**（2026.5.3 が「Coming Soon」から数日で全リージョン展開完了に変化）（[copilot]）
- **xAI Grok の更新追跡は Musk の X 投稿が一次ソース化**している傾向。X トレンド検索キーワードへの追加を提案（[master]）
- 月境界（5 月→6 月）の `digests/2026/06/` ディレクトリ切替は 3 リポとも正常（[master]）
- **リポ間・日次間の記述の揺れ（要注意）**:
  - OpenAI の評価額が [industry] 内で不一致（6/6 ダイジェスト「$730B」vs 6/7「$852B」）
  - GitHub Copilot Pro のクレジット表記が揺れ（[copilot]「$10 で 1,000 クレジット」vs [industry] 6/7「$10 基本 + $5 フレックス = $15/月」）
  - MiniMax M3 のリリース時期（[industry] 6/1「2026 年後半リリース予定」→ 6/3「6/1 リリース済み」。予告記事と実リリース報道の混在）
  - Microsoft 社内 Claude Code ライセンス廃止の対象規模（[industry] 6/2「約 12,000 人」vs 6/6-6/7「数千名」。部門全体の人数と対象エンジニア数の違いの可能性）
  - Claude 6/5 障害の影響範囲（[copilot] 6/6「Opus 4.7/4.8 のみ影響継続」vs 6/7「全モデルでエラー率上昇・順次復旧」。同一事象の続報差）
