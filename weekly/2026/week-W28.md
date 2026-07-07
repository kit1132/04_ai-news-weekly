# AI ニュース週次サマリー — 2026-W28（2026-07-06 〜 2026-07-12）

> **部分週（〜2026-07-07 実行日まで）**: 火曜実行のため対象週のうち月・火の2日分のみが確定データ。水〜日は未到来のため対象外（欠損ではない）
> 入力: 取得成功 6 / 6（対象2日 × 3リポ、欠損なし）
> 生成日時: 2026-07-07（JST）

## 今週のハイライト

### 1. GPT-5.6 広域GA、7/7は空振り — 予測市場「7/9」へ再プライシング、実質ゲートは政府枠組み

**事実** 6/26開始の限定プレビュー（米政府承認の約20組織向け・API＋Codex）から続くGPT-5.6（Sol/Terra/Luna）の広域GAについて、予測市場（Polymarket）は7/6時点で「7/7」を約74%で織り込んでいた。しかし7/7当日は限定プレビューのまま経過し広域GAは実現せず、市場は即日「7/9」（約59%）へ首位が入れ替わった。

**根拠** ゲートは日付ではなく6/2大統領令（EO 14409）に基づく任意フレームワーク（フロンティアモデルを公開前に最大30日、政府が事前テスト）。AIサイバーセキュリティ・クリアリングハウスは7/2設置期限だったが、枠組み本体のfinalizeは8/1予定であり、GA日はこの政府側プロセスの完了に連動する構図。個人ChatGPTへの搭載可否・提供プランは依然未確定。

**影響** モデル性能ではなく政府承認プロセスがフロンティアモデルの出荷カレンダーを実質規定する構図が、1日で「74%織り込み→空振り→7/9へ再プライシング」という形で可視化された。同型のゲートはGemini 3.5 Pro（Vertex AI限定プレビュー継続）にも波及しうる。

**行動指針** GPT-5.6導入計画は日付ではなく8/1の枠組みfinalizeを起点にスケジュールを引き直す。予測市場の織り込みは短期的に大きく振れるため単独の根拠にしない。

- https://openai.com/index/previewing-gpt-5-6-sol/
- https://polymarket.com/event/gpt-5pt6-released-onptptpt-20260623051439980
- https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/

### 2. Claude Fable 5、本日7/7で無償枠終了 → usage creditsの従量課金へ

**事実** Anthropicが7/1にグローバル復帰させたFable 5の導入枠（Pro/Max/Team/一部Enterpriseで週次利用上限の最大50%まで無償）が本日7/7で終了。以降はusage credits（API準拠レート 入力$10・出力$50 per Mtok）での従量利用に移行し、credits未有効化のテナント/シートはFable 5へアクセス不可となる。

**根拠** Anthropicは「capacity回復までの一時措置」と説明。標準Enterpriseシートには無償枠がなく、credits有効化が前提。3リポともこの切替を今週の主要トピックとして記録しており（[master][copilot][industry]）、[copilot]は7/8以降を従量課金開始と記す一方、[industry]は7/7当日を終了日・7/8を課金開始日と整理しており表現上の起点にわずかなズレがあるが内容に矛盾はない。

**影響** Fable 5を常用するチームは7/8以降のコスト増に直面する。credits未有効化のテナントはアクセス断が生じるため、事前確認を怠ると業務影響が出る。

**行動指針** Fable 5利用組織はusage credits有効化状況を至急確認。コスト増を前提に予算・利用ポリシーを見直す。

- https://www.anthropic.com/news/redeploying-fable-5
- https://www.searchenginejournal.com/anthropics-claude-fable-5-is-back-with-new-usage-limits-and-safeguards/581231/
- https://releasebot.io/updates/anthropic

### 3. GitHub Models、7/30全面廃止 — 猶予なし・Azure AI Foundryへの移行必須

**事実** GitHub Modelsが2026-07-30に全面リタイア（7/1告知）。プレイグラウンド・モデルカタログ・推論API・BYOKエンドポイントを含む全機能がFree/Team/Enterpriseすべてで停止し、grandfathering（既存利用者の継続利用）はない。移行先はAzure AI Foundry。

**根拠** 移行前の予行として7/16・7/23にブラウンアウト（一時的にエラーを返す）を実施予定。企業側は送信先許可リストに`*.azure.com`とFoundryエンドポイントを追加するIT/セキュリティレビューが必要で、残り期間内に間に合わないリスクが指摘されている。

**影響** GitHub Models依存の開発ワークフローは今月中に移行を完了させないとサービス断に直面する。ブラウンアウト日程は移行漏れを洗い出す実質的なテスト機会になる。

**行動指針** GitHub Models利用箇所の棚卸しとAzure AI Foundryへの移行計画を今月中に確定。7/16・7/23のブラウンアウトを移行検証の機会として活用する。

- https://github.blog/changelog/2026-07-01-github-models-is-being-fully-retired-on-july-30-2026/

### 4. AIチップ内製競争が加速 — AnthropicもSamsungと2nmで協議

**事実** AnthropicがSamsungと独自AIチップの製造を予備協議中と報じられた（7/2）。Samsungの2nmプロセス・先端パッケージングの活用を評価している段階で、用途・仕様・電力性能は未定。元OpenAIチップ設計チームのClive Chanが合流し内製ハード知見を補強している。

**根拠** 量産・出荷は早くて2027年後半の見込み。Anthropicは「Google/Amazon/Nvidiaを含む多様なハードスタックが引き続き中核」とコメントしており、既存クラウド依存を完全に置き換えるものではない。OpenAIの「Jalapeño」（6/24・Broadcom協業）に続く動き。

**影響** 主要AIラボが揃って脱Nvidia・自社シリコンへ動く構図が鮮明化。半導体・パッケージング企業への提案機会が広がる一方、実際の量産は数年先で短期的な調達構造への影響は限定的。

**行動指針** 半導体・データセンター関連の提案では「主要ラボの内製シリコン化」を中長期トレンドとして引用しつつ、短期の調達構造は既存クラウド（Nvidia/TPU/Trainium）依存が継続する前提で設計する。

- https://techcrunch.com/2026/07/02/anthropic-is-discussing-a-new-custom-chip-with-samsung/

### 5. 資本・政策：SoftBankがOpenAIへ第2トランシェ$10B実行、OpenAIは米政府への5%出資を提案

**事実** SoftBankが7/1、OpenAIへの追加出資の一環として第2トランシェ$10Bを実行（第3弾$10Bは10/1予定）。並行してOpenAIが米政府への5%出資（約$42.6B相当）を提案していると報じられた（7/2、Altmanが政権幹部と協議）。

**根拠** SoftBankの出資は2/27公表の総額$30B追加出資の一部でVision Fund 2経由。OpenAI提案はアラスカ永久基金を範に、他の主要AIラボにも同様の政府出資を求める構図で、現時点は概念段階（議会承認が必要）。

**影響** 巨額資本の投入とAI企業の富の国民還元を求める超党派の政治圧力が同時進行しており、資本構造・規制双方の不確実性が高い状態が続く。

**行動指針** OpenAI関連の投資・提携検討では、政府出資提案の帰趨（議会承認の有無）とIPOタイミング（2027年延期観測あり）を並行してウォッチする。

- https://group.softbank/en/news/press/20260701
- https://www.forbes.com/sites/siladityaray/2026/07/02/openai-reportedly-pitches-granting-us-government-5-stake/

---

## 開発ツール — CLI小刻み更新 / Copilot CLIに自動承認モード — [master]

- **GitHub Copilot CLI**: pre-release v1.0.69-1（7/4）で**auto allow-all モード**（LLMジャッジが許容可と判断したリクエストを自動承認）と`stayInAutopilot`設定（継続autopilot運転）を追加。v1.0.69-2（7/6）では`/rubber-duck`のpre-authヘルプ表示、MCPサーバのCLI OAuth認証などを追加。安定版はv1.0.68（7/1）のまま
- **OpenAI Codex CLI**: pre-release 0.143.0-alpha.36〜37（7/5・7/6）と日次で小粒更新が継続。安定版は0.142.5（7/1）のまま
- **Claude Code**: 新バージョンなし。最新はv2.1.201（7/3）
- **ChatGPT**: 全プラン向けに新しいspeech-to-textディクテーションモデルを展開（多言語混在・言語スイッチ・騒がしい環境等の書き起こし精度改善）。ChatGPT BusinessにPlugin管理者統制、Remote Controlの1対1認証付きQRペアリングも追加

## Microsoft / Copilot Studio — 一次情報の動きなし — [copilot]

- Copilot Studio基盤（Released Versions）は最新Build 2026.6.3（6/30初出）のまま。版ページは火曜更新だが7/7時点で次ビルド未反映（日中反映の可能性あり）
- M365 Copilot Release Notesは「July 01バッチ」が最新（透かし・秘密度ラベル継承・エージェントのスケジュール実行等）。次バッチは隔週傾向で7/14〜7/15前後見込み
- Power Platform Blogの「What's New in Power Platform: July 2026」は未公開（最新は6/11のJune 2026 Feature Update）

## 国内データ — JUAS「企業IT動向調査2026」速報：生成AI導入済み33.9% — [industry]

- JUAS（日本情報システム・ユーザー協会）が東証上場企業等4,500社対象（有効回答957社）の速報を公開。言語系生成AI「導入済み」33.9%、試験導入含め53.4%、売上1兆円以上の企業では85.1%が導入済みと、企業規模による導入格差が明確
- 国内エンプラの生成AI浸透度を示す一次データとして提案資料に引用可能

## 継続ウォッチ — [master][industry]

- **Google Gemini 3.5 Pro**: 7月第2週入りもなお限定プレビュー。Vertex AI限定Enterprise previewのみでGA日・確定価格とも未発表（一部報道で7/17説）
- **Anthropic vs OpenAI 競争構図**: Anthropicの売上ランレート$30B超（自己申告ベースでOpenAI逆転）から新規進展なし

---

## 来週の注目予定

- **7/8**: Anthropic 政府発行ID・生体認証ポリシー施行
- **7/9**: GPT-5.6 広域GA、予測市場で最有力視（約59%）
- **7/13**: Claude Code 週次上限+50%プロモ（5月開始）の期限（延長なき場合）
- **7/14**: 破壊的変更 — Visio → Power Automate エクスポート廃止発効 / M365 Copilot Release Notes 次バッチ見込み
- **7/15**: Claude Science（AI for Science）応募締切
- **7/16・7/23**: GitHub Models 移行ブラウンアウト（一時的エラー返却）
- **7/17**: Claude Corps 第1期応募締切 / Gemini 3.5 Pro GA候補日（未確定）
- **7月中旬〜下旬**: 2026 Release Wave 2 計画ページ公開見込み
- **7/21**: Copilot Cowork GA 告知イベント
- **7/23**: OpenAI computer-use-preview シャットダウン
- **7/30**: GitHub Models 全面廃止
- **7/31**: Devin classic 環境設定の read-only 参照終了
- **7月下旬〜8月**: M365 Copilot サービスプラン挙動変更（Premium/Basicのアクセス制御がサービスプラン主導に）
- **8/1**: covered frontier model 60日 EO 期限（GPT-5.6/Gemini 3.5 Pro の広域リリース条件を規定する連邦フレームワーク成果物の期日）
- **8/3**: 旧「Claude in Slack」退役
- **8/5**: Opus 4.1 Claude API 退役
- **8/26**: OpenAI Assistants API 廃止 / o3 退役 / GPT-4.5 完全廃止
- **8/31**: Sonnet 5 促進価格終了（$2/$10 → $3/$15）
- **9月**: iOS 27 / macOS 27 GA（AFM 3 本番）

---

## 改善メモ

- **[master] B-006**: 宿題ソース`platform.claude.com`（Fable 5/Mythos 5ドキュメント）でWebFetch疎通を確認し、取得方法欄をプライマリに確定
- **[master] B-001**: 月曜復旧チェックで主要ソース一括403は継続（`developers.openai.com/codex/changelog`も403継続、GitHub releases一次運用を継続）
- **[industry] B-004**: `daily-sources.md`取得方法欄のWebSearch優先化の継続提案（7回目→8回目）。RSS/WebFetch全ソース403が週を通じて継続
- **[copilot]**: 新規提案・障害の変化なし
