# AI ニュース週次サマリー — 2026-W24（2026-06-08 〜 2026-06-14）

> ⚠️ **部分週**（金曜実行のため 2026-06-12 まで。06-13, 06-14 は未来日付）
> 入力: 取得成功 15 / 21（欠損ファイル: 下表参照）
> 生成日時: 2026-06-12（JST）

## ⚠️ 欠損ファイル通知

| 日付 | 欠損リポジトリ | 影響 |
|---|---|---|
| 2026-06-13 | [master][copilot][industry] | 未来日付のため非存在 |
| 2026-06-14 | [master][copilot][industry] | 未来日付のため非存在 |

---

## 今週のハイライト

### 1. Claude Fable 5 リリース — SWE-Bench Pro 80.3%、同日マルチクラウド最広配備

**事実**: Anthropic が 2026-06-09 に Mythos 級モデルの一般公開版「Fable 5」を公開。SWE-Bench Pro 80.3%（2 位に約 11pt 差）、FrontierBench 首位、社内分析ベンチマーク初の 90% 超。入力 $10 / 出力 $50（100 万トークン）。Claude API・AWS Bedrock・Vertex AI・Microsoft Foundry・GitHub Copilot・Harvey・Snowflake Cortex AI に同日展開——フロンティアモデルの同日最広マルチクラウド配備の記録を更新した。

**根拠**: Stripe が 5,000 万行 Ruby コードベース全体のマイグレーションを 1 日で完了（従来チーム 2 ヶ月超）。Vellum AI の独立ベンチマークで同スコアを確認。Pro/Max/Team/Enterprise ユーザーは 6/22 まで無償試用、6/23 より従量課金移行。サイバーセキュリティ・生物化学等の高リスク領域の約 5% のクエリは Opus 4.8 へ自動フォールバック。

**影響**: GitHub Copilot での利用は管理者による明示的な有効化が必要で、Anthropic の 30 日データ保持ポリシーへのコンプライアンス対応が前提条件。セキュリティ研究者は Firefox パッチ 18 件から約 1 時間で 8 件の機能的エクスプロイトを生成できることを確認——安全性クラシファイアのトレードオフが浮上。

**行動指針**: 6/22 までに無償で評価を実施。GitHub Copilot 経由で使う企業は 30 日データ保持ポリシーの法務レビューを先行させること。

- https://www.anthropic.com/news/claude-fable-5-mythos-5
- https://techcrunch.com/2026/06/09/anthropic-released-claude-fable-5-its-most-powerful-model-publicly-days-after-warning-ai-is-getting-too-dangerous/

### 2. Apple WWDC 2026 / iOS 27 Extensions — OS レベルの AI ベンダー 4 社競争が開幕

**事実**: Tim Cook 最後の WWDC キーノート（2026-06-08〜）で iOS 27「Extensions」フレームワークを発表。Claude・ChatGPT・Gemini・Grok を Siri のデフォルト AI として設定可能になり、10 億台超の Apple デバイスへの直接流通チャネルが開かれた。Siri のクラウドバックエンドは Google の 1.2T パラメータ Gemini カスタムモデル（年間 $1B）で全面再構築。macOS 27（コード名「Golden Gate」）は Intel Mac サポートを完全終了し Apple Silicon 専用に。

**根拠**: Gemini クエリは Apple Private Cloud Compute 経由で処理され Google 側には不可視。Siri AI は EU DMA 要件（メッセージング・購入・アプリ制御への幅広いアクセスを要求）のためヨーロッパでは遅延し、まず Mac と Vision Pro で先行提供。iOS 27 の一般提供は 9 月を予定。

**影響**: OS レベルでの AI 分配が明示的に競争化。Anthropic・OpenAI・Google・xAI の 4 社が数億台のデバイスのデフォルト設定を巡って直接競合する構造が確立した。Apple は独自フロンティアモデル開発を断念し「マルチベンダー AI マーケットプレイス」に転換。

**行動指針**: AI サービス提供企業は App Store Extensions 対応を戦略最優先事項に引き上げる。デフォルト設定の獲得競争が始まった。

- https://aiweekly.co/node/2611
- https://www.techradar.com/news/live/apple-wwdc-2026-live

### 3. Microsoft、Fable 5 を従業員に禁止しつつ外販——Copilot との二重基準と Claude Code ライセンス打ち切り

**事実**: Microsoft が自社従業員に Claude Fable 5 の内部利用を禁止（Anthropic の 30 日データ保持ポリシーを法務チームが承認できないため）、同時に GitHub Copilot 経由では外部顧客へ提供を継続。さらに Experiences & Devices 部門（Windows・M365・Teams 担当）が Claude Code ライセンスを 2026-06-30 で打ち切り、GitHub Copilot CLI に一本化。

**根拠**: Claude Code はシート費＋トークン従量制でコスト予測が困難、一方 Copilot Enterprise は $39/seat/月の定額制。「自社製品を外販しつつ社内で競合製品を普及させる矛盾」が組織的意思決定を加速させた。

**影響**: エンタープライズ AI ツール標準化において、データ保持ポリシーの法務審査と定額 vs 従量のコスト可予測性が採否を決める主要因として確立した事例。

**行動指針**: Claude Code 導入済み・検討中の企業は、ベンダーのデータ保持条件を法務レビューの標準チェック項目に組み込む体制を整備する。

- https://www.windowscentral.com/microsoft/microsoft-cancels-claude-code-licenses-shifting-developers-to-github-copilot-cli-a-move-likely-driven-by-financial-motives

### 4. Anthropic & OpenAI が S-1 機密申請——AI 最大手 2 社が同年 IPO を目指す

**事実**: Anthropic が 2026-06-01 に、OpenAI が 2026-06-08 に SEC へ S-1 ドラフトを機密提出。Anthropic 評価額 $965B（ARR $47B、前年比約 5 倍）、OpenAI 評価額 $852B（Goldman Sachs・Morgan Stanley 主幹事、9〜11 月上場有力）。同週には SpaceX が史上最大 IPO を完了（2026-06-12、$75B 調達、評価額 $1.77T）——AI・テック上場ラッシュが同時進行。

**根拠**: Google が SpaceX の GPU 約 11 万基を $920M/月・総額 $30B で契約（2026/10〜2029/6）。OpenAI が Oracle Cloud 経由でモデル・Codex の提供を発表（6/11）。$300B 超の Stargate インフラパートナーシップの延長。

**影響**: 両社上場後は公開企業として財務指標と開発戦略が直接比較される。パブリック市場からの資本調達で AI 開発競争が一段と加速する見込み。

**行動指針**: 株主・投資家向けの AI ガバナンス・収益性開示が本格化する前に、企業利用契約の条件と将来コスト見通しを再確認する。

- https://www.nbcnews.com/business/corporations/anthropic-files-ipo-openai-rcna347897
- https://openai.com/index/openai-submits-confidential-s-1/
- https://techcrunch.com/2026/06/05/google-will-pay-spacex-920m-per-month-for-compute/

### 5. Gemini 6 時間超の大規模障害——Fable 5 同時リリースで可用性が競争軸に

**事実**: 2026-06-10 03:26 PDT より Gemini Flash・Pro モデルが 6 時間超にわたって障害（エラーコード 1076・1099）。Web・モバイル・Chrome インタフェース全域に影響し、Flash Lite のみ断続的に応答。WWDC 2026 期間中かつ Fable 5 ローンチと重なり、フロンティアプロバイダ間の稼働率比較が表面化。

**根拠**: Fable 5 はリリース初日から AWS Bedrock・Vertex AI・Microsoft Foundry 等に分散配備し単一障害点を低減。Claude Code v2.1.166 で `fallbackModel` 設定（最大 3 モデル指定・過負荷/障害時に自動切替）が先行して追加済み。

**影響**: エンタープライズ採用においてモデル性能だけでなく稼働率・冗長構成が主要調達要件として明確化されつつある。

**行動指針**: ミッションクリティカルな用途では Claude Code の `fallbackModel` 設定で冗長化を構成し、単一モデル依存を排除する。

---

## AI モデル・研究

### Fable 5 詳細 — [master][copilot][industry]

- SWE-Bench Pro 80.3%（2 位 +11pt）、FrontierBench 首位、社内分析ベンチマーク初の 90% 超（Opus 比 +10pt）
- 長時間・複雑タスクほど他モデルとの差が拡大する設計
- 6/22 まで無償試用（Pro/Max/Team/Enterprise）、6/23 より従量課金
- Snowflake Cortex AI が同日ローンチパートナーとして統合（Bedrock・Foundry・Copilot・Harvey と並ぶ最広同日展開）
- 高リスク領域の約 5% クエリは Opus 4.8 へ自動フォールバック

### Google Gemini — [master][copilot][industry]

- **Gemini 3.5 Live Translate GA（6/9）**: 70 言語超のリアルタイム音声翻訳。文末を待たず数秒遅延で話者の声調・ペース・ピッチを保持しながら連続翻訳。Google 翻訳アプリで即日グローバル提供、Google Meet は Workspace プランでプライベートプレビュー（https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-live-3-5-translate/）
- **Gemini Flash 管理者トグル廃止**: Enterprise 向け Gemini 3.5 Flash の地域別無効化オプションを削除、全域で必須化
- **大規模障害（6/10）**: 6 時間超、Flash/Pro 停止、Flash Lite のみ断続対応

### その他モデル・ハードウェア — [industry]

- **Cohere North Mini Code（6/9）**: 30B パラメータ MoE、Apache 2.0 ライセンス。H100 単基で動作するコーディングエージェント。256K コンテキスト、インターリーブドシンキング対応（https://cohere.com/blog/north-mini-code）
- **NVIDIA Cosmos 3（Computex）**: 世界初の完全オープン Physical AI オムニモデル。テキスト・画像・動画・音声・アクションを統合処理、ロボティクスベンチマーク 7 カテゴリ超で 1 位（https://gigazine.net/gsc_news/en/20260602-nvidia-cosmos-3/）
- **NVIDIA RTX Spark**: Blackwell GPU + Grace CPU（NVLink-C2C）、統合メモリ 128GB、1 PFLOPS。今秋発売予定（https://www.tomshardware.com/laptops/nvidia-unveils-rtx-spark-superchip-at-computex-2026）
- **Alibaba Qwen 3.7 Plus GA（6/1）**: ビジョン・コンピュータユース対応、Qwen 3.7 Max の約 1/6 のトークン単価（https://www.marktechpost.com/2026/06/02/alibabas-qwen-team-launches-qwen3-7-plus）

---

## 開発者ツール（Claude Code / Copilot / Cursor）

### Claude Code — [master][copilot]

- **v2.1.172-173（6/11-12）**: サブエージェントネスト最大 5 階層、Fable 5 統合修正（48 時間以内に 3 連続安定リリース）
- **v2.1.166（6/6）**: `fallbackModel` 設定で最大 3 モデル指定（過負荷・不可時に自動切替）、deny ルール glob パターン対応、`SendMessage` クロスセッションのセキュリティ強化（中継メッセージがユーザー権限を持たなくなり auto モードでブロック）（https://code.claude.com/docs/en/changelog）
- **Managed Agents 公開ベータ**: cron スケジューリング・Vault 環境変数、20+ 法務向け MCP コネクタ、12 業務別プラグイン（リサーチ・契約・訴訟・ケース管理）

### GitHub Copilot / Copilot Studio — [copilot]

- **従量課金ショック継続（6/1〜）**: 月額 $29 が最大 $750 の報告（25 倍）。8 月末まで一時クレジット救済継続。ユーザーレベル予算設定が GA（https://memeburn.com/github-copilots-new-pricing-shock-some-developers-say-their-ai-coding-bills-jumped-25x-overnight/）
- **GPT-5.5 Instant / Thinking Models 追加**: Copilot に新モデルオプション追加、xAI 統合向けガバナンスも拡充
- **Copilot SDK GA**: 6 言語（Node.js・Python・Go・.NET・Rust・Java）、MCP 統合対応（https://github.blog/changelog/2026-06-02-copilot-sdk-is-now-generally-available/）
- **Copilot Studio Build 2026.5.4**: 多言語音声エージェント（言語ごとに音声・速度・ピッチ個別設定）、マルチエージェント分析ダッシュボード追加。GPT-5 Auto が拡張タスク完了エージェントで利用不可に（https://learn.microsoft.com/en-us/power-platform/released-versions/copilotstudio/2026.5.4）
- **Federated Copilot Connectors GA（6/9）**: MCP プロトコルベース。Canva・HubSpot・Notion・Linear 等が接続可
- **Copilot Notebooks の Basic ユーザー拡張（6 月中旬）**: SharePoint Embedded コンテナに保存、テナントストレージ消費
- **Edge Browsing 限定プレビュー**: Copilot が Edge for Business 内で自律的にページナビゲーション・フォーム入力・マルチステップ操作。IT 管理者が URL 許可リスト・DLP・Purview 監査ログを制御（H2 2026 GA 予定）

### Cursor — [master][copilot]

- **Cursor 3.7 Design Mode（6/5）**: UI を直接クリック・描画・音声指示でエージェントに変更を指示。常時マイクオン・マルチ要素選択対応、エージェント実行中の次変更を音声でキューイング可（https://cursor.com/changelog）
- **Bugbot 新料金**: $40/月シート制 → 純粋な従量課金（$1-4/PR）。3 倍速（平均 90 秒）、22% コスト削減、10% 高い不具合検出率に改善

---

## プラットフォーム・インフラ

### Apple — [master][copilot][industry]

- **Apple Foundation Models**: 5 モデル構成（オンデバイス + クラウドバリアント）。Cloud Pro は NVIDIA GPU 経由で Google Cloud が稼働——Apple・Google・NVIDIA 三者パートナーシップ
- **Apple Private Cloud Compute 初の外部展開**: NVIDIA Confidential Computing + Intel TDX + Google Titan チップでエンドツーエンド暗号化処理。クエリは Google 側からも不可視（https://security.apple.com/blog/expanding-pcc/）
- **Xcode 27**: ローカル Swift モデル + Claude・Gemini・ChatGPT へのクラウドルーティングによる二重エンジン AI コーディング

### Microsoft 関連インフラ — [copilot][industry]

- **MXC（Execution Containers）**: AI エージェント向け OS レベルサンドボックス。ミリ秒起動、IT 管理者がファイル・ネットワーク・アプリアクセスを宣言的に制限。OpenAI・NVIDIA が採用パートナー
- **Microsoft Scout（Private Preview）**: M365 全体で動作する常時稼働型自律 AI エージェント。OpenClaw 基盤。Teams・Outlook・OneDrive・SharePoint に接続。Work IQ でユーザーの作業パターンを学習（https://www.microsoft.com/en-us/microsoft-365/blog/2026/06/02/introducing-microsoft-scout-your-always-on-personal-agent/）
- **Azure Linux 4.0 パブリックプレビュー**: Fedora ベース・Kernel 6.18 LTS・Python 3.14。汎用 Linux として初の Azure VM/VMSS/コンテナ対応（https://www.publickey1.jp/blog/26/linuxazure_linux_40azurewsl.html）

### その他インフラ — [industry]

- **Cloudflare AI Gateway コスト上限 OB（6/5）**: ドル建て日次/週次/月次予算設定。上限到達時にブロックまたは安価モデルへ自動ダウングレード。JWT ユーザー ID と連携した従業員別コスト可視化（https://blog.cloudflare.com/ai-gateway-spend-limits/）
- **Cloudflare × VoidZero 買収（6/4）**: Vite・Vitest・Rolldown・Oxc のオープンソース維持を保証（https://blog.cloudflare.com/voidzero-joins-cloudflare/）
- **Docker Gordon GA**: Docker Desktop 4.74+ 統合、無償アカウントで利用可能（https://www.docker.com/blog/meet-gordon-dockers-ai-agent-for-your-entire-container-workflow/）
- **Perplexity「Search as Code」**: AIエージェント向け検索スタック。モデルが検索パイプラインを Python コードとして直接組み立て、従来比トークン使用量 85% 削減（https://research.perplexity.ai/articles/rethinking-search-as-code-generation）
- **Perplexity ハイブリッドローカル/クラウド推論（Computex）**: 機密データをローカル処理、高負荷推論はクラウドへ自動ルーティング。7 月 Perplexity Computer（Windows）で提供開始予定（https://venturebeat.com/technology/perplexity-ai-unveils-hybrid-local-cloud-inference-system-at-computex-2026）
- **Google Cloud × SpaceX $920M/月 GPU 契約**: 約 11 万基の NVIDIA GPU、総額 $30B（2026/10〜2029/6）（https://techcrunch.com/2026/06/05/google-will-pay-spacex-920m-per-month-for-compute/）

---

## ビジネス・料金

### Anthropic 課金変更（6/15〜）— [copilot][master]

- Agent SDK・`claude -p`・GitHub Actions・サードパーティアプリが別クレジットプール（新設）に移行
- インタラクティブプール（変更なし）: Claude.ai Web/デスクトップ・Claude Code 対話利用・Cowork
- Agent SDK プール: Pro $20/月、Max 5x $100/月、Max 20x $200/月。API リスト価格で消費、繰越なし
- **要アクション**: 6/15 までに Anthropic からのメールでクレジットを請求（https://codersera.com/blog/anthropic-june-2026-billing-change-claude-code/）

### M365 価格改定 & GitHub Copilot — [copilot][industry]

- M365 E3 $36 → $39（7/1 発効）。6/30 以前に契約すれば現行料金でロック可能
- GitHub Copilot: 8 月末まで一時的なクレジット救済継続
- **Uber AI コスト事例**: エンジニアの 95% が AI ツールを月次利用、コミット済みコード 70% が AI 由来。月額 API コストがエンジニア 1 人 $500〜$2,000 で年間予算を 4 ヶ月で使い切り → 月額 $1,500 キャップを導入（https://fortune.com/2026/05/26/uber-coo-ai-spending-tokens-claude-code/）
- **Anthropic 本番コードの 80% 超が Claude 作成**: エンジニア 1 人あたりのコード出荷量が 5 年間で 8 倍に（https://venturebeat.com/technology/anthropic-says-80-of-its-new-production-code-is-now-authored-by-claude-how-your-enterprise-can-keep-up）

### 市場データ / ベンダー動向 — [industry]

- **Similarweb AIトラッカー（2026/4）**: ChatGPT 54.7%、Gemini 27.4%、Claude 8.2%（前四半期比 +306%）、DeepSeek 4.1%、Grok 2.8%
- **DeepSeek が Ramp 6 月トレンディング 1 位**: 自己ホスティングから「直接課金・データ送信」パターンへ転換が進む（https://the-decoder.com/deepseek-topped-ramps-trending-software-vendors-in-june-2026-as-us-companies-chase-cheaper-ai/）
- **Meta Hatch（7 月米国ローンチ予定）**: 月額 $200 の AI エージェント製品。開発中は Claude Opus 4.6 で動作、ローンチ時は Meta 自社モデル Muse Spark に切替（https://the-decoder.com/metas-hatch-ai-agent-could-cost-up-to-200-a-month-and-marks-its-first-paid-ai-product/）
- **OpenAI Codex 大幅拡張（6/2）**: Sites（社内 Web アプリ自動生成）、Annotations（AI レビュー）、6 業務別プラグイン（Salesforce/Jira/Notion 等 62 アプリ統合）。非開発者ユーザーがエンジニアの 3 倍速で増加中（https://openai.com/index/codex-for-every-role-tool-workflow/）

---

## 規制・法務

### EU AI Act 施行（2026-08-02）— [industry]

- 高リスクシステム（生体認証・信用スコアリング等）への義務化発効。違反時は最大 €35M または年間売上 7%

### ドイツ裁判所：Google AI Overview は Google 自身の発言 — [industry]

- ミュンヘン地裁仮処分（26 O 869/26）。AI Overview が存在しないソース情報を「合成」した事案で、従来の検索エンジン免責（BGH 判例）が不適用と判断。AI アンサーエンジン全般の法的責任に波及する可能性（https://the-decoder.com/landmark-german-ruling-declares-googles-ai-overviews-are-googles-own-words-and-makes-it-liable-for-false-answers/）

### コロラド州 AI 法 大幅縮小・2027/1 延期 — [industry]

- 包括的リスクベース AI 法を廃止・置換。透明性・開示に特化した狭いアプローチへ転換（https://www.hunton.com/privacy-and-cybersecurity-law-blog/colorado-ai-act-amended-and-effective-date-delayed）

### トランプ AI 大統領令（6/2）— [industry]

- フロンティアモデルの公開前最大 30 日の政府への自主提出を要請。強制力なし。NSA が機密ベンチマーク基準を設定（https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/）

### CVE-2026-45497（M365 Copilot CVSS 9.8）— [copilot]

- コマンドインジェクション脆弱性。Microsoft がサーバーサイドで公開前にパッチ済み。要対応: 6/4 以前 2 週間の Entra ID ログ監査・サービスプリンシパル権限レビュー

### macOS 証明書失効デッドライン（6/12）— [master][copilot]

- OpenAI の 6/12 証明書失効期限が ChatGPT Desktop 等に影響（TanStack サプライチェーン攻撃を受けての対応）。即時ユーザーアップデートが必要

---

## 来週の注目予定

- **2026-06-14**: M365 Copilot 自動インストール Phase 1 完了
- **2026-06-15**: Anthropic Agent SDK 課金分離——Pro $20/月クレジット有効化必須（メールからの請求が必要）
- **2026-06-15**: Claude API 旧モデル廃止（Sonnet 4・Opus 4）
- **2026-06-15**: M365 Conditional Access リソース除外ポリシー強制適用（MC1223829）
- **2026-06-16**: Work IQ APIs GA（A2A + Remote MCP + REST）
- **2026-06-22**: Fable 5 無償試用終了（Pro/Max/Team/Enterprise）
- **2026-06-23**: Fable 5 従量課金開始
- **2026-06-30**: Devin Classic 環境廃止 / Cascade EOL
- **2026-06-30**: Copilot Studio Teams クラシックエージェント作成廃止・感度ラベル表示 GA
- **2026-06-30**: M365 現行価格ロックの最終期限（7/1 E3 $36→$39 値上げ前）
- **2026-07-01**: Cursor Teams 新価格適用
- **2026-08-02**: EU AI Act 高リスクシステム義務化発効
- **2026-08-31**: GitHub Copilot クレジット救済終了

---

## 改善メモ

（[master][copilot][industry] の改善メモを統合・重複排除）

- **[全 RSS フィード]** Google News・GIGAZINE・The Decoder・VentureBeat・Publickey・hnrss.org・Product Hunt・GitHub Trending RSS が引き続き 403 継続。全ソース WebSearch フォールバックで対応
- **[Claude Code changelog]** WebFetch 403（https://code.claude.com/docs/en/changelog）。WebSearch + releasebot.io 経由で取得。releasebot.io 自体も WebFetch 403 のため WebSearch から間接取得
- **[mc.merill.net]** WebFetch 403 継続。WebSearch 経由で取得
- **[M365 Copilot Release Notes]** ファイルサイズ 18,000 行超。Microsoft Learn MCP 経由で取得後 grep で差分確認
- **[Copilot Studio What's New]** Microsoft Learn MCP 経由で取得。May 2026 が最新（6 月分はまだ未掲載）
- **[Business Insider Japan 料金早見表]** 月次定点情報として活用開始（https://www.businessinsider.jp/article/2606-how-much-did-major-generative-ai-service-fees-become-in-jun-2026/）
- **[MM 総研]** 2025 年 8 月調査から更新なし。2026 年調査待ち
- **[Perplexity Computer]** 7 月ローンチ予定のハイブリッドローカル/クラウド推論製品（Windows）をフォローアップ予定
- **[Meta Hatch]** 7 月米国ローンチ予定（開発中 Claude Opus 4.6 動作、ローンチ時 Muse Spark に切替）をフォローアップ予定
- **[SpaceX IPO]** AI 企業ではないが Google $920M/月 GPU 契約・OpenAI・Anthropic IPO ラッシュと並ぶ AI インフラ資本の動向として引き続き追跡
- **[GitHub Trending]** OpenClaw が 21 万 stars 超で安定。大きな変動なし
