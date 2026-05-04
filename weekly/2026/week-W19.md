# AI ニュース週次サマリー — 2026-W19（2026-04-28 〜 2026-05-04）

生成日時: 2026-05-04（JST）
対象期間: 2026-04-28（月）〜 2026-05-04（日）
入力リポジトリ: kit1132/01_ai-news-master / kit1132/02_ai-news-copilot / kit1132/03_ai-news-industry

---

## ⚠️ 欠損ファイル通知（部分生成）

以下のダイジェストファイルが存在しないため、該当日は他2リポジトリの情報のみで補完しています。

| 日付 | 欠損リポジトリ | 影響 |
|------|--------------|------|
| 2026-04-29 | kit1132/01_ai-news-master | モデル/Claude Code 情報が不足の可能性 |
| 2026-04-30 | kit1132/02_ai-news-copilot | Copilot/Power Platform 情報が不足の可能性 |
| 2026-05-03 | kit1132/01_ai-news-master | モデル/Claude Code 情報が不足の可能性 |

---

## 今週のトップライン

- **Microsoft-OpenAI 独占契約解消**（4/27）: OpenAI が AWS・Google Cloud 等全クラウドで製品提供可能に。Azure 優先は維持、AGI 条項撤廃。翌日に AWS Bedrock でOpenAI モデル提供開始
- **Anthropic $900B 評価で $50B 調達検討**（4/29）: ARR $30B 到達。5 月取締役会で方針決定予定
- **Microsoft Agent 365 / M365 E7 GA**（5/1）: $15/user/月のエージェントガバナンスプラットフォームと $99/user/月の Frontier Suite が正式提供開始
- **Claude Code v2.1.111→v2.1.126**: 週間 15 リリースの継続的アップデート
- **Musk vs OpenAI 裁判**: 4/28 開廷、$150B 損害賠償と Altman・Brockman 解任を要求
- **Pentagon AI 契約**: AWS/Google/Microsoft/NVIDIA/OpenAI/SpaceX 等 7 社と締結、Anthropic は除外

---

## 1. モデル・技術

### 新モデルリリース

#### Mistral Medium 3.5（5/2）
- 128B dense・256k context・マルチモーダル（vision encoder スクラッチ学習）
- SWE-Bench Verified **77.6%**（Devstral 2 / Qwen3.5 397B を上回る）
- 修正版 MIT ライセンスでオープンウェイト公開（`mistralai/Mistral-Medium-3.5-128B`）
- Le Chat の既定モデルに格上げ
- https://mistral.ai/news/vibe-remote-agents-mistral-medium-3-5

#### xAI Grok 4.3（4/30）
- 入力 $1.25/M tokens、出力 $2.50/M tokens（前モデル比 入力 -40%・出力 -60%）
- 1M トークンコンテキスト、Artificial Analysis Intelligence Index 53 点
- Sonnet 4.6 同等性能で 5 倍安価と評価される
- https://venturebeat.com/technology/xai-launches-grok-4-3-at-an-aggressively-low-price-and-a-new-fast-powerful-voice-cloning-suite

#### その他リリース（週前半までの情報補完）
- **Claude Opus 4.7**（4/16 リリース・今週の各ダイジェストで多数参照）: SWE-bench Verified 87.6%、新 `xhigh` エフォートレベル
- **GPT-5.5**（4/23-24）: 1M コンテキスト、API $5/$30 per MTok
- **GPT-5.4 mini / nano**: 高速・低コスト派生モデル

#### ベンチマーク比較
- Claude Opus 4.7 vs GPT-5.5: 共有 10 ベンチ中 6 つで Opus 4.7 がリード
- GPT-5.5: サイバー攻撃テスト（UK AISI）で Claude Mythos に並ぶ「High」評価
- DeepSeek V4 Pro（NIST 評価）: フロンティアから約 8 ヶ月遅れ、コスト効率は GPT-5.4 mini を 7 ベンチ中 5 つで凌駕

### モデル廃止・変更
- **Claude Sonnet 4 / 4.5 の 1M コンテキスト β 廃止**（4/30）: `context-1m-2025-08-07` betaヘッダーが無効化。200k 超は Sonnet 4.6 / Opus 4.6 以降へ移行必須
- **OpenAI Realtime API Beta**（5/7 廃止予定）
- **Sora アプリ版**（4/26 停止、API は 9/24 まで）

---

## 2. 開発ツール

### Claude Code（週間ハイライト）

今週は v2.1.111 → v2.1.126 まで約 15 リリース。主要変更点を抜粋:

| バージョン | 主な変更 |
|-----------|---------|
| v2.1.111 | `/ultrareview`（マルチエージェントコードレビュー）、`/less-permission-prompts`（許可リスト自動生成）、PowerShell tool |
| v2.1.117 | デフォルト effort → high（Pro/Max Opus 4.6/Sonnet 4.6） |
| v2.1.118 | Vim visual mode、カスタムテーマ（`~/.claude/themes/`）、MCP tool hooks、`/usage` 統合 |
| v2.1.119 | 設定の `~/.claude/settings.json` 永続化、prUrlTemplate、GitLab/Bitbucket/GitHub Enterprise PR URL 対応 |
| v2.1.120 | `claude ultrareview [target]` サブコマンド、Windows: Git for Windows 不要に、Skills の `${CLAUDE_EFFORT}` 参照 |
| v2.1.121 | `alwaysLoad` MCP サーバー設定、`claude plugin prune`、PostToolUse `updatedToolOutput` |
| v2.1.122 | `ANTHROPIC_BEDROCK_SERVICE_TIER` 環境変数、PR URL から `/resume`、OpenTelemetry 改善 |
| v2.1.123 | OAuth 401 リトライループ修正 |
| v2.1.126 | `/model` ピッカーがゲートウェイ `/v1/models` 結果を表示、`claude project purge`、セキュリティ修正（`allowManagedDomainsOnly` バイパスを修正）、画像 2000px 超の自動ダウンスケール |

なお v2.1.119/120 で 8 件のリグレッション（自動更新破損・サイレントモデルスワップ等）が一時報告され、v2.1.123 以降で修正済み。

- https://code.claude.com/docs/en/changelog

### Cursor

#### Cursor 3.2（4/24）
- `/multitask`: 非同期サブエージェントで並列実行
- Self-Hosted Cloud Agents: プライベートネットワーク内でコード実行
- Canvases: インタラクティブなビジュアル表現
- 大規模編集のフレーム落ちを約 87% 削減
- https://cursor.com/changelog

#### Cursor Security Review ベータ（4/30〜5/1、Teams/Enterprise）
- Security Reviewer: 全 PR を自動チェック（脆弱性・認証リグレッション・プロンプトインジェクション等）
- Vulnerability Scanner: スケジュールスキャンで既知 CVE・依存古さを検出、Slack 通知対応
- https://cursor.com/changelog/04-30-26

#### Cursor SDK パブリックベータ（4/29）
- TypeScript SDK でランタイム・ハーネス・モデルにプログラマティックアクセス
- 各エージェントが専用サンドボックス VM で稼働、サブエージェント・フック・SSE ストリーミング対応
- https://cursor.com/changelog/sdk-release

### GitHub Copilot

#### GitHub Copilot in Visual Studio April Update（4/30）
- Cloud Agent Sessions: IDE 内からリモートコーディングセッションを直接起動
- Debugger Agent: ライブランタイムでバグ再現・修正を検証
- C++ Code Editing Tools GA（クラス継承階層・関数コールチェーン）
- IntelliSense 優先: IntelliSense アクティブ時は Copilot 補完を抑制（デフォルト化）
- ユーザーレベルカスタムエージェント対応
- https://github.blog/changelog/2026-04-30-github-copilot-in-visual-studio-april-update/

#### GitHub Copilot CLI v1.0.36→v1.0.40（週間）
- `/remote`・`/keep-alive` コマンド追加
- MCP サーバー `client_credentials` OAuth グラント対応
- `/research` がオーケストレーター/サブエージェントモデルに刷新
- 6/1 全プラン usage-based billing 移行（5 月初旬にプレビュー請求 UI）

#### 注意: VS Code 1.118 Copilot co-author 問題（5/2-3）
- `git.addAICoAuthor` のデフォルトが "off" → "all" に変更され、Copilot 未使用でもコミットに「Co-Authored-by: Copilot」が挿入される問題が炎上
- v1.119 で元の動作に戻す方針
- https://github.com/microsoft/vscode/issues/313064

### Gemini CLI
- v0.40.0（4/28）: 階層メモリシステム、過去セッションから自動 Skill 生成、Gemma ローカルルーティング
- v0.40.1（5/1）: バグ修正パッチ

### Devin
- Fast Mode（約 2x 高速、4x ACU 消費）
- Desktop Testing: Computer Use で Linux デスクトップアプリの E2E テスト対応
- Devin Review: チャット内でコード編集提案しコミットとして直接適用可能
- v3 API 正式版: RBAC・セッション帰属・新機能追加
- https://docs.devin.ai/release-notes/2026

---

## 3. エンタープライズ製品

### Microsoft Agent 365 / M365 E7 Frontier Suite GA（5/1）

#### Agent 365（$15/user/月）
- エージェントの Observe / Govern / Secure コントロールプレーン
- マルチベンダー対応: OpenAI / Anthropic Claude / ServiceNow / Workday / LangChain 等を一元管理
- GA 時点はライセンスユーザー代理エージェントのみ対象。自律エージェントは Frontier Preview 継続

#### M365 E7（$99/user/月）
- M365 E5 + M365 Copilot + Entra Suite + Agent 365 のバンドル
- Copilot Wave 3: Word/Excel/PowerPoint のライブ編集（受動提案→アクティブ実行へ）
- Copilot Cowork（Claude 統合）含む

- https://www.microsoft.com/en-us/microsoft-agent-365

### M365 Copilot 主要アップデート

- **Copilot Studio 新モデル追加**: Grok 4.1 Fast / GPT-5.3 Thinking / GPT-5.4 Instant（実験プレビュー）
- **Researcher「Critique」機能**: GPT が起案、Claude がレビューする二重チェック
- **Excel Copilot**: GPT-5.5 / Claude Opus 4.7 対応、Plan Mode（変更計画の事前確認）
- **Copilot Notebooks 強化**: マインドマップ・外部 Web リンク参照・PPT/Word 生成
- **M365 Admin Center**: 「Copilot in M365 apps with Anthropic models」設定追加（5/4〜）。Excel/PowerPoint でデフォルト有効

### Power Platform

- **Power Apps Agent Feed + MCP Server GA**（5/4）: モデル駆動型アプリ内でエージェント活動を監視・承認
- **Flex Routing 拡張**（5/4）: Power Platform 環境・Copilot Studio・Dynamics 365 に展開
- **Power Platform Monitor Code App アラート GA**（5/4）: ヘルス閾値・プロアクティブ通知
- **Work IQ API Public Preview**（5 月）: REST API・MCP リモートサーバー経由で M365 業務コンテキスト取得

### Claude Security 公開ベータ（Enterprise、5/1）
- Opus 4.7 搭載、コードベース全体スキャン・データフロー追跡・パッチ生成
- スケジュールスキャン・CSV/Markdown エクスポート
- 連携: CrowdStrike / Microsoft Security / Palo Alto Networks / SentinelOne / Wiz
- https://claude.com/product/claude-security

### Claude for Creative Work（4/28）
- Adobe（50+ ツール）・Blender・Autodesk Fusion・Ableton・Splice 等 9 つのコネクターをリリース
- Anthropic は Blender Development Fund のパトロンに就任
- https://www.anthropic.com/news/claude-for-creative-work

### Mistral Workflows（4/28、パブリックプレビュー）
- Temporal ベースのエンタープライズ向け AI ワークフローオーケストレーション
- 制御プレーンは Mistral 管理、実行は顧客環境（クラウド/オンプレ/ハイブリッド）
- ASML・ABANCA・CMA-CGM 等が本番利用中
- https://mistral.ai/news/workflows

### Mistral Vibe Remote Agents（5/2）
- クラウド VM 上で並列に走るコーディングエージェント（CLI / Le Chat から非同期起動）
- Le Chat Work Mode: メール / カレンダー / Docs / Jira / Slack を同時操作

---

## 4. 提携・資金調達・M&A

### Microsoft-OpenAI 提携条件の大幅変更（4/27）
- Microsoft の OpenAI API 独占販売権を撤廃。OpenAI は AWS・Google Cloud 等でも提供可能に
- Microsoft のレベニューシェア支払いを終了、逆に OpenAI→Microsoft の支払いへ（2030 まで、上限付き）
- AGI 達成時の IP 権利変動条項を撤廃
- Azure は OpenAI 製品の優先クラウドパートナーを維持（非独占）
- https://blogs.microsoft.com/blog/2026/04/27/the-next-phase-of-the-microsoft-openai-partnership/

### AWS-OpenAI 拡張パートナーシップ（4/28〜4/29）
- Amazon Bedrock 上で GPT-5.5 / GPT-5.4 等のモデル、Codex、Managed Agents（限定プレビュー）
- OpenAI と AWS が共同開発の「ステートフルランタイム」でエージェントの長期コンテキストを保持
- https://aws.amazon.com/about-aws/whats-new/2026/04/bedrock-openai-models-codex-managed-agents/

### Anthropic 資金調達動向
- **Google $40B 投資確認**（4/24）: $10B 確定＋$30B 追加オプション。2027 年 5GW コンピュート供与含む
- **$900B 評価での $50B 調達検討**（4/29〜30）: ARR $30B 到達。5 月取締役会で方針決定
- **IPO 10 月検討継続**: Goldman Sachs・JPMorgan・Morgan Stanley との協議中

### 中国、Meta による Manus $2B 買収を阻止（4/27）
- 中国商務部が Singapore 拠点 AI スタートアップ Manus 買収をブロック
- 米中 AI 競争が M&A レベルでも直接衝突した初の大型事例
- https://www.cnbc.com/2026/04/27/meta-manus-china-blocks-acquisition-ai-startup.html

---

## 5. 業界動向・市場

### Big Tech AI CAPEX 2026 年合計 $725B（前年比 +77%）
- Google $190B、Amazon $200B、Meta $125-145B、Microsoft $190B
- Q1 だけで $130B 消化
- エネルギー価格上昇・DRAM 急騰がコストを押し上げ

### OpenAI 業績・Musk vs OpenAI 裁判

**業績**: ChatGPT 年末 10 億 WAU 目標は未達、月次収益目標も複数回未達（WSJ 報道）

**裁判**（4/28 開廷）:
- Musk が $150B 損害賠償と Altman・Brockman の解任を要求
- 4/29: 反対尋問で実際の寄付額が $38M にとどまっていた点が争点化
- OpenAI のIPO 計画（2026 年内）に直接影響する可能性

### Meta Q1 2026 決算（4/29）
- 売上 $56.3B（前年同期比 +33%）、純利益 $26.8B（+61%）
- 2026 年 CAPEX を $125-145B に上方修正
- Zuckerberg: 「数十億人にパーソナル超知能を届ける軌道に乗っている」

### テック業界レイオフ
- 4 月単月で約 4 万人。Oracle 約 3 万人、Meta 約 8,000 人、Snap 約 1,000 人（従業員 16%）
- 2026 年 1-4 月累計約 9.2 万人、うち約 48% が AI・自動化を理由に挙げる

### Stripe Sessions 2026（4/29-30、計 288 件発表）
- Link agent wallet: エージェントが決済を代行、使い捨てカード番号方式
- x402 Foundation: Stripe/Coinbase/Cloudflare 等 22 社が agentic payments 標準化
- https://stripe.com/newsroom/news/sessions-2026

### Cloudflare Project Think（4/29-30）
- 長時間稼働エージェント向け新プリミティブ（Durable Objects、Dynamic Workers 等）
- `@cloudflare/codemode`: MCP ツール呼出を単一プログラム化、トークン消費 99.9% 削減を実証
- https://blog.cloudflare.com/project-think/

### その他注目
- **Amazon 商品ページに会話型 AI「Join the chat」**（4/28）
- **X 広告プラットフォームを AI で再構築**（5/2）: Grok でセマンティックターゲティング、5/5 リリース開始
- **Novo Nordisk × OpenAI 戦略提携**（4/14）: 創薬から製造・サプライチェーンまで AI 全面統合
- **ICT 総研 生成 AI 利用率 54.7%**（2026 年 2 月調査、前回比 +25.7pt）
- **インターネット新規サイトの約 1/3 が AI 生成コンテンツ**（Stanford・ICL・Internet Archive）

---

## 6. 政策・規制・セキュリティ

### Pentagon AI 契約（5/1）
- AWS/Google/Microsoft/NVIDIA/OpenAI/SpaceX/Reflection AI の 7 社と IL6/IL7 機密ネットワーク向け AI 契約締結
- Anthropic は自律兵器・国内監視への利用拒否で除外（サプライチェーンリスク指定中）
- https://www.washingtonpost.com/technology/2026/05/01/pentagon-ai-deals-microsoft-amazon-google-classified-military/

### Mythos（Claude の高度モデル）を巡る動向
- ホワイトハウスが約 70 社への追加アクセス計画に反対（4/30）
- NSA は Mythos Preview を実利用中との報道（Axios・TechCrunch）
- Trump 大統領「DOD との合意は可能」とコメント

### EU DMA 対応
- EU 当局が Google に対し Gemini 等への競合アクセス開放をガイダンス（4/27）
- Android での競合 AI サービスアクセス拡大を要求。パブリックコメント期限 5/13

### Google DeepMind 従業員 600 人超が Pentagon AI 利用に反対署名（4/27）
- Pichai CEO 宛の公開書簡。機密軍事ワークロードへの AI 提供を拒否するよう要求
- https://www.washingtonpost.com/technology/2026/04/27/google-employees-letter-ai-pentagon/

### LLM インフラ向け重大脆弱性
- **LMDeploy（CVE-2026-33626、CVSS 7.5）**: SSRF 脆弱性、公開後 13 時間未満で悪用開始
- **LiteLLM（CVE-2026-42208、CVSS 9.3）**: 認証前 SQL インジェクション、36 時間以内に標的型攻撃。v1.83.7 で修正済み
- https://thehackernews.com/2026/04/litellm-cve-2026-42208-sql-injection.html

---

## 7. M365 管理者向け今後のスケジュール

| 日付 | イベント |
|------|---------|
| 5/5 | X 広告プラットフォーム新バージョンリリース |
| 5/7 | OpenAI Realtime API Beta 廃止 |
| 5/8 | OpenAI macOS アプリ証明書更新期限（更新しないとブロック） |
| 5/15 | アクション可能メッセージ外部アクセストークン廃止（MC1189663） |
| 5/16 | M365 Copilot Chat ライセンス変更（未ライセンスユーザーは Basic に制限） |
| 5/16 | Message Center 投稿見出し構造標準化（MC1282308） |
| 5/31 | Copilot Studio CLI GA |
| 6/1 | GitHub Copilot 全プラン usage-based billing 移行 |

---

## ソース別入力状況

| 日付 | 01_ai-news-master | 02_ai-news-copilot | 03_ai-news-industry |
|------|:---:|:---:|:---:|
| 2026-04-28 | ✓ | ✓ | ✓ |
| 2026-04-29 | **欠損** | ✓ | ✓ |
| 2026-04-30 | ✓ | **欠損** | ✓ |
| 2026-05-01 | ✓ | ✓ | ✓ |
| 2026-05-02 | ✓ | ✓ | ✓ |
| 2026-05-03 | **欠損** | ✓ | ✓ |
| 2026-05-04 | ✓ | ✓ | ✓ |
