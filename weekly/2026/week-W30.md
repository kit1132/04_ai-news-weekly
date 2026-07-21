# AI ニュース週次サマリー — 2026-W30（2026-07-20 〜 2026-07-26）

> ⚠️ **部分週**: 本サマリーは 2026-07-21（火）実行時点のもの。対象週（月〜日）のうち月曜(07-20)・火曜(07-21)の2日分のみ確定済みで、水曜(07-22)以降は未到来のため未収録。
> 入力: 取得成功 6 / 21（欠損15件は下表参照）
> 生成日時: 2026-07-21（JST）

## ⚠️ 欠損ファイル通知

| 日付 | 欠損リポジトリ | 影響 |
|---|---|---|
| 2026-07-22（水） | [master][copilot][industry] | 実行日未到来のため未収録 |
| 2026-07-23（木） | [master][copilot][industry] | 実行日未到来のため未収録 |
| 2026-07-24（金） | [master][copilot][industry] | 実行日未到来のため未収録 |
| 2026-07-25（土） | [master][copilot][industry] | 実行日未到来のため未収録 |
| 2026-07-26（日） | [master][copilot][industry] | 実行日未到来のため未収録 |

## 今週のハイライト

### 1. Gemini 3.5 Pro、Bloomberg一次報道で「数カ月遅れ」が確定 — Alphabet株下落
**事実**: これまで噂・リーク段階だった Gemini 3.5 Pro の遅延が、Bloomberg（7/16）の現・元従業員10名証言による一次報道で「数カ月遅れ」に格上げされた。6月末に訓練データを更新してコーディング能力改善を図ったが目標未達。報道を受けAlphabet株が下落（CNBC）。master 側でも 7/20・7/21 時点で GA 未達・モデルカード/API/料金/2M context 全て未発表・Vertex AI限定 preview のみ継続と、遅延の長期化を裏付ける観測が続く。
**根拠**: I/O 2026（5/19）発表以降、目標日は6月→7/17→未定と3度逸失。公開APIでGA済みなのはGemini 3.5 Flashのみ。
**影響**: Anthropic・OpenAIが優位モデルを出す中でGoogleが競争力を失うリスクが社内でも懸念されている。予測市場は月末〜8月上旬GAを最有力視。
**行動指針**: モデル選定提案でGemini 3.5 Proを前提に組み込むのは時期尚早。実GAまでは代替（Flash上位版テスト観測あり）を含めて継続監視。
- https://www.bloomberg.com/news/articles/2026-07-16/google-gemini-launch-delayed-as-tech-falls-short-of-internal-goals
- https://www.cnbc.com/2026/07/16/alphabet-stock-gemini-3-5-pro-ai.html
- https://www.cometapi.com/gemini-3-5-pro-release-date-rumored-specifications-all-we-know-in-2026-updated-july-2026/

### 2. EU、Googleに Android・検索データの競合AI開放を命令
**事実**: 欧州委員会が拘束力ある2措置を採択し、競合AIサービスに「Geminiと同等のAndroid機能アクセス」を開放するようGoogleに命令。第三者AIアシスタントを「Hey Google」同様に音声起動でき、アプリ横断タスク（配車予約・返信提案・訪問地情報提供）を実行可能にする必要がある。
**根拠**: 検索データ共有は2027年1月、Android AI機能開放は2027年7月からユーザーに到達見込み。EU成人の6割がAndroid利用。
**影響**: Anthropic/OpenAIのスマホ上エージェント展開余地が広がり、モバイルAIアシスタント選定の前提が構造的に変わる。
**行動指針**: 2027年の施行スケジュールを見据え、モバイルエージェント連携の提案余地を中長期ロードマップに反映。
- https://www.semafor.com/article/07/17/2026/eu-orders-google-to-open-android-ai-system-to-rivals
- https://www.macrumors.com/2026/07/16/eu-google-ai-apps-android-access/

### 3. 中国オープンモデル攻勢が週単位で連続 — Qwen3.8-Max が Kimi K3 に続投
**事実**: Alibabaが2.4兆パラメータのマルチモーダルモデル「Qwen3.8-Max」プレビューを公開（「Fable 5に次ぐ2番手」を自称、独立ベンチ未公表）。7/16のMoonshot「Kimi K3」（2.8兆・オープンウェイト、Frontend Code Arena首位）に続く投入。
**根拠**: Qwen3.8-Maxのオープンウェイト公開は「近く」のみで日付・ライセンス未定、現状はToken Planサブスクのホスト版プレビューのみ。
**影響**: 「大規模×オープン×低価格」の中国勢攻勢が続き、エンタープライズのモデル選定で中国製オープンモデルを比較対象に入れる圧力が強まる。
**行動指針**: モデル選定提案に中国オープンモデルの比較項目を追加し、オープンウェイト公開時期を継続ウォッチ。
- https://www.marktechpost.com/2026/07/19/alibaba-previews-qwen3-8-max-a-2-4-trillion-parameter-multimodal-model-days-after-moonshots-kimi-k3-open-weight-launch/
- https://dataconomy.com/2026/07/20/qwen3-8-24t-parameters-alibaba-ai-model-launch/

### 4. NVIDIA×Noetra、日本に世界初の「国家AIファクトリー」— 5年で最大約1兆円
**事実**: NVIDIAと国策AI企業Noetraが、140MW・NVIDIA Rubin GPU 27,500基＋Vera CPU 13,750基の「国家AIファクトリー」を構築。経産省「FRONTia プロジェクト」の計算基盤として、ロボティクス/デジタルツイン/産業自動化向けのオープン多モーダル基盤モデルを学習し、学習済み重みを国内開発者へ広く共有。
**根拠**: 6/30にNEDO公募採択、FY2026-2030で初年度3,873億円・5年で最大約1兆円。建設2027年4月着工・稼働2028年6月予定。SoftBank/Sony/NEC/Honda中核、44社超参画。
**影響**: 主権AI・国産オプションの提案根拠が強化される大型インフラ投資。
**行動指針**: 国内提案で主権AI/国産モデル選択肢を扱う際の一次事例として本件を引用可能。
- https://www.tomshardware.com/pc-components/gpus/nvidia-and-japans-noetra-consortium-to-build-140mw-rubin-ai-factory-with-27500-gpus
- https://blogs.nvidia.co.jp/blog/japan-government-industrial-leaders-and-nvidia-launch-the-worlds-first-national-ai-infrastructure/

### 5. Claude Code v2.1.215 — verify / code-review スキルの自動実行を廃止
**事実**: Claude Code v2.1.215（7/19）で `/verify` と `/code-review` スキルの自動実行を廃止し、ユーザーが明示的に呼び出したときのみ起動するよう変更。あわせてWindows PowerShellブロック環境での `/background` 失敗、パス補完中のシェルモード不具合、`/ultrareview` のPR参照拒否を是正。
**根拠**: master・copilot 両リポで7/20時点の最新版として確認、ワークフロー影響大の変更と明記。
**影響**: 従来Claudeが自動起動していたverify/code-reviewが呼ばれなくなるため、品質チェック工程を組み込んだ運用では明示呼び出しへの移行が必要。
**行動指針**: 本プロジェクト含め、`/verify`・`/code-review` に依存する自動化フロー・CLAUDE.md記載手順を点検し、明示呼び出しへの切替を確認する。
- https://code.claude.com/docs/en/changelog
- https://github.com/anthropics/claude-code/blob/main/CHANGELOG.md

## Claude / Anthropic

### Claude Enterprise Admin API のユーザー管理機能が beta 提供開始 — [master]
- claude.ai組織のメンバーをAdmin APIから管理可能に。メンバー一覧・メールアドレス検索、ロール変更、削除、招待の送信・取消、グループとそのメンバーシップ管理、カスタムロールの読み取りに対応。グループ／カスタムロール系リクエストは `anthropic-beta: ce-user-management-2026-07-13` ヘッダーが必要（メンバー・招待系は不要）。`read:org_audit` スコープのAdmin APIキーで全GETエンドポイントを呼べる。
  https://platform.claude.com/docs/en/manage-claude/admin-api

### Fable 5 が前払いクレジット運用へ移行 — [master]
- 7/19 23:59 PTで無償提供（週次上限の最大50%）とClaude Code週次上限+50%促進が終了。7/20以降は前払いクレジット（$10 / $50）で利用し、上限は標準水準に復帰。モデル仕様（1M context / 128k output）とプランの変更はなし。
  https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5

### Claude Mythos Preview が7/21で退役 — [master]
- `claude-mythos-preview` が予定どおり退役（リクエストは失敗するようになる）。移行先はProject Glasswingの `claude-mythos-5`（Fable 5と同等能力・safety分類器なし・限定提供）。仕様は1M context / 128k output / $10・$50で据え置き。widely-released側のFable 5・Opus 4.8等には影響なし。
  https://platform.claude.com/docs/en/about-claude/model-deprecations

## コーディングエージェント / 開発ツール

### GitHub Copilot CLI v1.0.72 安定版リリース — [master][copilot]
- pre-release v1.0.72-1（7/17）を経て安定版が確定（7/20）。常にブロックする `agentStop` フックの無限ループを是正（8回連続ブロックでターン終了）、follow-upメッセージでのマルチターンサブエージェントを常時有効化、`/add-dir` ディレクトリのセッション横断可視化を追加。セキュリティ面ではOSサンドボックスのmacOS keychainアクセスを既定オフ、サンドボックス内でのgit/gh認証をオプション提供。UX面では `/plugins` ヘルプコマンド、`copilot plugins install --skill`、セッションサイドバーのキーボード操作、`$` プロンプトショートカット、`/model --session` を追加。ワークツリー作成の堅牢性も向上。
  https://github.com/github/copilot-cli/releases

### OpenAI Codex CLI — alphaのみ前進、安定版は据え置き — [master]
- alphaが0.145.0-alpha.25（7/20）まで進行。安定版は0.144.6（7/18）据え置きで新機能追加なし。Cursorは3.11（7/11）＋Slack版強化（7/17）から新規リリースなし。
  https://github.com/openai/codex/releases

### Microsoft/Copilot Studio 一次情報源は据え置き — [copilot]
- Copilot Studio - What's New（June据え置き）、M365 Copilot Release Notes（July 15バッチ据え置き、次バッチは7/29前後見込み）、Power Platform Released Versions（Copilot Studio Build 2026.6.3据え置き、火曜更新の要監視日だった7/21も2026.7.x未反映で次回7/28へスライド）。

## 資金・資本

### Fireworks AI が $1.5B Series D（評価額$17.5B）— [industry]
- Nvidia出資のFireworks AIが$15.05億Series D、評価額$175億（主導Atreides / Index / TCV、Lightspeed・Nvidia・Menlo等参加）。ARR $10億超（前年比5倍）・日次40兆トークン処理、うち95%超が顧客の独自データに特化させたオープンモデル。「汎用クローズドモデルを、特化＋低コスト＋高速で置換」路線が評価を獲得。あわせて8090 Labsが$135M Series A（Salesforce Ventures主導、規制産業向けエージェント型「Software Factory」）を調達。
  https://www.cnbc.com/2026/07/16/fireworks-nvidia-cloud-ai-startup-value.html

### DeepSeek、中国本土IPOを準備 — [industry]
- Bloomberg（7/14）: DeepSeekが中国本土でのIPO申請を年末〜2027年初に予定、財務報告を12月末までに整備中。上場前の私募でプレマネー評価額最低4,800億元（約$710億）の新ラウンドも協議。Anthropic（10月観測）・OpenAI（2027）・DeepSeekと米中フロンティアのIPO競争が並走。
  https://www.bloomberg.com/news/articles/2026-07-14/deepseek-mulls-new-funding-weeks-after-7-billion-round-ft-says

## 国内エンタープライズ・ハードウェア

### ソフトバンク「Patching as a Service」を3,000社へ本格提供 — [industry]
- ソフトバンクとSB OAI Japanが、OpenAIのセキュリティ特化モデル「GPT-5.5-Cyber」基盤の「Patching as a Service」を重要インフラ企業3,000社へ本格提供開始。脆弱性診断→修復方針策定→パッチ適用提案までを一気通貫で支援。発表時点で金融・交通・製造など137社が導入意向。7/16に約1,000名規模の「エンタープライズAIサイバー防衛室」を設置。
  https://www.softbank.jp/en/corp/news/press/sbkk/2026/20260714_02/

### OpenAI初のハードウェア「Codex Micro」— $230のエージェント操作キーボード — [industry]
- OpenAIがコーディングエージェントCodex操作用の$230キーボード「Codex Micro」を発表（Work Louder共同設計）。13スイッチ、エージェント状態を示す発光「Agent Keys」、推論量を調整するダイヤル、ワークフロー起動用ジョイスティック。Appleとの営業秘密訴訟のさなかでの初ハード投入。限定生産・今月中出荷。
  https://techcrunch.com/2026/07/15/amid-hardware-legal-battle-openai-releases-a-230-keyboard-for-codex/

## 来週の注目予定

- **7/23**: OpenAI computer-use-preview シャットダウン
- **7/28**: Power Platform Released Versions 版ページ次更新（2026.7.x 反映見込みの要監視日、7/21分は未反映でスライド済み）
- **7/29 前後**: M365 Copilot Release Notes 次バッチ見込み
- **7/30**: M365 Copilot メモリ活用のエージェント提案 GA 予定
- **7/31**: Devin classic 環境設定 read-only 参照終了
- **8/1**: covered frontier model 60 日 EO 期限
- **8/3**: 旧「Claude in Slack」退役
- **8/5**: Opus 4.1 Claude API 退役 / Cowork 倍増利用枠終了
- **8/9**: ChatGPT Atlas シャットダウン
- **8/26**: OpenAI Assistants API 廃止 / o3 退役 / GPT-4.5 完全廃止
- **8/31**: Sonnet 5 促進価格終了（→ $3/$15）
- **9 月**: iOS 27 / macOS 27 GA（AFM 3 本番）

## 改善メモ

- 3リポとも新規提案・障害の変化なし（継続分は各リポの IMPROVEMENT-BACKLOG.md 参照）。
- [master] 月曜（7/20）の週次復旧チェック実施: `developers.openai.com/changelog`・`community.openai.com/c/announcements/6.rss`・`www.anthropic.com/news` の403は継続（未復旧）。
- [copilot] 継続提案5件（最多: B-005 Qiita RSS の WebSearch 化、6回目）。
- [industry] 継続提案1件（B-004 取得方法欄を WebSearch 優先へ、22回目）。
- 本サマリーは部分週（07-20〜07-21分のみ）での生成。次回定例実行（日曜09:00 JST）では対象週が2026-W31（07-27〜08-02）に切り替わる点に留意。
