# AI ニュース週次サマリー — 2026-W20（2026-05-11 〜 2026-05-17）

> 入力: 取得成功 19 / 21（欠損は下の表に列挙）
> 生成日時: 2026-06-12（JST・バックフィル生成）

## ⚠️ 欠損ファイル通知

| 日付 | 欠損リポジトリ | 影響 |
|---|---|---|
| 2026-05-12 | [master] kit1132/01_ai-news-Master | モデル/Claude Code 情報が不足の可能性。[copilot][industry] の同日ダイジェストで補完 |
| 2026-05-14 | [master] kit1132/01_ai-news-Master | 同上。5/13-14 の大型発表は [master] 5/15-16 の補完収録と [copilot][industry] でカバー |

## 今週のハイライト

### 1. Anthropic「Programmatic Credit Pool」発表 — サードパーティエージェント再開放と引き換えの従量制化

**事実** 5/13 の予告を経て 5/14 に正式発表。6/15 から Claude サブスクリプションの利用枠を「対話用」と「プログラム実行用」に分離し、月次の Programmatic credit（Pro $20 / Max 5x $100 / Max 20x $200、繰越なし、API 料金で消費）を新設する。対象は Agent SDK、`claude -p`、Claude Code GitHub Actions、OpenClaw 等のサードパーティハーネスで、ターミナルの対話型 Claude Code は影響なし。

**根拠** 4月の「第三者エージェント禁止」方針からの実質的な巻き戻し（有料化前提での再開放）。[copilot] も「Agent SDK Credits 導入により OpenClaw 等のプログラマティック利用が再開」と同内容を確認。

**影響** Theo Browne（T3 Code 作者）が「実効値で 25-40 倍の値上げ」と試算するなど開発者コミュニティの反発が 3 週連続でトピック化。Zed 等のサードパーティハーネスの実効サブシディが大幅減となる一方、OpenAI が同日（5/14）に新規 Business 顧客向け「Codex 2ヶ月無料」を発表し、移行圧力が増幅した。

**行動指針** 6/15 の発効前に `claude -p`・GitHub Actions・Agent SDK 経由のプログラマティック利用量を棚卸しし、自プランのクレジット枠内に収まるか試算する。ヘビーユースは API 直課金や安価モデルへのルーティングを検討。

出典:
- https://venturebeat.com/technology/anthropic-reinstates-openclaw-and-third-party-agent-usage-on-claude-subscriptions-with-a-catch
- https://www.infoworld.com/article/4171274/anthropic-puts-claude-agents-on-a-meter-across-its-subscriptions.html
- https://www.theregister.com/ai-ml/2026/05/14/anthropic-tosses-agents-into-the-api-billing-pool/5240748
- https://www.axios.com/2026/05/14/anthropic-claude-price-openai-tokens

### 2. Anthropic、ビジネス導入率で OpenAI を初逆転 — 評価額・インフラ・大型提携が同一週に集中

**事実** Ramp AI Index 5月版で Anthropic の企業導入率が 34.4%（前月比 +3.8pt）となり、OpenAI の 32.3%（-2.9pt）を初めて上回った。過去 1 年で導入率は 4 倍。原動力は Claude Code で、SemiAnalysis 分析では GitHub 公開コミットの 4% を Claude Code が生成（1ヶ月で倍増、年末 20% 超予測）。

**根拠** 同週に裏付けとなる動きが集中: Akamai と 7 年 $1.8B のクラウド契約（5/8 報道、Akamai 史上最大）、Salesforce Benioff CEO が「2026 年に Anthropic トークンを $300M 消費」と表明（5/16、ほぼ全額コーディング用途）、Gates Foundation と 4 年 $200M パートナーシップ（5/13）、PwC がアライアンス拡大で米国 3 万人を Claude トレーニング（5/14）、EPAM が 10,000 名の Claude 認証アーキテクト育成（単一企業最大の認証コミット）。$900B〜$950B 評価で $30B〜$50B の調達交渉も進行中（ARR は公表ランレート $30B。OpenAI 側は「ネットでは $22B 程度」と反論）。

**影響** エンタープライズ AI 選定の基準が変わりつつある一方、日経は「定額制の実質値上げ検討」を報道（Uber は年間 AI 予算を 4ヶ月で消化）。導入率の躍進とコスト構造の変化リスクが同時進行している。

**行動指針** 提案・選定時の根拠データとして Ramp AI Index と GitHub コミット比率を引用できるよう控える。コスト前提は Programmatic Credit Pool 発効（6/15）後の体系で再見積もりする。

出典:
- https://ramp.com/leading-indicators/ai-index-may-2026
- https://venturebeat.com/technology/anthropic-finally-beat-openai-in-business-ai-adoption-but-3-big-threats-could-erase-its-lead
- https://www.bloomberg.com/news/articles/2026-05-08/anthropic-inks-1-8-billion-computing-deal-with-akamai
- https://www.anthropic.com/news/gates-foundation-partnership
- https://www.anthropic.com/news/pwc-expanded-partnership
- https://thenextweb.com/news/salesforce-benioff-300-million-anthropic-tokens-slack-coding
- https://sherwood.news/tech/anthropic-in-talks-for-funding-at-a-valuation-as-high-as-950-billion-which-would-make-it-bigger-than-openai/

### 3. Claude Platform on AWS GA（5/11） — AWS アカウントのまま Claude API フル機能

**事実** Anthropic ネイティブの Claude Platform が AWS 上で一般提供開始。AWS IAM 認証、CloudTrail 監査ログ、AWS Marketplace 請求（既存コミットメント充当可）でClaude API のフル機能セット（Messages API、Managed Agents β、Files API β、Skills β、MCP Connector β、コード実行、Web Search/Fetch、プロンプトキャッシング、バッチ処理）を利用できる。東京を含む世界 17 リージョン。

**根拠** AWS が初のネイティブ Claude Platform 提供クラウド。データ処理は Anthropic が実施（AWS セキュリティ境界外）で、Amazon Bedrock 上の Claude は引き続き併存（棲み分け）。

**影響** AWS 利用組織にとってベンダー統合・調達・コンプライアンスが大幅に簡素化。「Bedrock（AWS 境界内・リージョン処理）」と「Claude Platform（最新フル機能）」の使い分けが新しい設計判断ポイントになる。

**行動指針** Bedrock 運用中のプロジェクトで、Bedrock 未提供機能（Managed Agents / Skills / Files API 等）を Claude Platform on AWS で補えるか、データ処理境界の要件と合わせて検討する。

出典:
- https://aws.amazon.com/about-aws/whats-new/2026/05/claude-platform-aws/
- https://www.anthropic.com/news/claude-platform-on-aws

### 4. 「エージェント管理アプリ」競争が一斉点火 — GitHub Copilot App / Codex モバイル / Agent View / VS Code Agent window

**事実** 1 週間で各社からエージェント並列運用 UI が連続リリース。①GitHub Copilot App テクニカルプレビュー（5/14、Windows/macOS/Linux。セッションごとに独立した git worktree + branch + task state で同一リポ並列実行）、②OpenAI Codex が ChatGPT モバイル（iOS/Android）で全プラン展開（5/14、週次アクティブ 400 万人）、③Claude Code v2.1.139 の Agent View（`claude agents` で全セッション一覧）と `/goal`（完了条件を満たすまでターン継続）（5/11-12）、④VS Code 1.120「Agent window」プレビュー（5/13、Copilot CLI/Cloud/Claude エージェントを統合管理）、⑤xAI のターミナルエージェント「Grok Build」ベータ（5/14、最大 8 並列サブエージェント、Arena/Plan Mode）。

**根拠** 3 リポすべてが同趨勢を別ソースで確認。Claude Code Desktop（前週リデザイン）、Codex App、Copilot App が直接競合する構図。

**影響** 「単発チャット支援」から「複数エージェントの並列実行と監督」へ開発 UI のパラダイムが移行。リモート/モバイルからのエージェント監視も標準機能化が進む。

**行動指針** Claude Code の Agent View・`/goal` を試し、並列セッション運用の型（バックグラウンド実行→必要時のみ復帰）を自分のワークフローに取り込む。

出典:
- https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/
- https://thenewstack.io/openai-codex-chatgpt-mobile/
- https://code.claude.com/docs/en/agent-view
- https://www.publickey1.jp/blog/26/vs_codeaiagent_window.html
- https://x.ai/news/grok-build-cli

### 5. Google「Gemini Intelligence」+ Googlebook 発表 — I/O 2026 直前の「AI OS」宣言

**事実** 5/12 の Android Show: I/O Edition で、Gemini を Android の OS レイヤに統合する「Gemini Intelligence」を発表。アプリ横断タスク自動化・画面認識・フォーム自動入力、音声の語りをビジネス文へ変換する「Rambler」、自然言語ウィジェット生成等を提供し、今夏 Samsung/Pixel から展開。ChromeOS 後継の AI ファーストノート PC「Googlebook」（Acer/ASUS/Dell/HP/Lenovo、2026 年秋）も発表。Android 17 プレビューも公開。

**根拠** Android 統括 Sameer Samat が「OS からインテリジェンスシステムへの移行」と明言。DeepMind はカーソルを AI エージェント化する「Magic Pointer」構想も公開。I/O 本編（5/19-20）では新 Gemini モデル（Gemini 3.2 Flash のリーク多数、エージェント「Gemini Spark」報道）が見込まれる。

**影響** Microsoft Copilot+ PC との正面衝突に加え、Apple も iOS 27 でサードパーティ AI モデル選択（Gemini/Claude 等）を計画（WWDC 6/8 発表見込み）と報道され、「OS × AI」の 3 つ巴が確定しつつある。

**行動指針** 5/19-20 の Google I/O を重点ウォッチ（新 Gemini モデルの API 提供条件、Workspace への波及）。

出典:
- https://blog.google/products-and-platforms/platforms/android/gemini-intelligence/
- https://blog.google/products-and-platforms/platforms/android/meet-googlebook/
- https://techcrunch.com/2026/05/12/everything-google-announced-at-its-android-show-from-googlebooks-to-vibe-coded-widgets/
- https://gigazine.net/news/20260515-google-gemini-spark/

## Anthropic / Claude

### Claude for Legal 正式ローンチ（5/12） — [copilot][industry]
- 法務特化プラットフォーム。12 の実務分野別プラグイン（Commercial/Corporate/Privacy/AI Governance/IP/Litigation 等）+ 20 以上の MCP コネクタ（Thomson Reuters CoCounsel、DocuSign、iManage、Relativity、Everlaw 等）+ 80 以上の専門エージェントテンプレート（Apache 2.0 で GitHub 公開）
- Claude for Excel/PowerPoint/Word が GA、Outlook は公開ベータ。Freshfields、Quinn Emanuel 等が実案件利用中。法務専門職は Cowork 最多利用のナレッジワーク分野
- https://www.artificiallawyer.com/2026/05/12/claude-for-legal-launches-may-reshape-the-legal-tech-world/

### Claude for Small Business 発表・全米ツアー開始（5/13-14） — [master][copilot][industry]
- 中小企業向けパッケージ。QuickBooks、PayPal、HubSpot、Canva、Docusign、Google Workspace、Microsoft 365 と接続し、給与計算・月次決算・キャッシュフロー予測等のワークフローを追加料金なしで提供
- 5/14 シカゴから全米 10 都市ツアー（各 100 人、半日 AI fluency トレーニング、参加者に Claude Max 1ヶ月分）。PayPal と共同コースも開設
- https://www.anthropic.com/news/claude-for-small-business

### リサーチペーパー「2028: Two scenarios for global AI leadership」（5/14） — [master]
- 2028 年を transformative AI の到来時点・米中 AI 競争の決着点と予測。輸出規制強化／distillation 攻撃の法的明確化／米国製 AI のグローバル普及という 3 つの政策提言
- https://www.anthropic.com/research/2028-ai-leadership

### Microsoft、社内 Claude Code ライセンスを取り消し（5/14 報道） — [industry]
- Experiences + Devices 部門が 2025 年 12 月から数千人に提供していた Claude Code ライセンスを 6/30 までに終了し、GitHub Copilot CLI へ一本化。社内で「Copilot より生産性が高い」と利用が急拡大したことと、会計年度末のコスト削減が背景
- https://the-decoder.com/microsoft-pulls-claude-code-licenses-and-pushes-developers-back-toward-its-own-ai-tool/

### Sonnet 4.8 GA は未確認のまま — [master]
- リリース予想ウィンドウ（5/5-16）を超過。リーク情報のみで、Code with Claude London（5/19）が最有力の発表機会として watch 継続

## 開発ツール

### Claude Code 週間リリース v2.1.139 〜 v2.1.143 — [master][copilot]

| バージョン | 主な変更 |
|-----------|---------|
| v2.1.139（5/11-12） | **Agent View**（`claude agents` で全セッションのコマンドセンター、Research Preview）、**`/goal`**（完了条件を満たすまでターン継続）、`claude project purge`、`/scroll-speed`、プラグインのトークンコスト試算、Hook 強化（`continueOnBlock` 等） |
| v2.1.140（5/13） | subagent_type の大文字小文字・区切り無視マッチング、`/goal` ハング修正、Bedrock/Vertex/Foundry の背景クエリが存在しない Haiku モデル ID を使うバグ修正 |
| v2.1.141（5/13） | `terminalSequence` hook フィールド、`ANTHROPIC_WORKSPACE_ID`、`claude agents --cwd`、Rewind メニューに「Summarize up to here」、permission ダイアログに `permissions.ask` の起因表示 |
| v2.1.142（5/14） | `claude agents` にセッション設定フラグ群（`--model`/`--effort`/`--mcp-config` 等）、**Fast mode の既定モデルが Opus 4.6 → 4.7 に**、ルート `SKILL.md` のスキル認識 |
| v2.1.143（5/15) | プラグイン依存関係の強制（disable 拒否/推移的有効化）、`/plugin` にターン毎トークン推定コスト表示、`worktree.bgIsolation: "none"`、PowerShell `-ExecutionPolicy Bypass` デフォルト化 |

- https://code.claude.com/docs/en/changelog

### GitHub Copilot — [copilot][master]
- **Copilot CLI v1.0.46〜48（5/12-14）**: 非推奨バージョン警告、read-only `gh` コマンド自動承認、diff 折返し（v1.0.46）／`/fork` コマンド、`/diff` の j/k ナビ（v1.0.47）／モデルピッカーに実トークン単価表示（AI Credits 課金対応）、CJK・絵文字レンダリング修正、Azure DevOps 環境での GitHub MCP Server 自動無効化（v1.0.48）
- **Code Review コメント体験改善（5/12）**: High/Medium/Low の重要度ラベル、類似コメントのグループ化
- **Grok Code Fast 1 廃止完了（5/15）**: xAI のモデル提供終了に伴い全体験から削除。移行先は GPT-5 mini / Claude Haiku 4.5。Enterprise 管理者はモデルポリシー更新が必要
- **Individual プラン変更**: 新規サインアップ一時停止継続、**Opus モデルが Pro から除外**（Pro+ のみ Opus 4.7 可）。6/1 の AI Credits 課金開始へ段階的制限
- https://github.blog/changelog/2026-05-12-copilot-code-review-comment-experience-improvements/
- https://github.blog/changelog/2026-05-08-upcoming-deprecation-of-grok-code-fast-1/

### Cursor — [master][copilot]
- **Microsoft Teams 連携（5/11）**: チャネルで `@Cursor` メンション → スレッド文脈を読み、リポジトリ・モデルを自動選択して PR 作成まで実行
- **Bugbot**: Effort 設定（Default / High / 自然言語カスタム）追加。シート課金を廃止し usage-based 課金へ移行（次回更新時、〜6/8）
- **Cloud Agent Dev Environments 拡充（5/13）**: マルチリポ環境、Dockerfile + ビルドシークレット、監査ログ・ロールバック。Enterprise はモデルアクセス制御・ソフト spend limit
- **セキュリティ**: 悪意ある Git リポジトリ経由の任意コード実行脆弱性を 2.5 で修正済み。未更新チームは速やかにアップデート推奨
- https://cursor.com/changelog/microsoft-teams

### Notion Developer Platform 公開（5/13） — [master]
- **External Agent API** で Claude Code / Cursor / Codex / Decagon を Notion ワークスペース参加者として接続。Workers（Notion ホスト型ランタイム、`ntn` CLI）、Database Sync（Salesforce/Zendesk/Postgres 等）も提供。「Notion をエージェントのコントロールルーム化」する戦略
- https://www.notion.com/blog/introducing-developer-platform

### その他 — [copilot][industry]
- **Devin**: PWA 対応（デスクトップ/モバイルインストール）、ファビコンでの状態表示
- **Raindrop AI「Workshop」**: AI エージェント専用 OSS ローカルデバッガ（MIT License）。全トークン・ツールコールを localhost ダッシュボードへストリーム。Claude Agent SDK / OpenAI Agents SDK / LangChain 等対応
- https://github.com/raindrop-ai/workshop

## Microsoft 365 / Copilot Studio / Power Platform

### Copilot Chat ライセンス変更が実施（5/16） — [copilot]
- 大規模組織（2,000+ ユーザー）では Word/Excel/PowerPoint/OneNote から Copilot Chat が完全削除。小規模組織は「standard access」として継続だが性能変動あり
- Web 版 Copilot Chat / M365 Copilot アプリ / Outlook / Teams は引き続き利用可能。ラベルは無料「Copilot Chat (Basic)」/ 有料「M365 Copilot (Premium)」に変更
- https://chrismenardtraining.com/post/microsoft-365-copilot-chat-changes-on-april-15-2026-what-unlicensed-users-need-to-know/

### Copilot Studio 4月アップデート総括（5/11 月次ブログ） — [copilot]
- **Apps in Agents GA**（Copilot Chat 内にリッチなアプリ体験を埋め込み）、**Analytics Viewer Role GA**（分析への読み取り専用ロール）、Workflows Agent 一元管理、Custom Metrics、Agent Store 拡充（Adobe Express、Box、Figma、Monday.com、Wix）
- **GPT-5.5 Thinking/Reasoning** が Early Release 環境で利用可能に（GCC 除く）
- https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/new-and-improved-agent-governance-intelligent-workflows-and-connected-app-experiences/

### Work IQ API Public Preview — A2A・MCP・REST の3形式 — [copilot]
- M365 Copilot の基盤インテリジェンスへ外部アクセス。A2A（カスタムエージェントがピアとして対話）、MCP（GitHub Copilot から Work IQ CLI 経由）、REST（5月提供）。GA は 2026 年夏予定
- https://techcommunity.microsoft.com/blog/copilot-studio-blog/work-iq-api-public-preview-build-copilot-powered-agents-with-a2a/4516286

### Power Platform May 2026 Feature Update（5/14） — [copilot]
- **Power Apps**: User Defined Types GA（Studio v3.26044、新規アプリでデフォルト有効）、Custom Tools & Rich UI（MCP 対応、Public Preview）、Grid Container GA、**InfoPath Migration Support GA**（Canvas Authoring MCP Server で Claude Code / GitHub Copilot が InfoPath フォームを変換）
- **Power Automate**: Self-Healing（Public Preview、GPT-4.1 mini + Claude Sonnet 4.5 の 2 モデル併用でデスクトップフローの UI 変更を自動修復）、Desktop Flow Testing GA、Record with Copilot（Public Preview）
- **管理**: Entra Agent Users（自律エージェント用専用アカウント、Public Preview）、Power Pages の GitHub Copilot Plugin（Public Preview）
- https://www.microsoft.com/en-us/power-platform/blog/2026/05/14/whats-new-in-power-platform-may-2026-feature-update/

### Power Apps MCP Server にクローズドループ学習（5/12） — [copilot]
- Agent Feed 上のユーザー修正をデータ入力ツールの改善に自動反映。低リスク操作は自動実行・高リスク操作は人間承認のフロー制御
- https://www.microsoft.com/en-us/power-platform/blog/power-apps/power-apps-mcp-server-introduces-closed-loop-learning-for-enterprise-agents/

### M365 アプリの Copilot 強化 — [copilot][industry]
- **Outlook（5/10 発表）**: Classic Outlook に Copilot Insights 拡大、キャンバス内直接ドラフト、Find a Time ペイン、iOS 添付ファイル分析
- **Planner Agent**: Copilot Chat 内で自然言語タスク作成・編集が完結。**Calendar Agent**: 自然言語ルールでスケジュール管理をバックグラウンド自動実行
- **Microsoft Edge Copilot 大幅刷新（5/13）**: 開いている全タブを横断するマルチタブ推論、履歴をトピック別グループ化する「Journeys」、長期記憶。従来の Copilot Mode は廃止しブラウザ本体へ統合
- **M365 Copilot UI 刷新予告（5/12）**: Word/Excel/PowerPoint/Outlook に統一「フローティングボタン + コンテキストプロンプト」を 6 月から展開。Copilot Chat に GPT-5.2 投入
- https://blogs.windows.com/msedgedev/2026/05/13/new-updates-to-edge-across-desktop-and-mobile/

### 管理者向け期限・変更 — [copilot]
- **Conditional Access**: 「All resources」ポリシーがリソース除外付きでも強制適用開始（5/13〜段階展開）
- **Actionable Messages 外部アクセストークン廃止**（5/15、Entra 認証へ切替必須）
- **Agent Registry API → Agent 365 移行**: 新 Graph API は 5/1 提供開始済み、旧 API は 6/15 廃止。未移行エージェントは動作停止
- **Teams Efficiency Mode 展開完了**（5月中旬、デフォルト有効）、**共有カレンダーの REST モデル自動移行**（5〜7月）

## OpenAI / ChatGPT

### OpenAI Deployment Company（DeployCo）正式設立（5/11） — [master][industry]
- 企業向け AI 導入を専業とする majority-owned 新会社。$4B 調達 / プレマネー $10B。TPG リード、Advent / Bain Capital / Brookfield / SoftBank 等 19 社参画
- Forward Deployed Engineers（FDE）を顧客企業に常駐させるPalantir 型モデル。Tomoro 買収で約 150 名の FDE を Day 1 から確保。発表後、Accenture -3%・Cognizant -5% など既存コンサル株が下落
- https://openai.com/index/openai-launches-the-deployment-company/

### OpenAI Daybreak — サイバーセキュリティ専用プラットフォーム（5/11 発表、5/14 詳報） — [master][industry]
- Codex Security をベースに脅威モデル構築 → 脆弱性検証 → パッチ提案を一気通貫で自動化。3 モデル構成（GPT-5.5 / Trusted Access for Cyber / GPT-5.5-Cyber）
- パートナーは Akamai、Cisco、Cloudflare、CrowdStrike、Fortinet、Oracle、Palo Alto Networks、Zscaler。非公開の Anthropic Mythos に対する「公開可能な対抗策」という位置付け
- https://thehackernews.com/2026/05/openai-launches-daybreak-for-ai-powered.html

### ChatGPT Personal Finance（Pro、米国、5/15） — [master]
- Plaid 経由で 12,000+ 金融機関と接続し、ポートフォリオ・支出・サブスクのダッシュボードと Financial memories を提供。Web/iOS、Plus への拡大を検討
- 個人金融データを LLM に渡す形態として、国内・欧州での規制対応が今後の焦点
- https://openai.com/index/personal-finance-chatgpt/

### ChatGPT 安全性・パーソナライズ機能 — [master]
- **Trusted Contact**: 深刻な安全懸念の検知時に事前指定した連絡先へ通知できるオプション（個人プランのみ、段階展開）
- **Memory Sources**: どの記憶（過去チャット・保存メモリ等）が回答の根拠かを Sources アイコンから確認・編集可能に
- https://help.openai.com/en/articles/6825453-chatgpt-release-notes

## Google / Gemini

### Workspace / Gemini App 更新（5月中旬） — [master]
- **Workspace Studio**: Ask NotebookLM step 追加（5/12〜）、Meet ステップが「meeting outputs ready」へ拡張（Notes by Gemini 対応、1 ワークフロー最大 100 ミーティング）、7 言語追加
- **Gemini App**: Deep Research にユーザーファイル/画像をソース追加、Canvas で対話的ビジュアル/クイズ変換、Deep Research が 2.5 Flash で全ユーザー無料化、Practice Quiz
- **Gemini in Vids**: Slides インポート時に AI Avatar スポークスパーソンを挿入。**Skills in Chrome**: 保存プロンプトのワンクリック実行（有料 Workspace）
- https://workspaceupdates.googleblog.com/

### Gemini 3.2 Flash リーク — [master]
- Gemini iOS アプリ、Google AI Studio、LM Arena で痕跡が複数確認。I/O（5/19-20）での正式発表が有力
- https://llm-stats.com/llm-updates

## モデル・新アーキテクチャ

### DeepSeek-V4 シリーズ（Pro / Flash） — [master]
- DeepSeek-V4-Pro（1.6T params / 49B activated）と V4-Flash（284B / 13B activated）を Hugging Face 公開。両モデル 1M token context、hybrid attention で 1M token 推論が V3.2 比 27% FLOPs / 10% KV キャッシュ
- https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro

### Ant Group「Ring-2.6-1T」（5/15 報道） — [industry]
- 1T パラメータ MoE（アクティブ 63B）の推論モデルをオープンウェイト公開（MIT License）。ClawEval で GPT-5.4 xHigh・Gemini 3.1 Pro を上回り、ARC-AGI-V2 66.18 / AIME 26 95.83
- https://huggingface.co/inclusionAI/Ring-2.6-1T

### 新興アーキテクチャ（独立検証は未済） — [industry]
- **Interfaze**（5/12 正式公開）: OCR・STT・構造化出力特化の 3 層アーキテクチャ。9 ベンチで Gemini-3-Flash / Sonnet 4.6 / GPT-5.4-Mini 超えを主張。IEEE CAI 2026 採択
- **Subquadratic「SubQ」**: 12M トークンコンテキスト・サブ二次スケーリングを主張し $29M シード調達。査読論文未公表で研究者から独立検証要求あり
- **Zyphra ZAYA1-8B-Diffusion-Preview**（5/15）: AMD チップで開発した拡散言語モデル
- https://venturebeat.com/technology/miami-startup-subquadratic-claims-1-000x-ai-efficiency-gain-with-subq-model-researchers-demand-independent-proof

## 業界動向・市場

### AI 起因の組織再編・利用動向 — [industry]
- **GitLab**: 「エージェンティック時代」移行を宣言し 7% 人員削減、R&D を 60 の自律チームに再編（5/11）。株価は時間外 8% 下落
- **PayPal**: 全従業員の 20%（約 4,760 名）削減、AI ネイティブ運用モデルへ転換（5/5 発表、2026 年最大のフィンテック削減）
- **Amazon「tokenmaxxing」問題**: 社内 AI 利用リーダーボードの評価利用で、不要タスクをAIに投げてスコアを稼ぐ行為が横行と FT 報道
- **Gallup 調査**: 米労働者の業務 AI 利用が初の 50% 超え（2023 年 21% → 50%）。日次+週次利用 28% で過去最高
- https://www.gallup.com/workplace/701195/frequent-workplace-continued-rise.aspx

### 中国・インフラ投資 — [industry]
- **ByteDance**: 2026 年 AI インフラ投資を 25% 増の約 $30B に引き上げ。**Tencent**: 下半期に投資大幅増、国産チップ（Huawei / Moore Threads 等）で米国製の穴を埋める戦略
- **xAI 共同創業者 Igor Babuschkin が「River AI」設立**: $5B 評価で最大 $1B 調達計画。大手 AI 企業出身者による「neolabs」潮流が継続
- https://www.scmp.com/tech/big-tech/article/3353573/alibaba-tencent-signal-ai-spending-surge-despite-earnings-pressure-china-chips-ramp

### Runway、日本進出（5/15） — [industry]
- 動画生成 AI の Runway がアジア初拠点として東京オフィス開設、初期投資 $40M。企業顧客は 12ヶ月で 300% 増、アジア販売量の 1/3 を日本が牽引。OpenAI Sora の日本撤退が追い風との見方
- https://gigazine.net/news/20260515-runway-comes-to-japan/

### エンタープライズエージェント製品の発表ラッシュ — [master][industry]
- **Salesforce Agentforce Operations GA**（4/29 GA、5月に Flows 連携ベータ）: バックオフィス自動化でサイクルタイム最大 70% 短縮
- **Writer**: プロンプト不要のイベント駆動型エージェント（Gmail/Slack/Drive 監視 → 自然言語ゴールで自律実行）
- **Xactly Fleet of Agents / Freshworks AI Agent Studio**（5/14）、**Glean ADLC**（エージェント開発の 7 段階標準フレームワーク、5/12）
- https://venturebeat.com/orchestration/salesforce-launches-agentforce-operations-to-fix-the-workflows-breaking-enterprise-ai

## 政策・規制・セキュリティ

### 米政府、NVIDIA H200 の中国 10 社への販売を承認（5/14） — [industry]
- Alibaba・Tencent・ByteDance・JD.com 等 10 社に各最大 75,000 チップの購入枠。ただし北京からの指導で中国企業は発注を保留し実出荷ゼロ。最上位 Blackwell は引き続き対中禁止
- 米中 AI 公式対話がトランプ・習近平の北京サミット（5/14-15）で議題に
- https://www.cnbc.com/2026/05/14/us-clears-h200-chip-sales-to-10-china-firms-as-nvidia-ceo-looks-for-breakthrough.html

### AI を使った攻撃・防御の最前線 — [industry]
- **Google GTIG**: 攻撃者が AI でゼロデイ脆弱性を発見・悪用した初の実例（2FA バイパス）を確認（5/11）。悪意あるパッケージ発見数は前年比 +75%
- **Microsoft MDASH**: 100+ の AI エージェント協調で Windows 脆弱性 16 件（うち 4 件クリティカル）を新発見（5/12）
- LLM がパッチ差分から 30 分でエクスプロイト生成可能になり、90 日脆弱性開示ルールの形骸化を複数研究者が指摘
- https://www.cnbc.com/2026/05/11/google-thwarts-effort-hacker-group-use-ai-mass-exploitation-event.html

### ArXiv、AI 生成コンテンツ規制強化 — [industry]
- LLM 出力を未検証のまま論文に含めた著者に 1 年間の投稿禁止。架空引用・AI 生成文言の混入増加が背景
- https://the-decoder.com/arxiv-tightens-penalties-for-ai-bungling-in-scientific-papers/

## 来週の注目予定

- **5/18-22**: Office 365 コネクタ Teams 無効化（Workflows Webhook 移行必須。未対応テナントはサービス断）
- **5/19**: Code with Claude London（Sonnet 4.8 GA の最有力発表ウィンドウ。5/20 に Extended London）
- **5/19-20**: Google I/O 2026（新 Gemini モデル / Gemini Spark、Android 17、Android XR グラス、Aluminium OS）
- **5/19-21**: SAP Sapphire 2026（Anthropic との Business AI Platform 統合詳細）
- **5/20**: NVIDIA 決算（売上 $78B / 前年比 +78% 予想）
- **5/25**: Outlook Lite 完全廃止（Android）
- **5/29**: Copilot Studio Question Themes Analysis GA 予定
- **5/31**: Copilot Studio CLI GA 予定
- **6/1**: GitHub Copilot 全プラン AI Credits（usage-based billing）移行 / Code Review Actions minutes 消費開始
- **6/8**: Cursor Bugbot 使用量課金への移行（次回更新時）
- **6/8-12**: Apple WWDC 2026（iOS 27 のサードパーティ AI モデル選択「Extensions」正式発表見込み）
- **6/10**: Code with Claude Tokyo（6/11 Extended Tokyo）
- **6/15**: Anthropic Programmatic Credit Pool 発効 / Agent Registry API 旧版廃止（Agent 365 移行期限）
- **6/30**: Microsoft 社内 Claude Code ライセンス終了期限

## 前週補遺（2026-05-05 〜 05-10）

旧 W19 ファイルが 4/28〜5/4 の 7 日窓で生成されたため、5/5〜5/10 が週次アーカイブの空白となっている。当該期間の 3 リポのダイジェストから主要トピックを補足する。

- **Code with Claude SF（5/6-7）** — [master][copilot][industry]: Claude Managed Agents に **Dreaming**（セッション横断のパターン抽出・メモリキュレーション、Research Preview）/ **Outcomes**（ルーブリック評価の独立 grader、Public Beta）/ **Multi-Agent Orchestration**（最大 20 エージェント・同時 25 スレッド、Public Beta）。Claude in Chrome ベータの全有料プラン開放、ant CLI 公開、Claude Code の Team Standard シート追加、Claude Code Desktop 全面リデザイン。https://claude.com/blog/new-in-claude-managed-agents
- **Anthropic × SpaceX Colossus 1 契約 + 利用上限の大幅引き上げ（5/6）** — [master][copilot][industry]: Colossus 1（300MW 超 / 220,000+ NVIDIA GPU）の全容量を確保し、Claude Code の 5 時間上限を全プランで 2 倍化・Pro/Max のピーク時間制限を撤廃。API は Tier 1 で入力 +1500% / 出力 +900%。https://www.anthropic.com/news/higher-limits-spacex
- **Anthropic のエンタープライズ攻勢（5/4-5）** — [master][copilot][industry]: Blackstone / Hellman & Friedman / Goldman Sachs と $1.5B のエンタープライズ AI サービス JV 設立。翌日に金融サービス向けプリビルトエージェント 10 種 + Microsoft 365 アドイン（Excel/PowerPoint/Word）GA + Moody's 提携を発表。Google と 5 年 $200B のクラウド/TPU 契約報道（The Information）も。https://www.anthropic.com/news/finance-agents
- **OpenAI の大型ウィーク（5/4-7）** — [master][industry]: The Deployment Company JV 正式発足（$4B/19 投資家）、GPT-5.5 Instant が ChatGPT 既定モデルに（high-stakes 領域の幻覚 52.5% 減）、GPT-Realtime-2 / Realtime-Translate / Realtime-Whisper 公開と Realtime API GA（旧 Beta は 5/7 廃止実施）、Workspace Agents（Enterprise/EDU EKM 向けカスタム GPT 後継）展開。https://openai.com/index/gpt-5-5-instant/
- **Microsoft 5/5 大型発表群** — [copilot]: Copilot Cowork が iOS/Android 対応 + Skills + プラグイン拡張（GA は 7 月予定）、Work Trend Index 2026（知識労働者の 78% が週 1 回以上エージェント利用、「Agent Supervisor」概念提唱）、Federated Copilot Connectors GA（HubSpot / LSEG / Moody's / Notion）、GPT-5.5 Thinking + ChatGPT Images 2.0 を M365 Copilot / Copilot Studio に投入。https://www.microsoft.com/en-us/microsoft-365/blog/2026/05/05/copilot-cowork-from-conversation-to-action-across-skills-integrations-and-devices/
- **開発ツールの集中アップデート（5/6-8）** — [master][copilot]: Cursor 3.3（Parallel Agents「Build in Parallel」、PR Review 刷新、PR Splitting）+ TypeScript SDK Public Beta + CVE-2026-26268（Git hook RCE、CVSS 8.1）修正。GitHub Copilot CLI に Rubber Duck（Claude セッションに GPT 系 critic を当てるクロスモデル批評。Sonnet+GPT で Opus との差の 74.7% を充填）。Devin v3 API GA・Review API・Full Desktop Testing。Claude Code は v2.1.128〜138 の高頻度リリース（worktree.baseRef、autoMode.hard_deny、plan mode 権限境界修正等）。https://github.blog/changelog/2026-05-07-rubber-duck-in-github-copilot-cli-now-supports-more-models/
- **MCP STDIO 設計脆弱性の公開** — [industry]: OX Security が MCP の STDIO トランスポートに任意コマンド実行を許す設計上の問題を指摘。20 万サーバー・累計 1.5 億 DL に影響、CVE 多数。Anthropic は「想定された動作」としてサニタイズ責任を開発者側と回答。MCP サーバー導入時の入力検証は自衛が前提に。https://venturebeat.com/security/mcp-stdio-flaw-200000-ai-agent-servers-exposed-ox-security-audit
- **中国勢オープンウェイトの一斉投入と業界動向** — [industry]: Z.ai GLM-5.1 / MiniMax M2.7 / Moonshot Kimi K2.6 / DeepSeek V4 が 12 日間で連続リリースし、エージェンティックコーディングでフロンティア級・推論コスト 1/3 以下を実現。DeepSeek は初の外部調達を $45B 評価で交渉。ほか DeepL が従業員 25%（約 250 名）削減で「AI-native」再編（5/7）、Microsoft / Google / xAI が米 CAISI のリリース前モデル評価に合意（5/5）、EU AI Act 簡素化の政治合意（高リスク AI 義務を 2027 年末に延期、5/7）。https://techcrunch.com/2026/05/06/deepseek-could-hit-45b-valuation-from-its-first-investment-round/

注記: 補遺期間の入力は 16/18。[master] の 2026-05-09・2026-05-10 が欠損のため、当該 2 日は [copilot][industry] のダイジェストで補完した（モデル / Claude Code 情報が不足の可能性）。

## 改善メモ

- **WebFetch 403 の広域継続（2026-04-02 以降）**: Anthropic 公式（news / research）、OpenAI、Google 系、learn.microsoft.com、mc.merill.net、techcommunity.microsoft.com、cursor.com/changelog、releasebot.io、changepilot.cloud、および [industry] の全 RSS フィードで 403 が継続。3 リポとも WebSearch プライマリ運用が定着。[copilot] は learn.microsoft.com 配下の 403 範囲が拡大している可能性を指摘（5/16）
- **安定して取得できているソース**: Claude Code Changelog（code.claude.com / raw.githubusercontent.com）、GitHub Releases、Microsoft Copilot Blog / Power Platform Blog（WebFetch 成功実績）。raw URL を最初から試行する運用が有効
- **[master] の取りこぼしパターン**: 5/15・5/16 のダイジェストが 5/13-14 の大型発表（Gates Foundation、PwC、GitHub Copilot App、Codex モバイル、Notion Developer Platform、Claude Code v2.1.142/143、2028 レポート）を相次いで取り逃した。「Anthropic 公式・GitHub Blog の直近 3 日分を毎回明示的に再チェックする」ステップの追加を [master] 自身が強く推奨
- **イベント発表の段階的公式化への対応**: Code with Claude SF の発表が 5/6 当日 → 5/7 続報 → 5/8 整理 → 5/11 総整理と分散した。キーノート当日 + 3〜4 日のウォッチ定型化と、「イベント 3-4 日後に確認済み機能を総整理する日」を設ける運用を推奨。Google I/O（5/19-20）は専用の速報セクション/テンプレ運用を検討
- **daily-sources.md への追加提案（[master] 発）**: GitHub Changelog（github.blog/changelog）を高優先ソース化、Notion Releases、xAI / Perplexity の独立セクション、Mistral News URL、OpenAI API Changelog の新 URL（developers.openai.com/api/docs/changelog）への更新、Podcast（All-In / Acquired / Dwarkesh）の補助ソース化
- **常設フォロー項目**: Programmatic Credit Pool バックラッシュ（3 週連続トピック化）。[master] は `.last-check-state.md` の常設フォロー項目への明示を提案
- **リポ間の差異（両論併記）**:
  - Claude Code v2.1.139 のリリース日が [master]=5/11、[copilot]=5/12 と 1 日ずれ（リリースのタイムゾーン差とみられる）
  - OpenAI Daybreak の日付が [industry]=5/11 発表、[master]=5/14 公開ローンチ詳報と段階的で、初出日が不一致
  - Anthropic の ARR は公表ランレート $30B に対し、[industry] 内で「実態は $40B 近い」（5/15）「$45B に迫る」（5/10、補遺期間）と観測値に幅があり、OpenAI 側の「ネット $22B 程度」という反論（5/14）も存在。引用時は「公表ランレート $30B」を基準とし観測値は注記扱いが安全
- **[industry] の週末空白問題**: 5/11・5/12 のダイジェストは前回チェック（5/4）からのキャッチアップを含み、5/5-10 のニュースが W20 入力ファイルに混在していた。本サマリーでは発生日ベースで前週補遺セクションに整理した。日次実行の安定化（または週次キャッチアップフローの正式化）を引き続き推奨
