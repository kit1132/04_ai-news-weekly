# AI ニュース週次サマリー — 2026-W33（2026-08-10 〜 2026-08-16）

> 生成日時: 2026-08-17（JST）

## 今週のハイライト

### 1. Sonnet 5 の $2/$10 が恒久価格になった — 9/1 の値上げ前提が消えた

**要点**: Anthropicが Sonnet 5 の導入価格 $2/$10 を恒久化し、9/1 予定だった $3/$15 への値上げを撤回した。値上げを織り込んだ費用試算は据え置き前提へ引き直しになる。

**詳細**: 8/10付でAPI公式pricingページに注記が入り、「launch時の導入価格が標準価格になった」と明記された。Batch API（50%割引）・プロンプトキャッシュの単価は従来どおり。比較対象のSonnet 4.6/4.5は$3/$15のまま据え置かれているため、Sonnet 5が旧世代より安い状態が恒久化した。本サマリーは前週分まで「8/31終了→$3/$15」を注目予定に記載してきたが、この期限は消滅した。

- https://platform.claude.com/docs/en/about-claude/pricing
- https://platform.claude.com/docs/en/release-notes/api

### 2. Claude Code の承認が分類器任せになった — 8/14 に Pro/Max/Team の既定へ

**要点**: 8/14からPro/Max/Team版Claude Codeの新規セッションでauto modeが既定になった。危険コマンドの検出率は人手13.6%に対し分類器89%という実測が根拠で、都度承認前提が崩れる。

**詳細**: 根拠は1,053人の対照試験。管理はmanaged settingsの`defaultMode`/`disableAutoMode`、分類器細目は`autoMode`の`allow`/`soft_deny`/`hard_deny`で設定する。切替前後にv2.1.229〜v2.1.233が連続リリースされ、危険フラグ付きgit/ghコマンドの自動承認停止や、v2.1.232での`/fork`の意味変更（サブエージェント起動→セッション複製、旧動作は`/subtask`に改名）が入った。

- https://code.claude.com/docs/en/changelog
- https://code.claude.com/docs/en/permission-modes
- https://claude.com/blog/auto-mode-default-in-claude-code

### 3. DeepSeek API が最大11倍値上げ — 8/16 発効、日本の業務時間はピーク帯

**要点**: DeepSeekがV4-Flash/V4-Proの料金をピーク帯で最大11倍に引き上げ、8/16 16:00 UTC（JST 8/17 1:00）に発効した。「桁違いに安い」という前提のコスト比較は今日から引き直しになる。

**詳細**: ピーク帯はUTC 01-04時と06-10時（JST 10-13時・15-19時）で日本の業務時間とほぼ重なる。V4-Pro出力は$0.87→ピーク$3.96/オフピーク$1.98、V4-Flash出力は$0.28→ピーク$1.32/オフピーク$0.66。同じ8/13にV4-Pro-0813の重みがMITで公開されており、値上げの受け皿としてセルフホストが位置づけられているとみられる。一次料金ページはゲートウェイ拒否のため、数値は二次報道の一致による。

- https://qz.com/deepseek-api-price-increase-v4-peak-off-peak-081326
- https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro-0813

### 4. Agent Plugins 1.0 が Copilot 全面で GA — 拡張の配布単位がベンダー横断で1つに

**要点**: GitHubが8/12にAgent Plugins 1.0をCopilot全面でGAし、Business/Enterprise管理者はmanaged-settings.jsonで一括統制できるようになった。クライアントごとの書き分けが不要になる。

**詳細**: 仕様自体は8/6公開のベンダー中立標準で、Core MaintainerはAmazon・Anysphere(Cursor)・Microsoft・OpenAI・Vercel+Googleの6社。プラグインはplugin.json・skills/・mcp.jsonを持つディレクトリで、管理者は`enabledPlugins`/`extraKnownMarketplaces`/`strictKnownMarketplaces`を設定できる。Anthropicはコア開発にもローンチクライアントにも入らず、Claude Codeは独自の`command`ソースを追加する路線を継続。v1.0.0では権限モデル・サンドボックス・署名検証・シークレット機構がすべてfuture workのままである。

- https://github.blog/changelog/2026-08-12-agent-plugins-1-0-in-vs-code-copilot-cli-and-the-copilot-app/
- https://developers.googleblog.com/agent-plugins-package-your-skills-tools-and-more/

### 5. Power Automate の Release Wave に緑チェックが4件付いた — 「未リリース」の前提が崩れた

**要点**: Power Automateの計画機能4件（Python実行・PowerPoint操作・ローカルAIモデル接続・CSVエクスポート）が実は7月以前にリリース済みだったと判明した。Blogに告知はなく、緑チェックだけが一次シグナルだった。

**詳細**: 8/14にRelease Waveページが6日ぶりに更新された（`ms.date` 8/4→8/11）。緑チェックが付いた4件のリリース日はいずれも7月以前で、Power Automate Blogにも月次記事にも告知はない。期日超過は延べ12行から6行へ半減し、8月期日は7件から10件に増えた。緑チェックの照合を怠ると、実際は使える機能を「未リリース」として提案から外しかねない。

- https://learn.microsoft.com/en-us/power-platform/release-plan/2026wave1/power-automate/planned-features
- https://learn.microsoft.com/en-us/power-platform/release-plan/2026wave1/power-apps/planned-features

---

## Claude Code / Anthropic

### Fable 5 の生物学セーフガードが緩和され fallback が約85%減った — [master]
- Anthropicが8/7、Fable 5の生物学関連fallback（分類器が下位モデルへ問い合わせを回す仕組み）を約85%削減した。Claude.aiは総fallbackが67%減、Coworkは55%減、Claude Codeは17%減にとどまる。virology・toxicology・molecular designの3分野は引き続きOpus 5へ回る。
  - https://www.unite.ai/anthropic-retunes-fable-5s-biology-safeguards-cutting-blocked-queries-85/

### Claude の生成物に不可視ウォーターマークが入るようになった — [master][industry]
- Anthropicが、EU AI Act第50条への対応としてClaudeの生成テキストへ機械可読の透かしを埋め込み、画像ファイルにC2PA署名を付ける運用を8/11に公表した。対象はAPI・Claude Code・Coworkを含む全プロダクトで全世界が適用範囲、オプトアウトの記載はない。2026年8月2日以降にローンチしたモデルはlaunch時点で対応済みで、それ以前のモデルは対応作業中。検出は「Claudeが処理した可能性」を示すのみで著者性は保証しない。
  - https://support.claude.com/en/articles/16266773-how-claude-marks-ai-generated-content

### Compliance API が Cowork / Claude Code のローカルセッションまで取得できるようになった — [master][industry]
- Anthropicが8/11、Enterprise向けCompliance APIの対象を拡張し、端末で動くCoworkとClaude Codeのセッション文字起こしを取得できるようにした（beta）。取得できる中身はプロンプト・応答・ツール呼び出し・skillsとartifactsの内容で、除外されるのはClaude Code on the web・Claude Platform経由・Bedrock/Vertex/Foundry上のセッションの3系統のみである。
  - https://claude.com/blog/compliance-api-cowork-and-claude-code

### Claude Tag がチャンネル全体の文脈で発言可否を判断するようになった — [master][industry]
- AnthropicがSlack連携のClaude Tagを8/13に更新し、メッセージ単位の軽量分類器からチャンネルの文脈・メモリ・ユーザー指示を使う判定へ切り替えた。自社計測で発言すべきかの判定精度が約30%改善したとしている。対象はTeams/Enterpriseで追加費用はなく、広げた文脈は使用量上限にも算入しない。Anthropic自身もSlackでのアドホックなデータ分析にClaude Tagを使う事例を公開し、あるチャンネルでは明示的なメンションなしに75%超の質問へ回答したとしている。
  - https://claude.com/blog/claude-tag-now-reads-even-more-of-the-room

### Claude in Chrome のサイドパネルが Cowork のセッションへ統合された — [master][industry]
- Anthropicが8/12、Chrome拡張のサイドパネルをCoworkのセッションへ統合した。従来は孤立していたサイドパネルの会話がアカウントに履歴として残り、ブラウザで始めた作業をデスクトップ・Web・モバイルの各アプリで続けられるようになった。提供はMax/Teamが即日、Proは数週間かけて展開し、Enterpriseは既定オフで管理者がドメイン制限つきで有効化する。Chrome専用で他のChromium系ブラウザとモバイルには未対応。
  - https://claude.com/blog/cowork-chrome-side-panel

### JetBrains の自社評価で Fable 5 が Opus 4.8 を16ポイント上回った — [master][industry]
- JetBrainsが8/13付で公開した評価事例によると、非公開の自社モノレポで測ったPython合格率はFable 5が44.3%、Opus 4.8が28.2%だった。直接比較ではFable 5がOpusの落としたタスク18件を解決し、逆に落としたのは2件のみ。解に到達する手数もOpus比で約22%少ない。用途は複雑なコーディング、IDEコンポーネント実装、自社製品への脆弱性テストなど。
  - https://claude.com/blog/how-jetbrains-evaluates-and-deploys-claude-fable-5

### Anthropic がセッション費用の倍率を公式ガイドで公開した — [master]
- Anthropicが8/14、Claude Codeのセッション効率化ガイドを公開した。出力トークンは入力の約5倍のコスト、キャッシュ読み出しは通常入力の0.1倍で、プロンプトキャッシュの有効期限はサブスクリプションが1時間・APIキー利用が5分と明記された。推奨運用はタスクの切れ目で`/clear`を打つ、モデルとeffortを開始時に固定する、ファイルは`@`メンションで添付する、休憩前に`/compact`する、の4点である。
  - https://claude.com/blog/maximizing-the-value-of-your-claude-code-sessions

### Claude Code の npm stable タグが latest から9版遅れている — [master]
- Claude Codeのnpm `dist-tags`を実測すると、8/16時点で`stable: 2.1.224`・`latest: 2.1.233`・`next: 2.1.233`だった。差分の9版にはauto modeの既定化、PowerShellとWindowsの権限バイパス修正3件、Windowsのパス検証バイパス修正が含まれる。changelogとGitHub releasesだけを見ていると、stableチャンネルに固定した組織へ修正が届いているかどうかは分からない。
  - https://registry.npmjs.org/@anthropic-ai/claude-code

## GitHub Copilot / Microsoft 365 / Power Platform

### MAI-Code-1-Flash が9/10に全Copilot体験から廃止される — [master][copilot][industry]
- GitHubが8/11、Microsoft製の小型コーディングモデルMAI-Code-1-Flashを9月10日付で全Copilot体験から廃止すると告知した。後継のMAI-Code-1.1-Flashは画像理解が加わり、定価は前世代比73%減で年額契約者には0.25倍のpremium request倍率が適用される。Business/Enterpriseは既定オフで、管理者がモデルポリシーを有効化するまで選択肢に出ない。
  - https://github.blog/changelog/2026-08-11-upcoming-deprecation-of-mai-code-1-flash/

### Copilot CLI に Agent Host Protocol が入り、セッションが端末からホストへ移った — [master]
- GitHubがCopilot CLIへAgent Host Protocol（AHP）を導入した（pre-release v1.0.80-0・8/13、安定版v1.0.80・8/14）。セッションがCLIプロセスからホスト常駐へ移り、複数端末が同じセッションにアタッチしてターンをライブで追えるようになった。`/ahp sessions|attach|new`でセッション操作、`/ahp start`/`stop`/`restart`でdaemon管理を行う。CLIを閉じると作業が終わる、という前提が外れた。
  - https://github.com/github/copilot-cli/releases/tag/v1.0.80-0

### Grok 4.6 と Gemini 3.7 Flash が Copilot に追加された — [master][copilot]
- GitHubがGrok 4.6（8/14）とGemini 3.7 Flash（8/13）を相次いでCopilotへ追加した。対象はいずれもPro/Pro+/Max/Business/Enterpriseで、VS Code・Copilot CLI・クラウドエージェント等から選べる。⚠️ **両モデルともBusiness/Enterpriseは既定オフ**で、管理者がそれぞれ個別にポリシーを有効化しないと選択肢に出ない。モデルが増えるたびに管理者の許可操作が要る形が続いている。
  - https://github.blog/changelog/2026-08-14-grok-4-6-is-now-available-in-github-copilot/

### Copilot Studio ガイダンスハブがモデル入れ替えを「移行案件」と位置づけた — [copilot]
- Copilot Studioガイダンスハブに8月節が新設され、AIモデルのライフサイクル管理を扱う記事3本が公開された（`updated_at` 8/11）。既定モデルを使うエージェントは既定更新のたびに計画の有無にかかわらず別モデルへ移るため、重要度・流量の高いエージェントは特定モデルを明示すべきとしている。退役モデルは「Continue using retired models」で30日間だけ延命できる。あわせて同日、Claude Sonnet 5がGitHub Copilotハーネス限定（標準ハーネスでは選択不可）だったことも判明した。
  - https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/plan-agent-model-lifecycle

### Agent 365 のレジストリが Bedrock / Gemini / Claude / Salesforce のエージェントも同期できるようになった — [copilot]
- Agent 365 Registry Syncが8/6公開の月次記事でGAし、管理者はAmazon Bedrock・Google Cloud Gemini・Anthropic Claude・Databricks Genie・Salesforce AgentforceのエージェントをAgent 365レジストリへ同期できるようになった。あわせてマルチテナントのエージェント管理がM365管理センターでPublic Previewに入り、複数テナントのエージェントを単一画面で棚卸し・統制できるようになった。
  - https://techcommunity.microsoft.com/blog/agent-365-blog/whats-new-in-agent-365-%E2%80%93-july-2026/4543654

### Copilot Credit の消費レート表が Learn 上で確認できた — [copilot]
- Copilot Studioの課金ドキュメントを一次確認したところ、生成AIツールの消費レートは10応答あたりbasic 1・standard 15・premium 100クレジットで、モデル階層の選択だけで消費が100倍変わることが分かった。推論モデルは操作のfeature rateに加えてtext and generative AI toolsが別途課金される二重課金になる。USD単価は依然としてLearn上になく、取得できないPDFにしかない状態が続く。
  - https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-messages-management

### M365 Copilot Release Notes に13日ぶりの新バッチが入った — [copilot]
- Microsoftが8/13、M365 CopilotのRelease Notesに8月分の新バッチ（対象7/28〜8/11・12項目）を公開した。SharePointのAuthoritative Sites（管理者指定サイトをCopilot Searchで優先表示）、WordでのAnthropicモデル選択、Outlookのチャット内コーチングなどが含まれる。Copilot CreditのダッシュボードがViva Insightsに追加され、直属5人以上のマネージャーもコスト消費を確認できるようになった。
  - https://learn.microsoft.com/en-us/copilot/microsoft-365/release-notes

### 業務用 Copilot の Web URL が8/18から copilot.cloud.microsoft へ移る — [copilot]
- Microsoftが8/14付でPartner Center8月アナウンスに追記し、業務用Copilotのweb URLを`m365.cloud.microsoft`から`copilot.cloud.microsoft`へ8/18から自動リダイレクトすると告知した。組織側で新URLをブロックしているとリダイレクトされないため、`*.cloud.microsoft`の許可リスト登録と接続性の事前確認が要る。デスクトップアプリは8/18に早期プレビュー、広範な展開は9月中旬から。
  - https://learn.microsoft.com/en-us/partner-center/announcements/2026-august

## OpenAI / Codex / ChatGPT

### OpenAI が拒否を減らした専用モデルを審査付きで防御側に配り始めた — [master][industry]
- OpenAIが8/10、サイバーセキュリティ向けDaybreakをBlueとRedの2層に分割した。Daybreak RedはGPT-5.6-Cyberへ到達できる唯一の経路で、社内評価では高度なセキュリティ要求の95%に応答する。Chrome のV8エンジンで未知の脆弱性2件を発見し`CVE-2026-15903`が割り当てられた実績がある。9/1からは全アカウントでハードウェアセキュリティキーが必須になる。3日前の8/7には未公開モデルAstraの開発を、cybersecurity能力がCriticalの可能性を理由に一部停止していた。8/11にはAmazon Bedrock（US Eastのみ）でも提供が始まった。
  - https://community.openai.com/c/announcements/6

### ChatGPT Business に月$125のPremiumシートが登場した — [industry]
- OpenAIが8/10、ChatGPT BusinessにPremiumシート（月$125・年契約$100）を追加した。標準シート（月$25）の5倍の利用量を持ち、5時間の利用上限を撤廃する。同一ワークスペース内で標準とPremiumを人ごとに混在させられる。先着10,000社に最大5席までのクレジット販促があり、受付は8/20まで。
  - https://openai.com/index/premium-seats-chatgpt-business/

### OpenAI が GPT-5.6 Sol を最大14倍速で動かす Ultrafast モードを一次確定した — [master]
- OpenAIのdevelopers changelogに8/13付でUltrafastモードが掲載され、限定プレビューであることが一次確定した。GPT-5.6 SolをStandardの最大14倍速・最大750 output tokens/secで動かす新サービス階層で、推論基盤はCerebrasのWafer-Scale Engine。⚠️ **課金レートは本日時点も未確定**。
  - https://developers.openai.com/api/docs/changelog

### ChatGPT の広告テストが日本を含む5カ国へ拡大した — [master][industry]
- OpenAIが8/11、ChatGPTの広告テストを英国・メキシコ・ブラジル・日本・韓国へ拡大した。表示対象はFree/Goのみで、Plus以上は広告なしのまま。日本では電通デジタル・博報堂DY ONE・サイバーエージェントが広告の調達・配信・運用を担う。⚠️ 国内報道では日本での広告開始は6月19日からとする記述もあり、時期の記載が割れている。
  - https://help.openai.com/en/articles/20001410-sign-in-with-chatgpt

### ChatGPT が Mac の操作履歴を記憶に変える Computer History を出した — [master]
- OpenAIがmacOS版ChatGPTにComputer History（公開8/13・対象Pro/Business/Enterprise）を追加した。承認したアプリとサイトの操作イベント（クリック・タイピング・アプリ切替）が検索可能な記憶に変換され、ChatGPTとCodexが参照する。スクリーンショットではなくイベントログで、生成された記憶はローカルに平文Markdownとして残る。OpenAI自身がプロンプトインジェクションのリスク上昇を警告している。EEA・スイス・英国は提供対象外。
  - https://9to5mac.com/2026/08/13/chatgpt-for-mac-adds-opt-in-computer-history-feature-replacing-chronicle/

### ChatGPT Enterprise/Edu の個人同期接続が8/14に無効化された — [industry]
- OpenAIが8/14、ChatGPT Enterprise/Eduの個人が認可した同期コネクタを無効化し、同期済みデータの削除を始めた。管理者管理の同期（admin-managed sync）は影響を受けないが、対応を取らなかったワークスペースでは同期済みナレッジが失われる。Google Drive・SharePoint・GitHubいずれも管理者側での再設定が要る。
  - https://help.openai.com/en/articles/10128477-chatgpt-enterprise-edu-release-notes

## オープンウェイト / ローカルLLM

### Meta が30Bのエージェント特化モデル Muse Glimmer を Apache 2.0で公開した — [master][industry]
- Meta Superintelligence Labsが8/10、30Bのdense multimodalモデルをApache 2.0で公開した。4bit量子化で18〜20GBまで圧縮でき、24GB/32GB VRAMの単一GPUに収まる。SWE-Bench Verified 76.0%・SWE-Bench Pro 51.2%・AIME 2026 94.7%。当日中にunsloth・mlx-community等の量子化がそろい、ローカル実行の経路が初日から整った。
  - https://huggingface.co/meta-models/Muse-Glimmer-30B

### Qwen3.8-27B の重みが Apache 2.0で公開された — [master][industry]
- Alibabaが8/14、Qwen3.8-27Bの重みを公開した。SWE-bench Pro 61.7%・OSWorld-Verified 84.3%・Terminal-Bench 2.1 73.0%で、Muse Glimmer 30B（SWE-bench Pro 51.2%）を10ポイント超上回る。コンテキストは262,144トークンがネイティブで、RoPEスケーリングで100万まで拡張可能。同時にQwen3.8-Maxの重み（2.4Tパラメータ・アクティブ95B・独自ライセンス）も公開されており、8/8公開だった事実は本サマリー期間中の8/13にようやく一次確認できた。
  - https://huggingface.co/Qwen/Qwen3.8-27B

### Grok 4.6 が公開され Cursor で初日から使えるようになった — [master]
- xAIが8/12、Grok 4.6を公開した。Artificial Analysis Intelligence IndexでGPT-5.6 Solと同点、Claude Fable 5とは1点差。Cursorも同日提供を開始し、価格は入力$2/出力$6（Fastは$4/$12）。パラメータ規模は1.5Tで、SpaceXによるAnysphere買収後、xAIとCursorが共同リリースを名乗る形が初めて確認できた。
  - https://forum.cursor.com/t/grok-4-6-is-now-live/168189

## Cursor / xAI / Devin

### Cursor が Grok Bot を early beta で公開した — [master]
- SpaceXAIとCursorが8/11、永続的なクラウドコンピュータ上で動くエージェント製品Grok Botをearly beta公開した。ブラウザ・ファイルシステム・ターミナルを持ち、承認が要るときだけ人に戻る。⚠️ **コンピュータの分離単位はBotではなくアカウント**で、置いたログイン情報とファイルは全Botから見える。対象はSuperGrok Heavy/Cursor Ultra/Cursor Teams Premium。
  - https://cursor.com/blog

### Cursor が Cloud Agents に Builds を導入した — [master]
- Cursorが8/13、リポジトリ・ツール・依存関係を事前に焼いたスナップショットからエージェントを起動するBuildsを追加した。内部計測で環境の起動時間が10分の1、first tokenまでが3分の1になったとしている。設定が壊れても直前の成功Buildから起動し続けるため、デバッグ中に環境が使えなくなることがない。
  - https://cursor.com/changelog

## Google / Gemini

### Gemini 3.7 Flash が GA — 導入価格は12/31まで、以降倍額に — [master][industry]
- Googleが8/13、コーディングとエージェント向けのGemini 3.7 FlashをGA公開した。導入価格は入力$0.75/出力$3.75で2026年12月31日まで有効、以降は$1.50/$7.50へ倍増する。3.6 FlashのGA（7/21）からわずか3週間での交代にあたる。⚠️ Googleは同時に3.6 Flashも同一の導入価格へ静かに引き下げており、据え置きは3.5 Flash（$1.50/$9.00）のみとなった。
  - https://ai.google.dev/gemini-api/docs/pricing

### Made by Google 2026 で Pixel 11系と Tensor G6 が発表された — [master]
- Googleが8/12、Made by Google 2026でPixel 11系4機種・Pixel Watch 5を発表した。AI面は端末内処理が中心で、TPU性能50%増のTensor G6・オンデバイスのGemini Nano 4・複数手順タスクを自動実行するGemini Intelligenceが柱。クラウド側の新モデル発表はなかった。Gemini 3.5 ProのGAはI/O後6月→7月→7/17と3回スリップしたまま、依然未ローンチである。
  - https://blog.google

## 企業動向・資金調達・市場データ

### Anthropic がデータセンター専用共同事業体を相次いで組成した — [master][industry]
- AnthropicがMacquarie Asset Management・GICと専用データセンター事業体Theseus Infrastructureを設立（8/10）したのに続き、Bitcoinマイナー出身のRiot Platformsと20年・最大$16.1Bのデータセンター契約を結んだ（8/11・テキサス州Rockdaleの191MW）。いずれも自社バランスシート外での調達拡大にあたる。
  - https://www.datacenterdynamics.com/en/news/gic-and-macquarie-form-theseus-infrastructure-to-serve-anthropics-data-center-needs/

### Anthropic の Decart AI 買収交渉と IPO 評価額の報道が相次いだ — [master]
- Anthropicがイスラエル拠点のDecart AIと約$6Bでの買収交渉に入ったと8/13に報じられた（Bloomberg・交渉継続中）。同日、10月IPOで$2T超の評価額を投資家へ示しているとの報道、Q2に初の四半期営業黒字$559M（売上$10.9B）を投資家へ示したとの報道も出た。いずれも報道ベースで公式発表ではない。
  - https://www.axios.com

### Cognition が $40B 評価額での調達交渉に入った — [industry]
- Devinを提供するCognitionが$40B評価額での調達交渉に入ったと8/11に報じられた。5月末の前回調達（プレマネー$25B）から3カ月足らずで50%超の切り上がりにあたる。年換算売上ランレートは$1B近くまで伸びている。
  - https://techcrunch.com/2026/08/12/ai-coding-startup-cognition-reportedly-already-in-talks-to-raise-at-40b-valuation/

### Rippling が AI トークン支出を公開し、費用の見方が人件費比率へ移った — [industry]
- Ripplingが8/7、AI Spend Consoleを投入した。同社のトークン支出はピーク時にR&D人件費予算の40%を占めていたが、対策後は約15%まで下がった一方、利用量そのものはほぼ維持されている。1人のエンジニアが月$50,000分のトークンを消費していた事例も明らかにした。
  - https://techcrunch.com/2026/08/07/after-rippling-blew-millions-on-ai-in-months-it-built-an-employee-roi-tool/

### NEC が「全員AI」の部門を新設し、経営分析の所要時間を7分の1にした — [industry]
- NECが8/1付で「コーポレートAI・Workforce部門」を新設したと8/10に発表した。AI部門長・AIボード・AIマネージャー・AI社員の4階層で構成し、社内業務要請に応じてAI社員を都度生成する。1カ月の社内検証で、経営分析・シミュレーション・リスク予測の所要時間が約7分の1に短縮された。
  - https://jpn.nec.com/press/202608/20260810_01.html

### JDLA が AI ガバナンスの第三者認証を開始した — [industry]
- 日本ディープラーニング協会が8/4、C認証（AI Governance Core Certification）の一般申請受付を開始した。法人単位で認証し有効期間は2年、最短約2カ月で取得できるとしている。認定コンサルティング企業はABEJA・Elith・Algomatic・キカガクなど6社が先行登録済み。
  - https://www.jdla.org/news/20260804001/

## 規制・政策

### 米エネルギー省がオープンウェイト・モデルの供給主体になった — [industry]
- 米DOEが8/7、政府後ろ盾では初のオープンウェイトAIプログラムGenesis Open Models Initiativeを始めた。第1弾Genesis-Science-1はArcee AIと共同構築し、材料科学・核融合等を対象領域とする。同時期のホワイトハウス自主評価枠組みは米国製オープンウェイトを能力にかかわらず対象外としており、政府の関与が審査側と供給側の二方向に分かれた形になる。応募締切は8/14。
  - https://www.energy.gov/undersecretaryforscience/articles/us-department-energy-launches-genesis-open-models-initiative

## MCP（Model Context Protocol）

- 公式ブログは7/28の`The 2026-07-28 Specification`以降、週末時点で19日連続新着がない。Tier 1 SDKも変化なし（TypeScript/Python 2.0.0・C# v2.0・Goはv2未発行）。⚠️ Agent Plugins 1.0はMCPを置き換えるものではなく、MCPサーバー構成（`mcp.json`）をskillsと一緒に梱包する層である。
  - https://blog.modelcontextprotocol.io/

## 来週の注目予定

- 8/17: Claude Console旧Workbench退役＋実験的プロンプトツールAPI廃止／Gemini APIのImagen 4.0系3本停止／Gemini in Classroomのモバイル開放
- 8/18: copilot.cloud.microsoftへのURL移行開始とデスクトップ早期プレビュー／PPCC 2026標準価格での登録期限／Copilot Studio Released Versions次回定例
- 8/19: Claude Code週次利用上限50%増の終了（23:59 PT）
- 8/20: Pixel 11系の出荷開始／Gemini Enterprise Agent PlatformのGrok 4.1ファミリー停止（一次未確認）
- 8/22: M365 CopilotアプリのUI変更がDeferredリングへ展開開始
- 8/25前後: M365 Copilot Release Notesの次バッチ見込み
- 8/26: OpenAI Assistants API廃止／o3退役／GitHub Copilot既定モデル有効化ポリシー発効
- 8/30: 公式DALL·E GPT退役
- 8/31: GitHub Spark既存ユーザーアクセス終了／GPT-5.4・5.4 miniがCodexから除外／Claude for Governmentの$1/機関プログラム終了／Power Automateモバイルアプリ廃止
- 9/1: GitHub Copilot全体験でモデル廃止（MAI-Code-1-Flash除く）／OpenAI Daybreak全アカウントでハードウェアキー必須化
- 9/10: MAI-Code-1-Flashが全Copilot体験から廃止
- 9月中旬: Copilotデスクトップアプリの広範な展開開始
- 10月: Anthropic IPO予定（$2T超の評価額を目標と報道）
- 10/27〜29: Power Platform Community Conference 2026（ラスベガス）
- 12/2: EU AI Actの生成コンテンツ標識義務、猶予終了
- 12/31: Gemini 3.6/3.7 Flashの導入価格終了（→倍額）

## 改善メモ

- 3リポとも週内を通じて一次未達（ゲートウェイ拒否・オリジン403）が継続している。masterは`www.anthropic.com`のオリジン403が週内解消せず、industryは`api-docs.deepseek.com`・`docs.aws.amazon.com`等の一次未達により料金・仕様の変更を二次報道の一致でしか確認できていない
- copilotリポで、既に公開・GA済みの機能が一次ページに反映されないまま残る事例が継続した。Copilot StudioのWhat's NewはGitHub Copilotハーネスの GA（8/3）を13日連続で `(Production-ready preview)` のまま表記し、Message Centerの一次取得も9日連続でできていない
- リポ間の食い違い: Grok 4.6の公開日はxAI一次情報が終始未確認のまま二次報道（8/7ローンチ説）と実際の公開日（8/12）が食い違っていた。ChatGPT広告の日本展開時期も、英語圏報道（8/11開始）と国内報道（6/19開始）で記述が割れている
- DeepSeekの値上げ・重み公開はいずれも発効・公開の当日まで検出が3日遅れた。ベンダーの料金ページを定点で監視する仕組みの欠如が、複数リポで共通の弱点として残っている
