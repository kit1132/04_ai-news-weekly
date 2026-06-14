# AI ニュース週次サマリー — 2026-W24（2026-06-08 〜 2026-06-14）

> 入力: 取得成功 21 / 21（欠損なし）
> 生成日時: 2026-06-14（JST）

---

## 今週のハイライト

### 1. Claude Fable 5 / Mythos 5 GA → 3日後に米政府令で全世界停止 — AIモデル供給リスクが顕在化

**事実**: Anthropicが6/9にClaude Fable 5（Mythos クラス初の一般公開版）をリリース。SWE-Bench Pro 80.3%（2位に11pt差）、Hex分析ベンチ初の90%超、ほぼ全公開ベンチでSOTA。価格は入力$10/出力$50（per 1M tokens、Opus 4.8の2倍）。Claude API・AWS Bedrock・Vertex AI・Microsoft Foundry・GitHub Copilot・Harvey・Snowflake Cortex AIに同日GA。6/22まで Pro/Max/Team/Enterprise で追加料金なし。ところが6/12 17:21 ETに米商務省（BIS、Lutnick長官名）の指示書が届き、Anthropicは**外国籍ユーザーをリアルタイムに識別できないため、有料エンタープライズを含む全ユーザー向けに両モデルをグローバル停止**して対応した。

**根拠**: Fable 5 = Mythos 5からサイバー/生物化学セーフガードを残した公開版。安全分類器により高リスク領域のクエリは<5%のセッションでOpus 4.8にフォールバックする設計。停止後、進行中セッションはエラー終了し新規クエリはOpus 4.8へ自動ルーティング。Anthropicは「誤解だと考えており、可能な限り早期の復旧に取り組む」と声明。

**影響**: Claude Code、GitHub Copilot（Pro+ 以上限定だったFable 5）、Microsoft Foundry、Devinが連鎖停止。エンタープライズの「単一モデル依存」リスクが一夜にして顕在化。さらにMicrosoftはFable 5停止前の6/10-11時点で、30日間プロンプト/出力保持ポリシー（Zero Data Retention対象外）を理由に社内従業員のFable 5利用を独自にブロック済み。外部顧客向けには即日GA、自社従業員には禁止という二重基準が露呈した。

**行動指針**: 本番ワークフローへのフロンティアモデル組込みには必ずフォールバック先（Opus 4.8, GPT-5.5等）を事前定義すること。Claude Codeユーザーは`fallbackModel`設定で3モデルまで指定可能。Fable 5の復旧時期は未定で「誤解の解消次第」と流動的。

- https://www.anthropic.com/news/claude-fable-5-mythos-5
- https://www.cnbc.com/2026/06/12/anthropic-disables-access-to-fable-5-and-mythos-5-to-comply-with-government-directive.html
- https://venturebeat.com/technology/anthropic-blocks-all-public-access-to-claude-fable-5-mythos-5-following-us-government-order-what-enterprises-should-do

---

### 2. Apple WWDC 2026 — Siri をGemini 1.2Tで全面再構築、iOS 27でマルチプロバイダAIマーケットプレイス開幕

**事実**: 6/8（日本時間6/9早朝）のApple WWDC keynoteで、Tim Cook最後のWWDCとなる大規模発表。**Apple Intelligence Extensions**が正式公開され、Siri・Writing Tools・Image Playground等のシステム機能でClaude/ChatGPT/Gemini/Grokをデフォルトとして選択可能に。iOS 27/iPadOS 27/macOS 27 "Golden Gate"（Intel Mac完全終了）を同時発表。Siriは**Google Geminiベース 1.2T paramsカスタムモデル（年$1Bライセンス）**でクラウドバックボーンを再構築。一方でAFM 3（Apple Foundation Models 3）の詳細が6/10-11のPlatforms State of the Unionで判明し、**推論時にはGeminiモデルもGoogleクライアントコードも使用しない**（Federighi明言）実態が確認された。AFM 3 Cloud Proは**Nvidia GPU on Google Cloud**で動作するApple×Google×Nvidia三社共同インフラ。EU圏ではDMAの兼ね合いでiPhone/iPad向け新Siirは延期。

**根拠**: 従来ChatGPTが独占していたApple Intelligenceのパートナー枠が、Extensionsシステムにより4社並列（Claude/ChatGPT/Gemini/Grok）に拡大。App Store AI Agent カテゴリも新設。Xcode 27ではローカルNeural Engine + Claude/Gemini/ChatGPTへのクラウドルーティングのデュアルエンジン構成。Foundation Models FrameworkはLanguage Model protocol準拠モデル全てをSwift APIで呼び出せる設計。

**影響**: LLMベンダー4社が10億台超のAppleデバイスでOS-levelのデフォルト枠を争う構造に転換。iOS 27 GA想定の9月（Apple CEO交代：Cook→Ternus）が主戦場。AnthropicにとってiOS公式backend獲得はIPO直前期の最重要ディール候補。Gemini障害（6/10 03:26 PDT〜6時間超、Fable 5 GA翌日と重複）が「Apple製品のGoogle依存」議論を加速。

**行動指針**: Apple Developer向けにはFoundation Models Frameworkが今夏オープンソース化予定。App Store Small Business Program参加（累計DL200万未満）はPrivate Cloud Compute上のAFM 3を無料利用可能。Xcode 27対応でSwiftアプリへのClaude/Gemini統合は単一APIで実装可能に。

- https://developer.apple.com/wwdc26/
- https://techcrunch.com/2026/06/08/wwdc-2026-everything-announced-on-siri-ai-os-27-apple-intelligence-and-more/
- https://machinelearning.apple.com/research/introducing-third-generation-of-apple-foundation-models

---

### 3. Anthropic・OpenAI が相次いで機密S-1を提出 — AI IPOラッシュとSpaceX史上最大IPO

**事実**: Anthropicが6/1にSECへ非公開S-1を提出（評価額~$965B、売上ランレート~$47B、前年比約5倍）、OpenAIが6/8に続けて提出（評価額~$852B、Goldman Sachs・Morgan Stanley主幹事、9〜11月上場有力）。同週6/12にはSpaceXが「SPCX」でNasdaq上場（$75B調達、評価額$1.77T、Saudi Aramco超えで史上最大のIPO）。

**根拠**: AnthropicのSeries Hで$65B調達済み。Anthropic自身のコードの80%以上をClaudeが生成（2021〜2025年でエンジニア1人あたりコード出荷量8倍）。6/22〜6/23のFable 5試食期間終了→credit消費移行はIPO前の収益指標前倒し設計とみられる。Mistral AIもEU圏での調達交渉中（€20B評価、€3B目標）。

**影響**: AI大手3社（Anthropic/OpenAI/Google）のCEOが6/15-17のG7サミット（フランス・エビアン）に出席予定。「自主的コミットメントのパッケージ」合意が見込まれ、フロンティアモデルの国際規制枠組みが形成される可能性。DeepSeekが6月のRampトレンディングソフトウェア1位（自己ホストから直接課金へ転換）というコスト競争も並行。

**行動指針**: 6/22-23のFable 5無料期間終了前にusage creditsの確認・設定を完了すること。AnthropicのProgrammatic Credit Pool（6/15施行）とあわせてエージェント系ワークフローの課金体系を見直し推奨。

- https://www.nbcnews.com/business/corporations/anthropic-files-ipo-openai-rcna347897
- https://openai.com/index/openai-submits-confidential-s-1/
- https://www.cnbc.com/2026/05/20/spacex-ipo-live-updates.html

---

### 4. GitHub Copilot トークン課金でコスト爆発 — 最大25倍増の報告、8/31まで救済措置

**事実**: 6/1からのGitHub AI Credits従量課金移行後、開発者から10x〜50xのコスト増報告が続出。Pro+（$39/月）で実質月額$180〜$750、エージェント的ワークフローでコスト高騰が顕著。GPT-4.1を6/1に全廃し高価なモデルへ強制移行。8/31までクレジット増量の救済措置あり。ユーザーレベル予算設定もGA化。

**根拠**: [copilot] リポジトリによると、2時間でクレジットの8%消費、1ファイルレビューで20%消費の事例。エージェントセッション1件で$40消費のケースも報告。Cursor・RooCode・OpenRouter等への移行加速中。

**影響**: Copilot Studio Build 2026.5.4では破壊的変更（GPT-5 Autoが拡張タスク完了エージェントで利用不可化）も重なり、Microsoft AI製品の課金複雑性が増大。Cursor Bugbotの従量課金（平均$1.20/PR）との比較で「PR reviewエージェントの市場SLA価格」議論が定着。

**行動指針**: GitHub Copilotのコスト管理には「ユーザーレベル予算設定」を即時適用推奨。エージェント系ワークフローはUsage Analyticsで1件あたりコストを測定してから拡大。M365価格改定（7/1発効）も重なるため、6/30までのロックイン判断が必要。

- https://memeburn.com/github-copilots-new-pricing-shock-some-developers-say-their-ai-coding-bills-jumped-25x-overnight/
- https://github.blog/changelog/2026-06-01-updates-to-github-copilot-billing-and-plans/

---

### 5. Code with Claude Tokyo — AnthropicのAPAC初開発者カンファレンス、Fable 5とネストsubagentをデモ

**事実**: 6/10にAnthropicがAPAC初の開発者カンファレンス「Code with Claude Tokyo」を開催（日英バイリンガル・同時通訳・ライブストリーム）。Boris Cherny（Claude Code lead）のキーメッセージは「The default isn't 'I'm going to prompt Claude'—the default is now 'I'm going to have Claude prompt itself'」。6/11のExtended Tokyoは独立開発者・アーリーステージ向けlaptops-open workshops形式。

**根拠**: SF（5/6）→London（5/19）→Tokyo（6/10）のシリーズで、日本はAnthropicのAPAC最大ユーザーベース。NEC（4月、30,000人展開）・Hitachi（5月、physical AI）・PwC（6/8拡張提携、30,000人認定プログラム）という3階層の導入実績が背景。

**影響**: Claude Code v2.1.172（6/10）で同時リリースしたsub-agents 5段ネスト（agents kicking off agents）がデモの技術軸。Fable 5 GAから5日連続stable release（v2.1.170〜176）で Tokyo開催に合わせたエコシステム整備を急ピッチで実施。

**行動指針**: Code with Claude Tokyo録画はblog.claude.comで後日公開予定（6/12以降）。Extended Tokyo（独立開発者向け）の録画は別途公開見込み。Boris Chernytのsub-agent設計論は`claudefa.st/blog/guide/agents/nested-subagents`に詳細ガイドあり。

- https://claude.com/code-with-claude/tokyo
- https://www.anthropic.com/news/pwc-expanded-partnership

---

## Claude / Anthropic

### Claude Code v2.1.170〜v2.1.176 — Fable 5 GA後6連続stable release — [master][copilot]

6/9〜6/12の5日間で6リリース。主要変更点：
- **v2.1.170（6/9）**: Fable 5をmodel pickerに追加（必須アップデート相当）。VS Code統合ターミナルからのtranscript保存バグ修正
- **v2.1.172（6/10）**: **sub-agentsが自身のsub-agentsをspawn可能（最大5段ネスト）**。Amazon Bedrockが`~/.aws`からregion自動読込。`/plugin`マーケットプレイス検索バー。1Mコンテキスト固着バグ修正含む20+件
- **v2.1.173（6/11）**: Fable 5モデル名の`[1m]` suffix自動正規化。Windows sandbox起動警告修正
- **v2.1.174（6/12）**: VS Code `/usage` にキャッシュミス/long context/subagent/skill/MCP別attribution追加。`/model`ピッカーのDefault表示修正。enterprise従量課金での誤バナー修正
- **v2.1.175（6/12）**: **`enforceAvailableModels`管理設定追加** — allowlistがDefault modelを制約、user/project設定から拡張不可。enterprise model ガバナンスの実装
- **v2.1.176（6/12）**: `enforceAvailableModels`の環境変数経由抜け穴を修正。日本語セッションのタイトル日本語化。Bedrock credential caching改善（固定1時間→Expiration準拠）

https://code.claude.com/docs/en/changelog

### Claude Code v2.1.169（6/8）— セーフモードとディレクトリ移動 — [copilot]

- **`--safe-mode`フラグ**: 全カスタマイズ無効化（CLAUDE.md/settings/スキル/MCPを全部オフ）でトラブルシュート
- **`/cd`コマンド**: プロンプトキャッシュを維持したままディレクトリ移動
- **`disableBundledSkills`設定**: バンドルスキルを管理設定で無効化可能
- セルフホストランナー`post-session`フック、Enterprise MCP ポリシー適用修正

### Claude Managed Agents — cronスケジュール + vault環境変数 Public Beta — [master][copilot]

6/9-10に公開beta化。
- **Cronスケジュール実行**: 夜間データ同期・週次コンプライアンススキャン等をサーバーレスで定期実行。自前スケジューラー不要
- **Vault環境変数**: シークレット（OAuth/APIキー）をネットワーク境界で注入、サンドボックスにはプレースホルダのみ保持。追加料金なし
- **20+ legal MCPコネクタ + 12実務プラグイン**: リサーチ/契約/ディスカバリ/案件管理/法的支援をカバー
- **connector observability**: 採用状況/エラー/レイテンシ/使用量をClaude製品横断でモニタリング可能。endpoint仕様: `managed-agents-2026-04-01` beta header必須

https://claude.com/blog/whats-new-in-claude-managed-agents

### Claude Corps — $150M・1,000人フェロー・米国NPO配置 — [master]

6/11発表。Anthropic、CodePath、Social Finance三社体制。
- 1,000名を米国NPO（400+組織）に12ヶ月フルタイム配置、年俸$85,000 + Claude token budget
- ホスト組織には$10,000 grant + 無償Claude credits
- 要件: 18歳以上/米国就労資格/正規職歴2年以内、**学位不要**
- 応募締切7/17、第1期100名は10月開始。2027年1月・8月コホートが続く

https://www.anthropic.com/news/claude-corps

### Anthropic Programmatic Credit Pool — 6/15施行 — [master][copilot]

Agent SDK・`claude -p`・GitHub Actions・サードパーティAgent SDKアプリが別クレジットプールに移行。Pro $20/月、Max 5x $100/月、Max 20x $200/月。未使用分繰越不可。クレジット枯渡で自動停止（オーバーフロー課金を手動有効化しない限り）。Claude API側でClaude Sonnet 4 / Claude Opus 4も同日退役。

### PwC × Anthropic 拡張提携 — 30,000人認定プログラム — [master]

6/8発表。Claude Code / Coworkを米国から段階展開し最終的にグローバル数十万人の従業員へ。共同Center of Excellence設立。PwC Office of the CFO（finance専門ユニット）をClaudeで新設。本番運用実績：プロスポーツ運用・保険引受・メインフレーム近代化・HR改革で最大70%の配送時間削減。

https://www.anthropic.com/news/pwc-expanded-partnership

---

## Apple WWDC 2026

### Apple Intelligence Extensions・iOS 27 / macOS 27詳細 — [master][industry]

- **iOS 27 Extensions**: Siri/Writing Tools/Image Playground/Smart Replyでプロバイダをper-feature設定（research=Gemini、coding=Claude、creative=ChatGPT等の用途別ルーティング想定）。9月にGAの見通し
- **macOS 27 "Golden Gate"**: Intel Mac完全終了、Liquid Glass UI改良、Spotlight内蔵Siri AI
- **AFM 3 Cloud Pro**: Nvidia Confidential Computing + Intel TDX + Google Titanチップで暗号化処理。Googleが推論フェーズでデータ不可視を保証。2026年夏フル稼働予定
- **AFM 3 Core Advanced**: 20B parameter on-device sparse architecture（1-4B activate/request）、iPhone 17 Pro以降で動作
- **DMA問題**: EU圏でiPhone/iPad向け新Siri AIを延期。Mac/Apple Watch/Vision Proでは提供

https://www.apple.com/newsroom/2026/06/due-to-dma-siri-ai-delayed-in-eu-for-ios-27-and-ipados-27/

### Xcode 27 — デュアルエンジンAIコーディング + MCP/ACPサポート — [industry]

6/9 Platforms State of the Unionで発表。ローカルNeural Engine（Swift特化モデル、リアルタイム補完）+ クラウドルーティング（Claude/Gemini/ChatGPT、大規模リファクタリング・テスト生成・自律デバッグ）のデュアルエンジン。MCP・Agent Client Protocol対応でサードパーティツール連携可能。エージェントがシミュレータ操作・テスト実行を自律的に実施。

https://www.apple.com/newsroom/2026/06/apple-aids-app-development-with-new-intelligence-frameworks-and-advanced-tools/

---

## Microsoft / GitHub

### Claude Fable 5の社内利用をMicrosoftが禁止 — 外部顧客にはGA — [master][industry]

6/10-11に発覚。Fable 5/Mythos 5の安全分類器運用のため**Anthropicがprompts/outputsをdefaultで30日間保持**（policy違反flag時は最大2年）。Microsoft法務が社内承認できず、内部版GitHub Copilotのmodel pickerからFable 5を除外。外部顧客向けGitHub Copilot/Foundryには6/9同日GA提供。他のClaude（Opus 4.x/Sonnet 4.x）はZero Data Retention規約下で継続利用可。Copilot Enterprise/Business管理者向けにFable 5 policyはdefault offで明示的enable必要。

https://cryptobriefing.com/microsoft-restricts-claude-fable-5-data-retention/

### GitHub Copilot for Fable 5 — Pro+ 以上限定、data retention注意 — [master][copilot]

VS Code（chat/ask/edit/agentモード）/Copilot CLI/Copilot cloud agentで利用可（停止前）。Pro+/Max/Business/Enterpriseのみ対応。Anthropic側30日間retention必須、モデル訓練には不使用。Copilot Enterprise/Business管理者はFable 5 policyを**default off**から明示的に有効化する必要あり。

### Microsoft Federated Copilot Connectors GA — MCPベースのリアルタイム外部データ接続 — [copilot]

6/11 GA。MCPプロトコルで外部データをM365 Chat/Researcher/Excel Agent Modeにリアルタイム統合。初期パートナー：Canva、HubSpot、Intercom、Linear、LSEG、Moody's、Notion等。Admin Center > Copilot > Connectorsから有効化・管理。

https://techcommunity.microsoft.com/blog/microsoft365copilotblog/federated-copilot-connectors---bringing-real-time-enterprise-data-within-microso/4515993

### Microsoft AI Models 7モデル正式発表 — MAI-Thinking-1がフラッグシップ — [industry]

Build 2026（6/2）で発表。MAI-Thinking-1（推論）、MAI-Code-1-Flash（Copilot/VS Code特化、5B params・60% fewer tokens）、MAI-Image-2.5、MAI-Transcribe-1.5（音声認識）を含む7モデル。Azure AI Foundry経由で提供。ただしCommon Crawl等の非ライセンスWebデータ使用の指摘（The Decoder）でクリーンデータ主張との矛盾が議題化。

### 社内Claude Codeライセンスを6/30で打切り → Copilot CLIへ移行 — [industry]

Experiences + Devices部門（Windows/M365/Teams等担当）のClaude Codeライセンスを終了。背景：自社製品Copilotを外部販売しつつ社内でClaude Code普及は矛盾。Copilot Enterpriseは$39/seat/月の定額制で予算管理が容易。

https://www.windowscentral.com/microsoft/microsoft-cancels-claude-code-licenses-shifting-developers-to-github-copilot-cli-a-move-likely-driven-by-financial-motives

---

## Copilot Studio / Power Platform

### Copilot Studio Build 2026.5.4 / 2026.5.5 — [copilot]

**2026.5.4**（展開中）:
- 多言語音声エージェント：言語ごとに音声・速度・ピッチを動的設定
- マルチエージェント分析：インベントリエンドポイント、エージェント別KPI・時系列トレンド
- エンティティ複数値抽出がデフォルト有効化
- **破壊的変更**: GPT-5 Autoが拡張タスク完了エージェントで利用不可。概要分析が「Total sessions」単一指標に変更
- Safe Sharing Governance: 共有/公開/実行時にコネクション共有ポリシー強制

**2026.5.5**（6/9 first available、日本は2026.5.4継続）:
- A2Aプロトコルで`tasks/get`対応（外部エージェントが現在のタスク状態を取得）
- GPT-5.5 Chatでインラインエージェント実行
- 評価シナリオでプロンプトごとにクライアント側コンテンツモデレーションレベルを設定可能
- **セキュリティ**: Anthropicレスポンスのエラー詳細をログから秘匿。AI生成URLの抑制/無害化を既定で有効化

### Power Platform June 2026 Feature Update — [copilot]

6/11公開。
- **Power Apps MCP Server クローズドループ学習（GA）**: エージェントがユーザーの修正をagent feed経由で自動学習し構造化メモリとして保持
- **高度なコネクタポリシー（GA）**: AIツールが利用するコネクタをアクション・内部MCPサーバー単位でガバナンス
- **Power Automateデスクトップフロー バージョン比較（GA）**: サブフロー/アクション/変数/UI要素を並べて差分比較

https://www.microsoft.com/en-us/power-platform/blog/2026/06/11/whats-new-in-power-platform-june-2026-feature-update/

---

## 開発ツール（Cursor / Devin / OpenAI Codex）

### Cursor Bugbot 大幅改善 — 90秒/22%cheaper/10%more bugs + `/review`コマンド — [master][copilot]

6/10頃リリース。内部エンジンをComposer 2.5（Moonshot Kimi K2.5ベース）に置換し:
- レビュー平均時間: 5分 → **~90秒**（90% の runが3分以内）
- バグ検出率: 0.56 → 0.62件/review（+10%）
- コスト: 22%削減
- **`/review`新コマンド**: push前にBugbot + Security Reviewを同時起動。増分review（前回以降の差分のみ）オプション追加

https://cursor.com/blog/bugbot-updates-june-2026

### Cursor 3.7 Design Mode — UIを指差し・声で編集 — [copilot]

6/5リリース。ブラウザ内でUI要素をクリック/描画/音声で直接編集。マルチ要素選択で一括変更。常時オンマイクで音声予約も可能。コンテキスト使用量レポート（system prompt/tool definitions/rules/skills別内訳）追加。

https://cursor.com/changelog

### OpenAI Codex CLI v0.139.0 stable（6/9）— 3連続stable release — [master]

6/4〜6/9の5日間でv0.137.0→v0.138.0→v0.139.0と3段階リリース:
- **v0.139.0**: Code modeがstandalone web searchを直接呼出可能。tool/connector input schemasが`oneOf`/`allOf`構造を保持（MCP/大型schema互換性向上）
- **v0.138.0**: `/app`コマンドでCLI threadをCodex Desktop（macOS/Windows）に引継
- **v0.137.0**: reasoning effort選択柔軟化

### Devin — Windsurf→Devin Desktop正式移行 + Classic廃止迫る — [copilot]

6/2のOTAアップデートでWidsurfがDevin Desktopに自動移行。デフォルト起動画面がAgent Command Centerに変更。6/30 Classic環境セットアップ廃止、7/1 Cascade EOL。ACP（Agent Client Protocol）対応でClaude Agent・OpenCode等を実行可能。Fable 5は6/12に製品から削除（Opus 4.8 / GPT-5.5は継続）。

---

## 規制・政策・セキュリティ

### 米政府輸出管理令でFable 5が全世界停止 — AIモデルの地政学リスク顕在化 — [master][copilot][industry]

（今週のハイライト#1参照）。AI企業にとってのサプライチェーンリスクの新類型として確立。単一モデル依存の危険性とフォールバック設計の重要性を業界全体に示した。

### EU AI Act — 高リスクAIシステム規制が8月2日に本格適用 — [industry]

対象：生体認証・重要インフラ・採用/人事・信用スコアリング・法執行等のAnnex III高リスクAIシステム。義務：リスク管理・データガバナンス・技術文書・人間監視・サイバーセキュリティ要件。違反時は最大€35M or 売上7%の罰金（一部12〜16ヶ月猶予あり）。

https://www.legalnodes.com/article/eu-ai-act-2026-updates-compliance-requirements-and-business-risks

### 独ミュンヘン地裁 — Google AI Overviewの虚偽情報でGoogleの直接責任を認定 — [industry]

6/10報道（事件番号 26 O 869/26）。AI Overviewが存在しない情報を「合成」した事案。裁判所はAI Overviewを「独立した実質的主張」と認定し、従来の検索エンジン免責（BGH判例）は不適用と判断。AIアンサーエンジン全般の法的責任に波及する先例となりうる。

https://the-decoder.com/landmark-german-ruling-declares-googles-ai-overviews-are-googles-own-words-and-makes-it-liable-for-false-answers/

### Mythos Preview — Firefox 18件のパッチから8件の動作exploitを1時間以内に自律生成 — [master]

Help Net Securityが6/9に報告。Mythos Previewが18件のFirefoxパッチから**8件の動作するcode-execution exploitを自律生成**、最初のexploitはパッチ公開から**1時間以内**に完成。N-day→weaponized exploitのリードタイム規制議論の起点となる見込み。

### OpenAI macOS app cert revoke（6/12期限）— TanStack supply chain attack対応 — [master]

5/11のTanStack supply chain attack（Mini Shai-Hulud）でOpenAI社員2端末が侵害。ChatGPT Desktop・Codex App・Codex CLI・Atlasの旧証明書が6/12以降macOS標準保護機能でブロック。顧客データ/IPへの侵害はなし。AI devツールのsupply chain securityがOS級メンテナンスサイクルに組み込まれた初の大規模事例。

### トランプ大統領AI大統領令署名（6/2）— 自主的枠組み — [industry]

「Promoting Advanced AI Innovation and Security」。フロンティアAIモデルを公開前最大30日間、政府へ自主提出を要請（強制力なし）。NSA長官がフロンティアモデル認定閾値の「機密ベンチマークプロセス」を開発。AIサイバーセキュリティ・クリアリングハウスを新設。

---

## 業界動向・市場

### コスト管理が企業課題に — Uber・GitHub Copilot・Cloudflare — [industry][copilot]

- **Uber**: 2026年AI予算を4ヶ月で使い切り月額$1,500キャップ導入。エンジニア95%がAIツールを月次利用、コミット済みコードの70%がAI由来でも予算超過
- **GitHub Copilot**: 最大25倍コスト増（詳細は上記）
- **Cloudflare AI Gateway**: ドル建てAI利用上限をオープンベータで提供（6/5）。日次/週次/月次の予算設定、上限到達時にリクエストブロックまたは安価モデルへ自動ダウングレード

https://blog.cloudflare.com/ai-gateway-spend-limits/

### DeepSeekがRampトレンディング1位 — 自己ホストから直接課金へ転換 — [industry]

6月のRampトレンディングソフトウェアランキングでDeepSeekが1位。従来のオープンソース自己ホスティングから「DeepSeekに直接課金しデータを送信」するパターンへ転換。DeepSeek V4は価格優位で、Anthropic（4月Ramp AI Index: 34.4%）・OpenAI（32.3%）が依然リードするがコスト競争が激化。

https://the-decoder.com/deepseek-topped-ramps-trending-software-vendors-in-june-2026-as-us-companies-chase-cheaper-ai/

### Moonshot Kimi K2.7-Code / Cohere North Mini Code — オープンウェイト攻勢 — [industry]

- **Kimi K2.7-Code**（6/12、Modified MIT）: 1T params MoE（アクティブ32B、384エキスパート）、256Kコンテキスト。Kimi Code Bench v2で+21.8%。ただし「ベンチマークが実利用と乖離」との指摘（VentureBeat）
- **Cohere North Mini Code**（6/9、Apache 2.0）: 30B params MoE（アクティブ3B）、256Kコンテキスト。H100 1基で動作、コーディング専用設計。インターリーブドシンキング対応。中国勢・オープンウェイトでClaude Code/Codexの価格/自己ホスト面に揺さぶり

https://cohere.com/blog/north-mini-code

### Google × SpaceX — 月額$920MのAIコンピュート契約 — [industry]

Googleが約11万基のNVIDIA GPUへアクセスする契約を締結（2026/10〜2029/6、総額~$30B）。Google Cloud側は「Gemini Enterpriseエージェントプラットフォームの短期ブリッジ容量」と説明。AnthropicのGoogle Cloud/Broadcomコンピュートパートナーシップ拡大（BroadcomカスタムAIチップ共同開発も検討）と同週に重なり、Google Cloudが「AIインフラのハブ」として多角的に拡大。

https://techcrunch.com/2026/06/05/google-will-pay-spacex-920m-per-month-for-compute/

### OpenAI Ona（旧Gitpod）買収 — 長時間Codexエージェントを強化 — [industry]

6/11発表。安全な分離クラウドサンドボックスで、開発者がワークステーションを閉じても作業継続。Codexの長時間ジョブ（分単位→数時間〜数日）を顧客のクラウド内で実行。AnthropicのManaged Agents（cron/vault）への対抗軸。Oracle Cloud提携（6/11）と合わせてCodexエコシステム拡張。

https://siliconangle.com/2026/06/11/openai-acquires-ai-agent-orchestration-startup-ona/

### Microsoft Scout — M365全体で動作する常時稼働パーソナルエージェント — [copilot]

Build 2026（6/2）で発表、Private Preview。OpenClaw基盤でTeams/Outlook/OneDrive/SharePointに接続。Work IQでユーザーの作業パターンを学習。Entraエージェントアイデンティティで個別ガバナンス。GitHub Copilotライセンスが前提。

---

## 来週の注目予定

- **6/15（明日）**: Anthropic Programmatic Credit Pool 施行 / Claude API で Sonnet 4 / Opus 4 退役（要移行確認）
- **6/15-19**: Google × Kaggle「AI Agents Intensive」無償5日間コース
- **6/15-17**: G7サミット（フランス・エビアン）— Altman（OpenAI）・Hassabis（DeepMind）・Amodei（Anthropic）が出席、自主的コミットメントのパッケージ合意見込み
- **6/16**: Microsoft Work IQ API GA（A2A + Remote MCP + REST）
- **6/18**: Gemini CLI / Gemini Code Assist IDE拡張サービス終了（Antigravity CLI移行）
- **6/22**: Fable 5 の Pro/Max/Team/Enterprise 追加料金なし期間終了（※停止中のため実質保留）
- **6/22-26**: Gemini 3.5 Pro GA 推定ウィンドウ（Pichai I/O公約の6月内GA、最終週ドロップ予想）
- **6/23**: Fable 5 利用に usage credits 必要化（※停止中のため保留）
- **6/25**: gemini-3.1-flash-image-preview / gemini-3-pro-image-preview 廃止
- **6/27**: GPT-4.5 が ChatGPT から退役
- **6/30**: Devin Classic環境セットアップ廃止 / GPT-5.2・GPT-5.3-Codex 新規API リクエスト不可化 / Copilot Studio Teamsクラシックエージェント作成廃止 / M365価格ロックイン期限
- **6月中旬**: Grok V9-Medium（1.5T params）公開予定（未着地）/ Mistral Vibe Slack連携 Code Mode
- **7/1**: M365価格改定発効（E3 $36→$39等）/ Devin Cascade完全廃止 / Anthropic Claude Partner Network初回階層昇格レビュー
- **7/17**: Claude Corps 第1期応募締切
- **8/1**: M365パッケージング更新完了 / GitHub Copilot クレジット救済措置終了
- **8/26**: OpenAI Assistants API廃止 / o3退役
- **9月**: Apple CEO交代（Cook→Ternus）/ iOS 27・iPadOS 27・macOS 27 Golden Gate GA（Apple Intelligence Extensions + AFM 3本番ローンチ）
- **10月**: Claude Corps 第1期100名フェロー配置開始
- **Q4 2026**: Azure Agent Mesh GA目標

---

## 改善メモ

- [全リポ共通] WebFetch 403が2ヶ月超継続。Claude Code changelog（code.claude.com）のみWebFetch安定、他は全ソースWebSearchフォールバック運用。releasebot.io・GitHub Releases等のサードパーティ集約サイトをフォールバック源として`daily-sources.md`に正式追加推奨（[copilot]リポから4回連続で同提案）
- [master] anthropic.com/news が引き続き403。Claude Corps（6/11）がAnthropicブログ取りこぼしで6/12に遅延掲載。`daily-sources.md`のAnthropicセクションにtheregister.com/washingtonpost.com等の主要メディア横断WebSearchを「公式News取りこぼし検出用フォールバック」として明記推奨
- [copilot] Qiita（4件）・Zenn（3件）・devblogs.microsoft.com M365 Dev BlogのRSSフィードが403化（B-005/B-006/B-007）。WebSearch代替を検討
- [industry] 全RSSフィード（Google News、GIGAZINE、The Decoder、VentureBeat、Publickey、hnrss.org、Product Hunt、GitHub Trending）が403継続
- [master×industry矛盾なし] Fable 5停止について：[copilot]が6/14で初報、[master]が6/13-14ダイジェストでは詳細未掲載（翌週補完予定）。[industry]も6/14未掲載。停止は6/12夜発生で日曜・月曜の各リポの速報ラグに注意
- [master] Snowflake Cortex AI Fable 5 launch partner GA（6/9）が当日のmaster 6/10ダイジェストで漏れ、6/11に補完。Snowflake公式ブログ（snowflake.com/en/blog）の`daily-sources.md`追加を再推奨（3回目）
- [industry] Claude Fable 5 & Mythos 5（6/9）・OpenAI S-1提出（6/8）・Cohere North Mini Code・Docker Gordon GAが過去ダイジェストで未掲載のまま6/12でまとめて掲載される事例が発生。速報性の高いリリース/規制イベントは定例ソース巡回と別枠で「Anthropic/OpenAI/Claude」「規制」キーワードのWebSearchを優先実行することを推奨
- Gemini 3.5 Pro GA（6月内公約）とGrok V9-Medium（mid-June公約）が今週末時点で未着地。来週サマリーで確定報告予定
