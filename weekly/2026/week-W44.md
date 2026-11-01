# AI ニュース週次サマリー — 2026-W44（2026-10-26 〜 2026-11-01）

> 生成日時: 2026-11-02（JST）

## 今週のハイライト

### 1. Opus 4.8 の fast mode と Sonnet 4.5 が 11/30 に同時に止まる — fast mode を使う処理は Opus 5.5 への切替を先に済ませる

**要点**: Anthropicが10/30にOpus 4.8のfast modeを非推奨にし、11/30に削除する。削除後は`speed: "fast"`付きの要求がエラーになり、通常速度へも落ちない。これまで「モデルを選べばfast modeも使える」前提だった。

**詳細**: 同じ11/30に`claude-sonnet-4-5-20250929`もClaude APIから退役する。

- 廃止されるのは`claude-opus-4-8`のfast modeの組み合わせだけで、モデル自体はActiveのまま（暫定退役は2027-05-28以降）。モデル退役ページは未更新
- 移行先は`claude-opus-5-5`（fast mode対応）。告知から削除まで31日
- 同日に重なる期限: Gemini 4 Argonの導入価格が終わり（12/1に単価が$4/$20へ倍増）、OpenAIのEvals・`v1/prompts`・Agent Builderも停止する

- https://platform.claude.com/docs/en/release-notes/overview#october-30-2026
- https://code.claude.com/docs/en/changelog

### 2. Claude Code が1週間で2.1.311〜2.1.316 まで進み、通信先・権限・管理設定の前提が動いた — 閉じた環境と管理設定は 2.1.316 の挙動で引き直す

**要点**: 2.1.311でBedrock/Vertex/Foundry利用でも`downloads.claude.ai`へ通信するようになった。2.1.316ではTeam/Enterpriseのサーバー管理設定が承認プロンプトなしで適用される。これまで「クラウド経由なら外へ出ない」「管理設定は開発者が承認する」前提だった。

**詳細**: npmは11/1時点で`{stable: 2.1.309, latest: 2.1.316, next: 2.1.316}`。`2.1.313`は未publish、`2.1.315`はchangelogに項が無い。

- 2.1.311（10/26）: モデル設定を署名つきファイルで取得する。止めるには`CLAUDE_CODE_MODEL_CATALOG=off`。`DISABLE_COMPACT`は圧縮をオフにする方向にしか効かない
- 2.1.312（10/27）: クラウド経由の未知のモデル名に短いシステムプロンプトを使う。戻すには`CLAUDE_CODE_SIMPLE_SYSTEM_PROMPT=0`
- 2.1.314（10/30）: `permissions.blockWritesOutsideWorkingDirectories`で作業ディレクトリ外への書き込みを全モードで拒否できる。`FORCE_HYPERLINK=false`の意味が反転した
- 2.1.316（10/31）: サーバー管理設定を承認なしで適用する。gatewayに`pooled_budget`（グループ共有の月次予算）が入った

- https://code.claude.com/docs/en/changelog
- https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md

### 3. GitHub が Copilot の課金・承認・権限を同時に動かした — 「席数で買う」「承認は人が出す」「許可は毎回押す」前提を引き直す

**要点**: GitHub Enterprise CloudにCopilotが含まれ、課金は席数でなく初回要求からのEnterprise予算の従量になった。Copilotの承認が必須承認数に数えられ、コマンド許可もLLMが自動判定できる。

**詳細**: いずれも10/26〜10/28の発表。Enterprise契約は営業経由で、セルフサーブは「数週間以内」に日付を出す。

- Enterprise込み契約: 席ごとの月次AIクレジットは無い。ライセンスの無いユーザーはCopilot Standalone（$10/ユーザー/月）。Actionsの無料枠はドル建ての共有枠になり、cloud sandboxの課金は11月に始まる
- Copilot code reviewの承認（GA、既定オフ）: 有効にするとCopilotの承認が必須承認数に入る。新コミットのpushで取り消される。Max（public preview）も加わった
- Assisted permissions（10/26 GA）: 安全と判定したものだけ自動で通す。Enterprise管理者はAllow Allを禁じたままAssistedを許可できる
- Copilot Fusion（10/28 GA、全プラン）: タスクごとにモデルを振り分け、課金は使った各モデルの標準単価の合計

- https://github.blog/changelog/2026-10-28-github-enterprise-now-includes-access-to-github-copilot
- https://github.blog/changelog/2026-10-28-copilot-code-review-merge-with-confidence-with-max-and-approvals
- https://github.blog/changelog/2026-10-26-github-copilot-assisted-permissions-generally-available

### 4. OpenAI の価格が1週間で3方向から下がった — 中位モデルの試算と「ChatGPT 席と API は別払い」を引き直す

**要点**: GPT-6.1 Terraは入力$1・出力$5で、GPT-5.6 Terra（$2/$12）の半額以下になった。ChatGPT Pro/Businessの契約にはAPIクレジットが月最大$500付く。API定価は調達の基準にならなくなった。

**詳細**: GPT-6.1 Terraは10/26にAPIとCopilotで同日GA。Copilotでは11/16にGPT-5.6 Terraが廃止される。

- GPT-6.1 Terra: コンテキスト1.05M・最大出力128K。272K超は$2/$7.50。比較はGPT-6.1 Sol $2/$10、GPT-6 Luna $0.10/$0.50
- APIクレジット（10/28）: Proは月額と同額、Businessは席あたり$20/$100（ワークスペース上限$500/月）。繰り越せない
- Pro枠: 10/30に予定されたPro 200の削減は撤回され、Pro 100/500のWork・Codex枠は倍になった（The Decoder）
- 値引き: The Informationによると、大口顧客へ定価から30〜90%の値引きを出している

- https://developers.openai.com/api/docs/pricing
- https://community.openai.com/t/claim-up-to-500-in-api-credits-using-your-chatgpt-pro-or-business-subscription
- https://github.blog/changelog/2026-10-26-gpt-6-1-terra-in-github-copilot

### 5. 送ったデータの扱いが2か所で変わった — Gemini API の新規プロジェクトと OpenAI の Daybreak Blue は「残らない・学習に使わない」が前提でなくなった

**要点**: Gemini APIは10/26以降の有料新規プロジェクトで`store=true`が既定になった。OpenAIはDaybreak Blueのセッションデータを11/29から学習に使う。どちらも従来の設定のままでは外せない。

**詳細**: Daybreak Blueの件は二次報道（The Decoder 10/31）で、OpenAIの一次ページでは未確認。

- Gemini API: プロンプトと応答がAI Studioのログに既定で55日残る（7・14・28・55日から選べる）。既存プロジェクトは変わらない。学習利用の扱いはページに記載が無い
- Daybreak Blue: Trusted Accessの参加者へメールで通知された。「モデル改善」オフでも対象。反発を受けた2通目でオプトアウト手段を約束したが、手順は未公開

- https://ai.google.dev/gemini-api/docs/changelog
- https://the-decoder.com/openai-plans-to-train-models-on-daybreak-blue-cybersecurity-session-data-that-was-previously-off-limits/

## Anthropic / Claude

### Anthropic が S-1 を公開提出し Nasdaq「ANT」で上場を申請した — [industry]
- 売上は2026年上期$163億（Q2 $116億、2025年通期$46億）で、従量課金が約80%を占める。数値は二次報道による
- 上期の純損失は$807億で、約$724億は公正価値変動による非資金費用。Q2単独ではGAAP営業利益$9.74億と初めて黒字になった
- 価格帯・株数は未決定。上場は早ければ11月中旬と報じられている
- https://www.anthropic.com/news/s1-sec

### Usage and Cost Analytics API が beta で出た — [master]
- 10/29にトークン利用量とコストをモデル・ワークスペース・APIキー・利用者で集計できるAPIが出て、旧Usage and Cost APIとEnterprise Analytics APIの4エンドポイントはlegacyになった。旧APIは引き続き使える

### サブエージェントを1本のループへまとめる手引きと移行キットが出た — [industry]
- Anthropicが10/22に公開した。Opus 4.5以降のモデルでは単一ループのほうが速く品質も保てるとしている

### 利用ポリシーの改定版が 11/12 に発効する — [master][industry]
- 11/12発効。ほかに、claude.ai/designの単体サイトが12/14に閉鎖され、`claude-opus-4-5-20251101`の暫定退役日は11/24以降（確定日ではない）

## GitHub Copilot / Microsoft 365 / Power Platform

### Power Platform と Copilot Studio で退役が続いた — [copilot]
- Power Automateの「Describe it to design it」が11/30に退役し、新規フローの作成は組織承認のAIアシスタントのプラグインへ移る
- Power AppsのCopilotによるPower Fx式生成・コントロール名の一括変更が12/11、モデル駆動アプリの説明文のAI生成が11/30に退役する
- AI Builderクレジットは11/1以降の新規・更新ライセンスに付かず、実行費用はCopilot Creditsで賄う（MC1526652）
- Copilot Studioのコスト管理をM365管理センターのCost Managementへ環境ごとに移せるようになる（11/20まで、MC1530368）。移した環境はPPACに出なくなる

### Copilot のリリース管理とモデルが変わった — [copilot]
- Targeted releaseが2027年1月に退役し、11月には割り当てを変更できなくなる。早期検証はFrontierだけになる
- CoworkのモデルピッカーにGrok 4.7とGPT 6.1 Solが入った。GrokはxAIが独立プロセッサとして処理するため、選ぶとMicrosoftのDPAの外になる
- Copilot NotebooksがCopilot Workspacesへ移り、チームでOfficeファイルを共同編集する場になる。Frontierには10月に出た
- Power Platform Admin（preview）プラグインで、管理者がCoworkからテナントの統制状況を自然言語で問い合わせられる

### Copilot Studio と Teams の課金・ポリシー — [copilot]
- Teams会議のCopilotポリシーが11月中旬にMeetingAIとTranscriptionWithMeetingAIへ分かれ、PowerShellで旧ポリシーを書き換える運用は失敗する（MC1532253）
- Copilot Studioの課金レート表に推論モデルの計算例が載り、1メッセージで141〜461クレジットかかる例が示された
- Work IQ APIはライセンス割り当てなしで呼べる従量課金になり、管理者が作るカスタムMCPコネクタも出た
- GitHub Copilotハーネスは「Microsoft Copilotハーネス」に改名された。機能と課金は変わらない
- Copilot Studioの評価機能（タスク完了・ツール精度の採点器など）がGAし、作成者と閲覧者を分けるEvaluation Viewerロールが加わった

### Power Apps の作成エージェントがプレビューで入った — [copilot]
- キャンバスStudioの作成エージェントはメーカー本人のGitHubアカウントで動き、課金とGitHubの規約が適用される

## OpenAI / Google / その他

### Gemini Notebook が Gemini アプリの接続アプリとして既定オンで出た — [master]
- GeminiとGemini Notebookの両方を許可したOUでは、設定を変えなくてもチャットからノートブックとソースを作成・編集・削除できる。EEAは既定オフ

### Cursor のマーケットプレイスに Claude Code の偽拡張が約11時間載った — [industry]
- 10/29にClaude Codeを装った悪性拡張が公開され、最大5,000人に影響した可能性がある（The Decoder）。ホスト名・ユーザー名・OS・グローバルIPの収集を試みた
- Cursorは拡張を削除し、マーケットプレイスを一時停止した。Anthropicは開発に関与していない

### Orca（Stably AI）が v1.4.240〜v1.4.245 まで毎日更新された — [master]
- v1.4.242でClaudeフォルダの`keybindings.json`に自前のショートカットを書き込むようになった（Settings → Agentsでオフ可）
- v1.4.245でプラグインが既定で有効になり、承認したプラグインはコンピューター全体にアクセスできる。Macのcomputer useは既定でバックグラウンド実行になった

## 来週の注目予定

- 11/2: xAI `grok-imagine-image-quality`が退役。Meetの63言語音声翻訳がScheduled Releaseへ展開開始
- 11/4: Entraで一般ユーザーのブループリント作成が既定オンになる（MC1506733）。Kimi K3.1 Proの重み公開の約束期限（二次）
- 11/5ごろ: Anthropicのゲスト研究者（生命科学）の応募受付が終了
- 11/9: Dataverseのみのテナントでストレージ検証が始まる（MC1483529）
- 11/12: Anthropic Usage Policy改定版が発効。Copilot StudioのGPT-4.1/GPT-5系が退役（MC1506318）
- 11/15: Dataverse for Teams環境の新規作成が止まる。Copilot Studioのカスタム採点器ライブラリがGA
- 11/16: CopilotからClaude Opus 4.8・Opus 5・GPT-5.6 Terraを廃止。Teamsの旧GitHubアプリが退役
- 11/17: Gemini APIのTTS・Liveプレビュー5種が停止（最短日）。Gemini内のGemsが設定パネルへ移動
- 11/17〜20: Microsoft Ignite
- 11/20: Copilot Studioのコスト管理をM365管理センターへ移す機能がGA
- 11/24以降: `claude-opus-4-5-20251101`の暫定退役日
- 11/29: OpenAIがDaybreak Blueのセッションデータを学習に使い始める
- 11/30: Opus 4.8のfast modeと`claude-sonnet-4-5-20250929`が停止。Power Automateの「Describe it to design it」が退役
- 12/1: Copilotの前提サブスク不要オファーが始まる。Gemini 4 Argonの単価が倍増
- 12/11: Power Appsの式生成などCopilot機能が退役
- 2027-01-14: OpenAIのGPT-4o・GPT-4o mini・GPT-4.1・GPT-4.1 miniが削除（移行先は`gpt-6-luna`）

## 改善メモ

- 3リポとも新規の障害・提案の変化は無い（継続分は各リポのIMPROVEMENT-BACKLOG.md参照）
- [copilot] 継続提案2件: B-080（CoworkのLearn URL差し替え、6回目）、B-081（Learnが本日も旧ハーネス名のまま、4回目）
- [industry] B-047: TLDR AIの週次スイープを`tldr.tech/ai/YYYY-MM-DD`のcurl取得へ切り替える。継続提案5件（最多B-040、13回）。`www.indiatoday.in`がゲートウェイ拒否（新規）
- [master] 見送り候補: B-036/B-037/B-043/B-078
- 週次側: 二次報道（S-1の財務値、Daybreak Blueの学習利用）は一次未確認のまま転記した
