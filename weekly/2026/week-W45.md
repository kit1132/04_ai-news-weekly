# AI ニュース週次サマリー — 2026-W45（2026-11-02 〜 2026-11-08）

> 生成日時: 2026-11-09（JST）

## 今週のハイライト

### 1. Claude Code が 2.1.317〜2.1.319 まで進み、ゲートウェイ・管理設定・通信の前提が動いた — ゲートウェイ越しの無人実行と `deniedMcpServers` は 2.1.319 の挙動で引き直す

**要点**: Anthropicが2.1.319で、テレメトリを切った環境とLLMゲートウェイ経由の環境の auto mode を、サーバー側チェックが届かないとき確認か拒否に回すようにした。これまで素通りした操作が止まり、`claude -p` は終了コード1で終わる。

**詳細**: 3リリースで挙動が3つ変わった。npmは11/6時点で`{stable: 2.1.311, latest: 2.1.319}`。

- 2.1.317（11/3）: セッション内の`claude -p`が親の ID・transcript を共有しなくなった。戻すには`CLAUDE_CODE_DISABLE_NESTED_SESSION_ID=1`。gatewayに費用レポート`GET /v1/organizations/analytics/cost`が加わった
- 2.1.318（11/3）: `deniedMcpServers`のURL指定が Anthropic 提供コネクタとクラウド / self-hosted runner のコネクタも止める。IDEのターミナルから起動しても拡張を入れなくなった
- 2.1.319（11/6）: gateway経由のauto modeを旧挙動に戻すには`CLAUDE_CODE_AUTO_MODE_SERVER=0`。`permissions.denyInsteadOfPrompting`が加わった。worktree作成時のサンドボックス脱出など3件のセキュリティ修正が入った
- 2.1.317より前: web / shell ツールがアカウントのメールアドレスを User-Agent で外部サイトへ送っていた（7/17に最初の報告。確認を求めるのは2.1.317から）

- https://code.claude.com/docs/en/changelog
- https://raw.githubusercontent.com/anthropics/claude-code/main/CHANGELOG.md
- https://gigazine.net/news/20261106-claude-code-mail-address/

### 2. 改ざん版 Claude Code 拡張は 2.1.312・2.1.313 と判明 — アンインストールだけでは SSH 鍵と自動起動が残る

**要点**: 10/29にCursorのマーケットプレイスで配布された改ざん版の拡張は2.1.312と2.1.313（macOS・Windows）だった。攻撃者のSSH鍵と自動起動を書き込むため、拡張を消しても侵入口が残る。「消せば済む」前提は成り立たない。

**詳細**: 公開時間は10/29 2:27〜13:35 PT。影響人数はどの一次にも無い。Anthropicは公式経路の配布物は無事としている。

- 確認: `~/.ssh/authorized_keys`に`svc-telemetry`の鍵があるか（Windowsは`administrators_authorized_keys`も）
- 除去: 不正な鍵、`~/.config/.smt`・`.smtk`、LaunchAgent`com.apple.sysmond.plist`（macOS）または`SysMon`タスク（Windows）を消し、`ssh -R` / `autossh`のトンネルを止める
- その後: 該当端末から使えた認証情報を別端末から更新する。Cursorは端末の再構築も勧めている

- https://cursor.com/blog/claude-code-extension-security-notice
- https://phorion.io/blog/offical-claude-code-vsx-compromise/
- https://gigazine.net/news/20261102-official-claude-code-extension-compromise/

### 3. Copilot / Power Platform の期限が11月〜12月に集中した — Power Automate・Word・プロンプトのモデルと、UBB の時期を引き直す

**要点**: 11/30にPower Automateデザイナーの Copilot と Describe it to design it が止まる。12/2にPower Platformのプロンプトから Claude・Grok が外れる。一方、Copilot Business の従量課金の既定オンは2027年1〜3月へ延び、12/1の前提が消えた。

**詳細**: 退役は自動移行か機能停止で、既存のフローは消えない。

- 11/30: Power Automateデザイナーの Copilot（MC1540258）と Describe it to design it（MC1537406）。作成の入口は外部AIアシスタントのプラグインか Copilot Studio MCP に移る。EU / EFTAでデータ移動オフの環境の GPT-5 Chat も終わり、延長できない
- 12/2: Claude Sonnet 4.6・Opus 4.6・Grok 4.1 Fast が退役し、同じ段（Basic / Standard / Premium）の GPT 系へ自動移行する（MC1536101）
- 延期: Copilot Business の既定オンは12/1 → FY27 Q3（2回目の延期）。UBBモデル（GPT-6 Astra / Claude Fable 5.1）の GA は12月上旬に、外部メールを Copilot から外す Purview DLP の GA は2027年6月に延びた

- https://mc.merill.net/message/MC1536101
- https://mc.merill.net/message/MC1506318

### 4. Claude Enterprise に IP 許可リストが入り、Copilot では管理センターの統制に抜けが出た — 社外網の利用と Cowork コネクタの統制を引き直す

**要点**: Anthropicが11/5、IP許可リストをConsole / Admin APIで管理者が自分で設定できるようにした（beta）。Enterpriseで有効にするとClaude Codeも社外網から使えない。一方、Copilot CoworkのPower PlatformコネクタにはPPACのDLPが効かない。

**詳細**: Claude側はInference hooks（DLP連携）がGA、セキュリティセンターと親組織の一括管理がbeta。

- IP許可リスト: IPv4 / IPv6とCIDRを組織あたり1,000件まで。強制サインアウトAPIはAPIキー・実行中のクラウドセッション・routineを止めない
- Cowork: Power Platformコネクタの可否はM365管理センターの Agents > Tools で決まる。PPACのDLPポリシーは適用されない（MC1542062）
- 同日にOpal（Frontier）が11/9から従量課金と支出ポリシーを前提にする（MC1540330）

- https://claude.com/resources/articles/claude-enterprise-security-updates

## Claude Code / Claude Developer Platform

### Messages API の message threads（beta） — [master]
- 長い会話をサーバー側に保持し、新しいメッセージだけを送れるようになった（beta ヘッダ`message-threads-2026-08-12`）。スレッドは最後のリクエストから5分で失効する
- 50万〜100万トークンのリクエストで TTFT の中央値が約35%下がったとAnthropicは説明している。課金とトークン量は減らず、ZDRの対象外

### Claude の透かし範囲の拡大 — [industry]
- 11/16から Opus 4.6・Opus 4.5・Sonnet 4.5・Haiku 4.5 の出力にも透かしが入る。4モデルとも`temperature`・`top_p`・`top_k`が既定値のときだけ付く
- 11/3の第1弾は Mythos 5・Opus 4.7（設定にかかわらず付く）と Sonnet 4.6。理由は12月のEU AI Actの期限

## GitHub Copilot / Cursor / 開発ツール

### Copilot CLI v1.0.107 — [master]
- `alwaysApply: false`のプラグインルールが、`/instructions`で有効にするまで掛からなくなった
- `/code`と統合ダッシュボード`/settings`が加わり、GPT-6.1 Terraを選べる。レビュー依頼だけでAutopilotが実装を始める問題も直った

### Copilot code review の API 管理・承認・Max — [master][industry]
- 11/6にenterprise・organization・repositoryの設定をREST / GraphQL APIで管理できるようになった。enterprise / organization のエンドポイントはGitHub Appsとfine-grained PATに非対応
- 10/28発表のPR承認機能（GA）は、有効にするとCopilotの承認が必須承認数に数えられる。既定はオフ。最上位のMaxレビューはパブリックプレビュー
- Balanced effortは3モデルの指摘を別モデルがまとめる形になった

### GitHub の連携拡大 — [master][industry]
- Copilotが JetBrains Air のエージェント選択に加わった（11/3・ACP）。個人 / 組織プランのどちらで課金されるかは選べない
- Slack と Teams の`@GitHub`が一般提供になった（11/6）

### `pull_request_target` の既定ブロックが延期 — [industry]
- 公開リポジトリでの既定ブロックは11/2から12/2へ延びた。その前の11/9と11/16の16:00〜18:00 UTCに試験ブロックが入る
- 対象は公開リポジトリ（Free・Team・Enterprise Cloud）。ブロックされた実行は失敗する

### Cursor — [master]
- Live Apps（11/5）: クラウドエージェントがアプリを作り、DB・Cursor SSO・ホスティングまで用意する。公開前にセキュリティ検査を通る。全有料プランが対象
- Voice Chat（11/6）: エージェントと声で作業を進められる。音声処理はGrok Voiceで、Privacy Modeではゼロデータ保持

### Conductor — [industry]
- Metaが買収し、クラウド版は11/20に終了する。デスクトップ版は2027年初め以降に新モデルが追加されない

## OpenAI / モデル / 市場

### GPT-6-Cyber — [master][industry]
- 11/5にAPIで提供された。Preparednessはサイバー Critical。入力$20 / 出力$100（100万トークン）で、Daybreak Redで承認された組織に限る
- `gpt-5.5-cyber-preview`は2027-02-01にAPIから削除される。移行先は「利用できる最も能力の高いサイバー用モデル」とだけ書かれている

### ChatGPT と Codex の利用枠 — [industry]
- 12月からPlus・Pro・Businessで1つのトークン予算を共有する（The Decoder 11/1）。開始日とプラン別予算額は未公表。一次の本文は未確認

### Kimi K3.1 Pro — [master]
- 重みがHugging Faceで公開された（総2.8T / 活性104BのMoE・100万トークン文脈）。約束期限の11/4を守った
- 独自ライセンスで、第三者向け推論・FT事業の売上が年$20M超なら別契約が要る

### 市場データ — [industry]
- Menlo Ventures（Anthropicの出資者）の推計で、企業LLM API支出のシェアはAnthropic 55%・OpenAI 31%・Google 9%。一次未確認
- Synergy Research Q3 2026のクラウド市場は$168B（前年比55%増）。AWS 26%・Microsoft 19%・Google 16%。数値はPublickey経由のみ

## Microsoft 365 Copilot / Copilot Studio

### 利用制限・課金の変更 — [copilot]
- 11/9から、M365 Copilotライセンスのない Copilot Chat 利用者に上限のかかる機能が増える。管理者は上限を見ることも変えることもできない
- Teams の Intelligent call delegation は11/17から従量課金のパブリックプレビューに移る。支出ポリシーがないと止まる（MC1537490）

### 機能の撤去・移行 — [copilot]
- 単体のWord / Excel / PowerPointエージェントが11月中旬から撤去され、Copilot Chatに置き換わる（12月下旬完了・MC1536062）
- WordのTop of Doc要約が11月末までに廃止される。要約はCopilotウィンドウで頼む（MC1454113）

### 管理・開発 — [copilot]
- Copilot Studio MCPサーバーが出た。Claude Code・Codex・GitHub Copilotからエージェントを作成・テスト・公開できる。Work IQがGAになった
- M365管理センターにエージェント利用状況レポートが加わった。Copilot Searchの権威あるコンテンツはSharePointサイト100件まで指定できる
- 高度なパッケージ（MCP付き・アクション付きエージェント）のアップロードを、管理者が絞れるようになった。未設定のテナントは10/25から全ユーザーに許可されている
- Copilotの Claude モデルは2026年末までにEU Data Boundary内で処理される。EU / EFTAでは既定で無効

## 来週の注目予定

- **11/9**: `pull_request_target`の試験ブロック（16:00〜18:00 UTC）。Opal（Frontier）で従量課金と支出ポリシーが前提になる。Copilot Chatの上限拡大
- **11/10**: Claude Desktopの管理ポリシーの変更（`desktopHome`なしの`coworkTabEnabled` / `chatSessionRetentionDays`。中身は一次未確認）。BedrockでMythos 5 / Opus 4.7 / Sonnet 4.6の透かし展開が完了予定
- **11/12**: Anthropic Usage Policy改定版が発効。Copilot Studio・Copilotハーネスの GPT-5 Chat・GPT 5.6 Sol / Luna が退役
- **11/13**: ExcelとCoworkの会計機能がGA（MC1536053）
- **11/16**: Copilotから Claude Opus 4.8 / Opus 5 / GPT-5.6 Terra を廃止。透かしの第2弾。2回目の`pull_request_target`試験ブロック。旧GitHub Teamsアプリが退役
- **11/17〜20**: Microsoft Ignite。11/17にIntelligent call delegationが従量課金プレビューへ、Gemini Live / TTSのpreviewモデルが停止（二次のみ）
- **11/20**: Conductorクラウド版が終了

## 改善メモ

- 3リポとも新規提案・障害の変化なし。継続: B-036 DeepSeek登録（12回目）、B-040 セキュリティ開示の定点（15回）、B-080 Cowork の Learn URL 差し替え（13回目）、B-081 モデル表の題名（11回目）、B-088 Gemini API Changelog の URL 差し替え（5回目）
- 矛盾: Learnの`cowork-models`・`cowork-admin-governance`は「Anthropicの有効化はユーザー・グループ単位」と書くが、`cowork-access`は「テナント全体のみ」のまま（11/5改訂）
- 一次未確認: ChatGPT / Codex統合枠（`help.openai.com`が403）、Menlo Venturesの数値、SynergyのQ3発表、Gemini関連の停止日
- 11/10のClaude Desktop変更は、2.1.319の警告から存在だけが分かっており、中身は未公表
