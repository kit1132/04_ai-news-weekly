# AI ニュース週次サマリー — 2026-W34（2026-08-17 〜 2026-08-23）

> 生成日時: 2026-08-24（JST）

## 今週のハイライト

### 1. Copilot Tuning が8/20で停止し、未完了の調整実行が破棄された — 「いつでもやり直せる」前提が消えた

**要点**: Microsoftが8/20、Agent BuilderのCopilot Tuningを停止し、未完了のモデル調整実行を破棄した。前提は「いつでも再調整できる」から「期限内に終えないと失われる」へ変わった。移行先はCopilot StudioのSkills基盤。

**詳細**: 告知はMessage Center MC1454393（8/14付）のみ。Optimizationテンプレートは退役するが既存エージェントとファインチューニング済みモデルは動作を継続し、自動移行はない。再開はPublic Previewが2026年9月・GAが12月。一次のLearnページ3本は停止・退役の記載を最後まで載せておらず、`copilot-tuning-overview`は「サポートされるシナリオ」節にOptimizationを現行機能として掲示し続けた。

- https://learn.microsoft.com/en-us/microsoft-365/copilot/copilot-tuning-overview
- https://learn.microsoft.com/en-us/microsoft-365/copilot/copilot-tuning-faq

### 2. Manus が Meta 買収後のユーザーデータを削除した — 復元は8/25以降のみ

**要点**: 中国当局の命令でMeta・Manusの$2B買収が解消し、2025-12-29以降に生成されたユーザーデータが8/23〜24に削除された。バックアップの猶予はこの週で尽き、復元は8/25以降に限られる。

**詳細**: Meta買収完了は2025-12-29。中国NDRCが技術輸出・外国投資規制違反を理由に撤回命令を出し、2026-08-12に買収が正式解消した。削除は8/23 08:00（シンガポール時間）から8/24にかけて実施され、対象は買収完了後に生成された分のみ。告知はManusアプリ内とメールで行われた。

- https://www.scmp.com/news/us/article/3363704/facebook-parent-meta-unwind-us2-billion-manus-ai-deal-after-beijing-block
- https://www.trendingtopics.eu/manus-becomes-independent-again-following-2b-meta-deal-and-deletes-user-data/

### 3. GhostApproval が6つのAIコーディング支援ツールで承認画面を偽装できると判明した — 人間の承認が統制の最後の砦にならない

**要点**: Wizが公開した脆弱性パターンで、Claude Code・Cursor・Amazon Q Developer等6製品の承認ダイアログの表示パスと実際の書き込み先が食い違う。「人間が承認しているから安全」という統制設計の前提が崩れた。

**詳細**: 手口はシンボリックリンク追従とUI誤表示の組み合わせで、無害に見えるパスを承認させるとSSH鍵などが差し替わる。対応はAmazon Q Developer・Cursor・Google Antigravityが修正済み、Windsurf・Augmentは未修正、Anthropicは「利用者がディレクトリを承認した時点でリスクを引き受けている」としてthreat model外と判断した。⚠️ 現行のClaude Code（v2.1.240）は該当バージョンより新しく、実務上の判断は変わらない。本件は7/8公開だが本リポジトリ群が42日遅れで捕捉した。

- https://thehackernews.com/2026/07/ghostapproval-symlink-flaws-could-let.html
- https://www.infosecurity-magazine.com/news/ghostapproval-flaw-ai-coding/

### 4. Claude API で Computer Use・Files API・Agent Skillsが GA、Browser Use tool も新設された — beta前提の保留理由が消えた

**要点**: Anthropicが8/19、Claude APIのComputer Use・Files API・Agent SkillsをGAし、新設のBrowser Use toolも公開した。betaヘッダーが不要になり「betaだから本番に載せない」という保留理由が消えた。

**詳細**: Browser Use toolはページのアクセシビリティツリーを直接読み、要素参照でレイアウト変化に耐える。Computer Useは1ターンで複数アクションを返すバッチ実行に対応した。beta ヘッダーを送るリクエストは従来形式のまま動くため既存コードの改修は不要。導入事例Asteroidは処理時間32分→13分・コスト約30%減・完了率100%を報告している。⚠️ Browser Use tool は Claude API 限定でBedrock等では使えない。

- https://platform.claude.com/docs/en/release-notes/api
- https://platform.claude.com/docs/en/agents-and-tools/tool-use/browser-use-tool

### 5. Claude Code の週次利用上限50%増が8/31まで延長され、恒久化の検討が初めて明言された — 上限到達時に人が張り付く前提が消えた

**要点**: Anthropicが週次上限50%増を8/31まで延長し、プランの恒久的な変更にしたいと初めて明言した。あわせて利用上限リセット時にセッションを自動継続する機能も既定で入り、上限に当たったら人が戻って再開する前提が消えた。

**詳細**: プロモーションは5/13開始で7/19→8/19→8/31と3度目の延長。過去は毎回「一回限り」の書き方だったが今回は恒久化の意思を明示した。対象はPro/Max/Teamとシート課金のレガシーEnterpriseで、5時間枠の5/6恒久倍化は本件と独立。自動継続（v2.1.234）は`/config`でオフにできる。

- https://code.claude.com/docs/en/changelog

---

## Claude Code / Claude Developer Platform

### 週内に v2.1.234〜v2.1.240 まで7版が公開された — [master][industry]
- Claude Codeが週内に7版を連続公開した。v2.1.234（8/17）は利用上限リセット時の自動継続を既定にし（ハイライト5参照）、Windows NT名前空間パスの拒否範囲をリモートファイル読み取り等5経路へ広げた。v2.1.235（8/18）は承認ダイアログの表示内容と実際の許可範囲を常に一致させ、内容を全表示できない場合は「今後確認しない」自体を出さなくなった（ハイライト3のGhostApprovalと同じ論点）。v2.1.236（8/19）はmacOS sandboxのワイルドカードread-denyルールが許可読み取り領域の内側でも優先されるようにし、リネームによる読み取り制限の迂回を塞いだ。v2.1.237（8/20）は前置きと実況を省く「Concise」出力スタイルを追加した。v2.1.239（8/21）はBedrockプロキシ経由の二重課金バグとUS限定推論1.1倍プレミアムのコスト見積もり未反映を修正した。
  - https://code.claude.com/docs/en/changelog

### npm の dist-tags で latest 先行状態がいったん解消した — [master]
- npmの`dist-tags`は週初`{stable: 2.1.224, latest: 2.1.233, next: 2.1.234}`から動き、8/23時点で`{stable: 2.1.231, latest: 2.1.240, next: 2.1.240}`になった。`next`が`latest`を先行し続けていた状態（8/15以降6例）がいったん解消し、`stable`との差も10版から9版へ縮んだ。
  - https://registry.npmjs.org/@anthropic-ai/claude-code

### Claude Enterprise の Admin API がユーザー管理を GA した — [master][industry]
- Claude Enterprise向けAdmin APIのユーザー管理エンドポイント（members / invites / groups / custom roles）が8/19にGAし、group・custom-roleの要求に`anthropic-beta`ヘッダーが不要になった。同日、Claude ConsoleのWorkbenchはPlaygroundへ改称され、Messages APIの全パラメータとSDKリクエスト・APIレスポンスの全文表示に対応した。ConsoleのセッションビューアもタイムラインのミニマップとInspectorパネルを備えて刷新された。
  - https://platform.claude.com/docs/en/release-notes/api

### Managed Agents に Web ツールのドメイン制限とセルフホストのメモリ接続が入った — [master][industry]
- Claude Managed Agentsの`web_search`/`web_fetch`に許可・拒否ドメインを設定できるようになり（8/19）、既存の`name`/`enabled`/`permission_policy`だけのリクエストはそのまま動く。同日、self-hosted sandboxでもmemoryストアを接続できるようになり、データレジデンシー要件でセルフホストを選んだ組織にも永続メモリが開いた。
  - https://platform.claude.com/docs/en/managed-agents/tools

## Claude 製品 / Anthropic

### Anthropic が Model 2 の存在を開示し misalignment risk を引き上げた — [master]
- Anthropicが8/14公開のAugust 2026 Risk Reportで、misalignment riskの評価をvery lowからlowへ引き上げ、Claude Mythos 5を上回る未公開モデル「Model 2」の存在を開示した。同社が公表しないモデルが手元で使える上限ではないことが明らかになった。human feedbackベンダー経由のトラフィックが約13カ月間・約1.33億件、生物学分類器を通らずに流れていたことも開示している。
  - https://www.axios.com/2026/08/14/anthropic-model-2-ai-risk

### Claude Security が Mythos 5 に切り替わり Enterprise で追加課金なしに使えるようになった — [master]
- Claude Securityの脆弱性スキャンが8/21にMythos 5へ切り替わり、全Claude Enterprise顧客がpublic betaで追加のサブスクリプション契約なしに使えるようになった。課金はスキャンしたコード量に比例するトークン従量制。あわせてオープンソースのセキュリティ向けにClaudeクレジット$35M分を配るDefender Advantage Fundも始まった。
  - https://claude.com/blog/bringing-claude-mythos-5-to-more-defenders

### Anthropic Python SDK が v1.0 になり httpx を捨てた — [master][industry]
- Anthropicが8/20、Python SDK v1.0を公開しHTTP層をhttpxからhttpx2へ移した。Python 3.10未満、旧Text Completions API、Messagesの`temperature`/`top_p`/`top_k`が同時に削除され、既存のPython連携は無変更では上がらない。`AnthropicBedrock`はAWSリージョン未設定時に`us-east-1`へ暗黙フォールバックせずエラーを投げるようになった。
  - https://github.com/anthropics/anthropic-sdk-python/blob/main/MIGRATION.md

### Anthropic の年換算売上が約$650億に達したと報じられた — [master][industry]
- Anthropicの年換算売上が7月末時点で約$650億に達したとBloombergが報じた（非公式）。IPOは今月末にも申請の可能性があり、規模はSpaceXの記録（$1.77T評価額）に並ぶか上回る見込みと報じられている。Q2は速報値で調整後営業利益が初めて黒字化し、計算コストは売上1ドルあたりQ1の71セントからQ2の56セントへ下がった。
  - https://www.cnbc.com/2026/08/15/anthropic-revenue-jumps-to-over-11point5-billion-in-q2-report.html

### 導入事例と研究成果が相次いで公開された — [master][industry]
- ABC Legal（本番稼働エージェント50超・対象タスク費用約50%減）、Slack CPOインタビュー（会話履歴のナレッジベース化）、monday.com（エージェント対話500万件）、Claude Scienceプロダクトガイド（ローカルdaemon構成・beta継続）が公開された。⚠️ いずれもROIの絶対値は記事に無い。研究面ではClaudeがde novoタンパク質結合体を15標的中14で成功させたと技術報告があり、Adaptyv BioとTwist Bioscienceの独立CROが測定し、48時間セッションでMythos Previewのヒット率26.7%（通常10〜15%）を確認した。
  - https://claude.com/blog/how-abc-legal-turned-every-employee-into-a-builder-with-claude-managed-agents
  - https://www.anthropic.com/research/Claude-accelerates-protein-design

## GitHub Copilot / Microsoft 365 Copilot / Power Platform

### Copilot Studio の新規エージェントに Entra Agent ID が必須になった — [copilot]
- Copilot Studioが8/21、全新規エージェントにEntra Agent IDを強制するようになり、環境レベルのオプトアウトが消えた。既存エージェントに自動移行経路はなく、低使用は廃止でよいが高使用（日次会話・本番業務・Teams連携）は公式の自動移行経路が出るまで作り直さないよう案内されている。条件付きアクセスなどEntraのセキュリティ機能を広げるにはMicrosoft Agent 365ライセンスが要る。
  - https://learn.microsoft.com/en-us/microsoft-copilot-studio/admin-use-entra-agent-identities

### メーカー資格情報でエージェントを動かす経路を塞ぐ機能が3件並んだ — [copilot]
- Copilot StudioのRoadmapに、メーカーの資格情報でエージェントを動かすことを塞ぐ機能が3件見つかった。管理者がメーカー資格情報の使用を禁止する566997はGA期日が2026年8月（今月）、資格情報オーバーシェアの検出566873はGA9月、自律エージェントのRun-Only共有567894はGA2027年1月である。566997は月末まで残り8日の時点でも`In development`のままだった。
  - https://learn.microsoft.com/en-us/microsoft-365/admin/manage/mrc-mcp

### Microsoft Copilot アプリの統合で Group Chat が履歴ごと削除された — [industry]
- Microsoftが8/18、消費者向けと商用のCopilotアプリを統合し、Web URLを`copilot.cloud.microsoft`へ移した。同時にGroup Chat・Podcasts・消費者向けDeep Researchが廃止され、**Group Chatのスレッドと画像は退避手段なく完全削除**された。Deep Researchの保存済みレポートは残るが新規作成はできない。デスクトップ版は早期プレビューが始まり、広範な展開は9月中旬から。
  - https://www.techrepublic.com/article/news-microsoft-copilot-app-merger/

### Copilot for JetBrains と Slack / Microsoft Teams への展開で統制語彙が広がった — [copilot][industry]
- GitHubがCopilot for JetBrainsに`managed-settings.json`による企業管理設定を導入し（8/18）、プラグイン・MCPサーバー・OpenTelemetry・権限モードを中央統制できるようにした。8/21にはSlack・Microsoft Teamsでの共有エージェント機能が公開プレビューに入り、`@GitHub`メンションで開始したセッションがチーム共有の専用チャンネルに載る。リポジトリ管理者はエージェント作成PRのマージに追加承認を必須化できる。
  - https://github.blog/changelog/2026-08-18-enterprise-managed-settings-in-github-copilot-for-jetbrains
  - https://github.blog/changelog/2026-08-21-the-new-github-copilot-experience-in-slack

### 自己申告型のコネクタ接続とメモリ保持のガバナンス機能が Roadmap に並んだ — [copilot]
- Copilot Studioが利用者自身の資格情報でJira/Confluenceを接続できるSelf-serve sync connectorsを起票し（Preview 8月・GA 9月）、統制の重心が事前の敷設から事後の可視化へ寄る。Copilotメモリの保持・バージョン管理をPurviewで扱う機能（569612・GA 9月）も起票され、Exchangeメールボックスの隠しフォルダーに置かれるメモリが保持ポリシーの対象になり得ることが判明した。Teams会議・通話向けInteractive Agentsは9月GA予定だったが8/17に中止された。
  - https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=569612

## OpenAI / Codex / ChatGPT

### GPT-5.6 Sol が20%超値下げされた — 少なくとも11/21までの暫定措置 — [master]
- OpenAIが8/21、GPT-5.6 SolのAPI単価を入力$5→$4・出力$30→$20へ下げた。公式はpromotional rateと明記し、少なくとも2026-11-21まで有効。適用範囲は従量課金APIとCodexクレジット、対象ChatGPT Workプランで、Pro/Plus/Businessの定額サブスクリプションは対象外。
  - https://community.openai.com/t/20-price-reduction-for-gpt-5-6-sol-api-codex-credits-and-chatgpt-work/1391726

### ChatGPT for Teens が展開され年齢推定で自動振り分けされるようになった — [master][industry]
- OpenAIが8/18、13〜17歳向けのChatGPT for Teensを展開した。自己申告の未成年に加え、年齢推定システムが18歳未満と見積もったアカウントも自動でこのモードに入る。性的・ロマンチックなロールプレイや自傷等への制限が強まり、保護者はアカウント連携で設定を管理できる。
  - https://www.axios.com/2026/08/18/openai-chatgpt-for-teens

### ChatGPT Ads が欧州31市場へ展開される — [master]
- OpenAIが8/24（本サマリー期間の直後）にChatGPTの広告を欧州31市場へ展開すると8/19に告知した。表示対象はFree/Goのみで、Plus以上は広告なしを維持する。会話履歴への広告主アクセスはないと明言されている。
  - https://openai.com/index/chatgpt-ads-expands-across-europe/

### OpenAI DevDay Exchange が8都市で開催され東京は10/20 — [master]
- OpenAIが8/18、10月からDevDay Exchangeとして8都市で開発者イベントを開くと告知した。東京開催は10/20で、応募締切は9/17。従来の単一開催・基調講演型とは組み立てが異なる。
  - https://community.openai.com/t/openai-devday-is-going-global/1391106

### Codex CLI が安定版 0.148.0・0.149.0 を相次いで公開した — [master]
- Codex CLIの安定版が8/18に0.148.0（Amazon Bedrockを組み込みプロバイダに追加）、8/20に0.149.0（`codex agents`ダッシュボード・`codex queue`・`codex doctor`の診断拡張）と続けて出た。pre-releaseは0.150.0系まで進んだが、多くの版で本文が1行のみで内容を確認できない状態が続いている。
  - https://github.com/openai/codex/releases

## Google

### Ask Gemini in Chat が発表され Gemini 3.5 Pro の未GA が続く — [master]
- GoogleがWorkspace Intelligenceを基盤にAsk Gemini in Chatを発表した。Google Chat上でGmail/Drive/カレンダーを横断検索できる機能で、ロールアウトは8/26開始。⚠️ プロモーション枠の高上限は10/1までで、試用の結論はこの期間内に出す必要がある。Gemini 3.5 ProのGAはI/O発表後6月→7月→7/17と3回スリップしたまま未ローンチが続く。
  - （WebSearch経由・一次はゲートウェイ拒否）

### Gemini API の単価は据え置き、Imagen 4 系は停止済み — [master][industry]
- Gemini 3.7 Flash / 3.6 Flashの導入価格（入力$0.75/出力$3.75）は2026年12月31日まで有効で、2027年1月1日に$1.50/$7.50へ倍増する。Imagen 4.0の標準・ultra・fast各生成エンドポイントは8/17に停止済み。
  - https://ai.google.dev/gemini-api/docs/pricing

## Cursor / xAI / Devin

### Cursor が Origin でコードホスティングに参入した — [master]
- Cursorが8/17、自前のgitホスティングとPR、GitHub双方向同期を持つOriginを全有料プランへ早期ベータで配り始めた。Vercel/Depot/Buildkiteのアプリ拡張が使え、Vercel連携ではPRごとにプレビューデプロイが付く。「コードはGitHubに置き、エージェントはIDEから呼ぶ」という前提が崩れる。
  - https://cursor.com/changelog/origin-code-hosting

### Cursor Cloud Agents に Subscriptions が入り監視型の起動が可能になった — [master]
- Cursorが8/19、Cloud AgentsにSubscriptionsを追加した。PRやSlackスレッドの監視、スケジュール実行の3つの発火条件を持ち、人が都度起動して結果を待つ前提から条件成立で自動的に動く前提へ変わる。サブエージェントをそれぞれ別の仮想マシンで走らせる独立実行にも対応した。
  - https://cursor.com/changelog

### Grok 4.6 が Amazon Bedrock で GA した — [master]
- xAIのGrok 4.6が8/19、Amazon Bedrockで一般提供された。US GeoとGlobalの2推論プロファイルから選べ、xAIと個別契約せず既存のIAM/CloudTrail/コスト管理の枠内で評価できる。価格は入力$2/出力$6。
  - https://aws.amazon.com/about-aws/whats-new/2026/08/amazon-bedrock-grok-4-6/

## AI セキュリティ・ガバナンス

### GhostApproval と Copilot Autofix 悪用事例で AI 支援コードの検証工程が焦点になった — [industry]
- ハイライト3のGhostApprovalに加え、Wizの攻撃側エージェントがSnowflakeの公開リポジトリでCopilot Autofix由来とされるコマンドインジェクションを発見し、社内Jiraの読み取りまで5日で到達した事例が明らかになった。Wiz側は当該コミットにCopilot Autofixがco-authorとして関与したとする一方、GitHub側は人間が書いた変更で関与もレビューもないと否認しており、当事者の見解が割れている。
  - https://www.wiz.io/blog/red-agent-snowflake-copilot-cicd-bug

### GLM-5.3 がサイバー能力を理由にウェイト公開を延期した — [industry]
- Z.aiが8/14公開のGLM-5.3で、オープンウェイトの公開だけを安全性評価とハードニングのため約2週間先送りした。主要なオープンウェイト系ラボが自社モデルの攻撃的サイバー能力を理由に公開延期を明言した初の事例。CyberGym 84.5%・ExploitBench 54.4%を自己申告している。
  - https://www.axios.com/2026/08/14/china-open-source-ai-glm-53

## オープンウェイト / ローカル LLM

### DeepSeek がエージェントハーネス本体を MIT で公開した — [master]
- DeepSeekがエージェントハーネス本体をMITで公開し、8/17のrc.7でClaude CodeとCodexのサブエージェントを自前のJob Panelに取り込んだ。設計思想は「Everything is a Plugin」で、モデル・ツール・スキル・サンドボックスがいずれも差し替え可能なプラグインとして実装されている。「ハーネスは各社の囲い込み」という前提が外れる。
  - https://github.com/deepseek-ai/deepseek-harness

### DeepSeek の新料金が発効し キャッシュヒット入力が最大12倍になった — [industry]
- DeepSeekの新単価が日本時間8/17 1:00に発効した。倍率が最大なのは出力ではなくV4-Proのキャッシュヒット入力で、ピーク帯（UTC 01-04時・06-10時、日本のオフィス時間とほぼ重なる）は12倍になる。キャッシュ活用を前提に安さを見積もっていた試算ほど大きく狂う。
  - https://qz.com/deepseek-api-price-increase-v4-peak-off-peak-081326

## MCP（Model Context Protocol）

- MCPのリードメンテナ2名が8/22、7/28の仕様リリース以来25日ぶりに公式ロードマップを公開した。優先領域はサーバー起点イベントによるポーリング脱却、HTTPネイティブtransportの統一、エージェントIDとエンタープライズ向けセキュリティ（DPoP・Workload Identity Federation）、ツール呼び出し結果の標準化、SDK開発体験投資の5本。
  - https://blog.modelcontextprotocol.io/posts/mcp-roadmap/

## 企業動向・資金調達・市場データ

### Stripe が OpenRouter を $7B 超で買収した — [industry]
- Stripeが8/16、400超のモデルを中継するOpenRouterを$7B超で買収することで合意した。5月の$113M調達時（評価額$1.3B）から3カ月で5倍超にあたる。決済事業者がモデルルーティング層そのものを取りに来た形で、Stripeにとって直近18カ月で最高額の買収になる。
  - https://www.bloomberg.com/news/articles/2026-08-16/stripe-nears-deal-to-buy-ai-firm-openrouter-for-over-7-billion

### Nvidia が OpenAI のオハイオ DC 向けに最大 $105B の融資を保証した — [industry]
- Nvidiaが8/17、OpenAIが賃借予定のオハイオ州データセンター群を支えるため最大$105Bの資金支援に合意した。初期4.25GWの計算容量が対象で、稼働は2028年に段階的に立ち上がる見込み。⚠️ 2025年9月に公表された「Nvidiaが$100B出資」提携は当初の形では実現しておらず、本件はその組み替えにあたる。出資と融資保証は別物である。
  - https://www.cnbc.com/2026/08/17/nvidia-financing-open-ai-data-center-ohio.html

### Groq が評価額半減で $350M を調達した — [industry]
- Groqが8/17、Series Aとして$350Mを調達し評価額$3.5Bとなった。昨年9月のピーク$6.9Bから半減した水準。事業はAIチップの自社設計からGPU/AIインフラを提供するneocloudへ軸を移している。
  - https://techcrunch.com/2026/08/17/groq-raises-350m-to-fuel-its-pivot-from-ai-chips-to-neocloud/

## 来週の注目予定

- 8/24: ChatGPT Adsが欧州31市場で開始／Anthropic・OpenAIが下院民主党の監督書簡へ回答する期限
- 8/26: OpenAI Assistants API廃止／o3退役／GPT-4.5完全廃止／GitHub Copilot既定モデル有効化ポリシー発効／Ask Gemini in Chatのロールアウト開始
- 8/30: 公式DALL·E GPTの退役
- 8/31: Claude Codeの週次上限50%増が終了／GitHub Sparkの既存ユーザーアクセス終了／`gemini-robotics-er-1.6-preview`停止／GPT-5.4・5.4 miniがCodexから除外／Power Automateモバイルアプリの廃止／Copilot Studio566997（メーカー資格情報ブロック）のGA期日
- 8月末: Anthropicが IPOを公開申請する可能性
- 9/1: GitHub Copilot全体験でモデル廃止／OpenAI Daybreak全アカウントでハードウェアセキュリティキー必須化／MAICPP契約更新条項の自動発効
- 9/10: MAI-Code-1-Flashが全Copilot体験から廃止
- 9/17: OpenAI DevDay Exchangeの応募締切
- 9月: Copilot Tuningの新体験がPublic Preview／Copilot StudioのDataverse・Azure SQLナレッジソースGA／簡素化Copilot体験のOutlook・Teams展開／Self-serve sync connectorsのGA／Copilotメモリの保持機能GA／Federated Copilot Connectorsの政府クラウドGA
- 10/1: Apple のEU向け新ビジネス条件が発効
- 10/16〜11/11: OpenAI DevDay Exchange 8都市（東京は10/20）
- 10月: Anthropic のIPO予定（$2T超の評価額を目標と報道）
- 11/21: GPT-5.6 Solの暫定値下げが有効とされる期限（少なくともこの日まで）
- 12/2: EU AI Actの生成コンテンツ標識義務、猶予終了
- 12/31: Gemini 3.7 Flashの導入価格終了（→倍額）

## 改善メモ

- 3リポとも一次未達（ゲートウェイ拒否・オリジン403）が週内解消しなかった。masterは`www.anthropic.com`のオリジン403、industryは`api-docs.deepseek.com`の拒否が継続し、DeepSeekの新単価は課金区分別の確定値を一次で取れないまま週を終えた
- copilotリポで、GA済み機能が一次ページに反映されないまま残る事例が悪化した。Copilot StudioのWhat's NewはGitHub Copilotハーネスの GA（8/3）を週末時点で20日連続「(Production-ready preview)」のまま表記し、July 2026節の新設という編集機会があっても直らなかった
- 3リポともAnthropicの同一リリースノートページからの取りこぼしが再発した。8/19のClaude API GA（Computer Use・Browser Use・Files API・Agent Skills）は同一URLから3日連続で毎回別項目が抜け落ち、8/20のPython SDK v1.0も4日連続で同型の取りこぼしが起きた
- masterはMeta（Muse Code）とManus分離の一次3ホストにいずれも到達できず、複数の二次報道の一致で数値を採るケースが続いた。industryはGhostApproval（7/8公開・42日遅れ）とAWS $1B FDE組織（6/30発表・53日遅れ）で取りこぼしの最長記録を更新した
