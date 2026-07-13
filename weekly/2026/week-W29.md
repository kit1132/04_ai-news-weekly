# AI ニュース週次サマリー — 2026-W29（2026-07-13 〜 2026-07-19）

> **部分週（〜2026-07-13 実行日まで）**: 月曜実行のため対象週のうち月曜1日分のみが確定データ。火〜日は未到来のため対象外（欠損ではない）
> 入力: 取得成功 3 / 3（対象1日 × 3リポ、欠損なし）
> 生成日時: 2026-07-13（JST）

## 今週のハイライト

### 1. Apple が OpenAI をトレードシークレット窃取で提訴

**事実** Appleが7/10、カリフォルニア州北部連邦地裁でOpenAIをトレードシークレット窃取で提訴した。OpenAIがハードウェア事業のため、Appleの未発表製品情報（部品・図面・資料）をApple従業員に共有させたと主張している。

**根拠** OpenAIハードウェア責任者で元Apple VPのTang Tanが、採用面接中のApple現職者に実部品を「show and tell」で持参させ社内機密の共有を促したと指摘。元Appleエンジニアが貸与PCで機密文書をダウンロードし、退職後も返却しなかったとの主張も含まれる。

**影響** 2024年のiPhone×ChatGPT統合以来の両社提携が、OpenAIのハードウェア参入（Jony IveのioProductsを$6.4Bで買収）を機に冷却化していた流れが訴訟という形で表面化した。

**行動指針** Apple Intelligenceへのベンダー統合等、Apple↔AIベンダーの提携動向を追う上での背景として注視する。

- https://www.cnbc.com/2026/07/10/apple-openai-lawsuit-trade-secrets.html
- https://techcrunch.com/2026/07/10/apple-sues-openai-over-alleged-trade-secret-theft/
- https://fortune.com/2026/07/10/apple-openai-lawsuit-trade-secrets-theft-allegations/

### 2. エンタープライズAIエージェントに「評価ギャップ」— VentureBeat Researchが573名調査で定量化

**事実** VB Transform 2026（7/14-15・Menlo Park）を前に、VentureBeat Researchが従業員100名以上の企業リーダー573名（2026年6月実施、オーケストレーション/信頼性・評価/セキュリティ・ID/インフラ・計算/コンテキスト・RAGの5調査）を対象にしたエンタープライズAIエージェント調査シリーズを公開した。

**根拠** 半数の企業が「社内評価をパスしたエージェント/LLM機能が顧客対応で失敗」を経験し、うち4社に1社は複数回発生。にもかかわらず66%が人間レビューなしの本番投入を一部許可済み、または今後12カ月で構築予定と回答。自社GPU運用企業の86%が稼働率50%以下。27%は「請求書が来て初めてエージェントのコストを知る」リアクティブ統制のみで、エージェント単位の予算・上限を持たない。

**影響** 自律度の上昇が保証（アシュアランス）整備を追い越している実態が定量データで裏付けられた。GPU遊休データは「AIバブル論」に対する過剰投資の実証にもなる。

**行動指針** エージェント導入提案では「モデル選定」より「評価・ガードレール・人間レビュー境界・エージェント単位のコスト上限」の設計を本丸として提示する。自社GPU稼働率データはクラウド従量 vs 自社GPUのTCO精査の切り口として活用できる。

- https://venturebeat.com/orchestration/enterprise-ai-is-entering-an-evaluation-gap-agents-are-gaining-autonomy-faster-than-companies-can-verify-them
- https://venturebeat.com/orchestration/wall-street-is-debating-the-ai-buildout-enterprises-just-answered-86-say-their-gpus-run-at-half-capacity-or-less

### 3. Bun の Zig→Rust 全面移植を Claude Fable 5 が11日・約$165kで完遂

**事実** JavaScriptランタイムBunが、約53.5万行のZigコードをClaude Fable 5を用いて11日間（実働約6日、作業期間5/3〜5/14）でRustへ全面移植したと7/10〜7/12に複数メディアが報道した。

**根拠** 「implementer/reviewer」を分けた並列ワークフローでClaudeを最大64インスタンス並走させ、Claude Code内で約50の動的ワークフローを実行。2,000ビルドのストレステストでメモリ6.7GB→609MB、性能+2〜5%、バイナリ約20%縮小を達成。API換算コストは約$165,000（非キャッシュ入力59億トークン、出力6.9億トークン、キャッシュ入力読み72億トークン）で、作者はAIなしなら「エンジニア3名×約1年」と試算している。

**影響** 大規模言語移行におけるAI支援リファクタリングのROIを示す具体事例が得られた。人月換算3人年→11日・$165kという数字はモダナイゼーション案件の投資対効果の参照値になる。

**行動指針** レガシー大規模リファクタリング・言語移行案件の提案でROI試算の参照値として引用する。並列エージェント運用（実装役と検証役の分離）を品質担保の設計パターンとして検討する。

- https://www.publickey1.jp/blog/26/javascriptbunclaude_fable_511zigrustclaude.html
- https://gigazine.net/news/20260712-bun-zig-rust/

### 4. Claude Fable 5、有料プラン無償提供が7/12で終了 — 利用クレジット経由へ移行

**事実** Fable 5（Pro/Max/Team/premium seat型Enterprise向け）の追加課金なし提供が、予定通り7/12 23:59 PTで終了した。7/12以降、Fable 5は各プランの週次利用上限（included weekly usage）にカウントされず、利用クレジット経由での提供に移行する。

**根拠** 公式ドキュメント上も「Fable 5 / Mythos 5へのアクセスは復旧済み」（6/12の輸出規制→6/30解除→7/1再展開の一連の流れ）と明記されており、現行仕様は1M context / 128k output / $10・$50で据え置き（Fable 5はrefusal分類器ありで違反技術を99%+ブロックしOpus 4.8へリルート、Mythos 5は分類器なしでProject Glasswing限定）。

**影響** Fable 5を常用するチームは7/12以降、利用クレジット消費によるコスト増に直面する。

**行動指針** Fable 5利用組織は利用クレジットの有効化状況・予算を至急確認する。

- https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5
- https://www.anthropic.com/news/redeploying-fable-5

---

## 開発ツール — [master][copilot]

- Claude Code v2.1.207（7/11）・Cursor 3.11（7/10）・Codex CLI alpha 0.145.0-alpha.4（7/11・安定版0.144.1）はいずれも据え置き。週末を挟み新バージョンなし
- **GitHub Copilot CLI**: [copilot]が本日v1.0.70（7/9・回収）を新規記録。GPT-5.6モデル対応、`--sandbox`/`--no-sandbox`フラグ（セッション単位のシェルサンドボックス制御）、プロンプト書き換え用`/refine`新設、ページング対応MCPリソース管理、信頼済みリポジトリ設定（`.github/copilot/settings.json`、モデル・reasoning effortのリポジトリ単位ピン留め）を追加。一方[master]はpre-release v1.0.71-0（7/10）を「据え置き」と記録しており、両リポでバージョン系列の表記に食い違いがある（改善メモ参照）
- **Claude Code週次上限+50%プロモ**（5月開始）が本日7/13に期限到来。延長発表は[copilot]確認時点で未確認

## Microsoft Copilot / Power Platform — [copilot]

- 一次情報は静穏継続。Released Versionsは最新Build 2026.6.3（6/30初出）のまま。版ページは火曜更新のため次回7/14が要監視
- M365 Copilot Release NotesはJuly 01バッチ（対象6/17〜7/1）が最新でoff-cycleバッチなし。次バッチは隔週傾向で7/14〜7/15前後見込み
- Power Platform Blogの「What's New in Power Platform: July 2026」フィーチャー更新は未公開（最新は6/11のJune Feature Update）。2026 Release Wave 2計画ページも403継続で未公開

## OSS・ローカルLLM — [industry]

- 推論エンジン「Colibrì」（Pure C・依存ゼロ）が、744BパラメータのMoEモデルGLM-5.2を約25GB RAMのコンシューマ機で実行（7/10・HN 453ポイント）。密部（int4で約9.9GB）のみ常駐させ、21,504のルーテッド・エキスパート（計約370GB）をディスクからLRUキャッシュでストリーミング。MLA注意（KVキャッシュ57倍圧縮）・投機的デコード等で省メモリ化。速度は0.05〜1 tok/sで本番向けではないが、API契約前の大型OSSモデルのフィージビリティ検証用途に意味を持つ
  - https://github.com/JustVugg/colibri

## 継続ウォッチ — [master][industry]

- **GPT-5.6の全面展開**: ChatGPT Teamへの全面提供は7/14予定（本日時点で追加報なし）。Enterprise文脈長は1.5Mトークン（GPT-5.5の400Kの約3.75倍）
- **Gemini 3.5 Pro**（7/17 GA目標）: 変化なし。第三者報道は7/17目標で一致するがGoogle公式のモデルカード・API仕様・確定価格は未発表。2Mトークン文脈・Deep Think層を予告、Vertex AI限定プレビュー継続

---

## 来週の注目予定

- **7/14**: iOS 27 Public Beta公開予定 / Visio→Power Automateエクスポート廃止発効 / M365 Copilot Release Notes次バッチ見込み / Copilot Studio版ページ次更新（2026.7.x反映見込み） / GPT-5.6のChatGPT Team全面提供
- **7/15**: Claude Science（AI for Science）応募締切 / M365 Copilotアプリ新UI（MC1325422）のopt-outトグル終了・以降デフォルト化
- **7/17**: Claude Corps第1期応募締切 / Gemini 3.5 Pro GA候補日（未確定）
- **7月中旬〜下旬**: 2026 Release Wave 2計画ページ公開見込み / Grok 4.5 EU提供予定 / ChatGPT WorkがPlus・Businessへ拡大予定
- **7/21**: Copilot Cowork GA告知イベント
- **7/23**: OpenAI computer-use-previewシャットダウン
- **7/31**: Devin classic環境設定のread-only参照終了
- **7月下旬〜8月**: M365 Copilotサービスプラン挙動変更（Premium/Basicのアクセス制御がサービスプラン主導に）
- **8/1**: covered frontier model 60日EO期限
- **8/3**: 旧「Claude in Slack」退役
- **8/5**: Opus 4.1 Claude API退役 / Cowork倍増利用枠の終了
- **8/26**: OpenAI Assistants API廃止 / o3退役 / GPT-4.5完全廃止
- **8/31**: Sonnet 5促進価格終了（$2/$10 → $3/$15）
- **9月**: iOS 27 / macOS 27 GA（AFM 3本番）

---

## 改善メモ

- **[master][copilot]**: GitHub Copilot CLIの最新版表記に食い違いあり。[master]はpre-release v1.0.71-0（7/10）を「据え置き」と記録する一方、[copilot]はv1.0.70（7/9・回収）を本日の新規更新として記録。バージョン系列（pre-release番号の前後関係）の整合性確認が必要
- 3リポとも新規提案・障害の変化なしと報告（継続分は各リポIMPROVEMENT-BACKLOG.md参照）
- **[industry]**: 継続提案1件（B-004 取得方法欄のWebSearch優先化、14回目）。RSS/WebFetch全ソース403が継続
