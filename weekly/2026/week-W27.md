# AI ニュース週次サマリー — 2026-W27（2026-06-29 〜 2026-07-05）

> 入力: 取得成功 21 / 21
> 生成日時: 2026-07-05（JST）

## 今週のハイライト

### 1. Fable 5 / Mythos 5 世界停止が決着 — 米輸出規制解除で7/1グローバル復帰

**事実** 週初（6/29、停止18日目）時点でFable 5は依然全世界で停止中、Mythos 5のみAnnex A（重要インフラを運用・防衛する米組織約100）に限定提供。Axios報道の「今週中復旧」観測はPentagon・NSAの最終署名待ちで6/30も足踏みが続いたが、米商務省（Lutnick長官署名）が6/30に輸出規制を解除し、7/1 15:31 ET にClaude Platform / Claude.ai / Claude Code / Claude Cowork でFable 5がグローバル復帰。6/12開始から約3週間の全世界停止サーガが決着した。

**根拠** 発端はAmazon研究者によるMythos 5のjailbreak発見・通報（Fortune）。Anthropicは再訓練した分類器で当該手法を99%超ブロックする対策を導入（副作用としてコーディング系benignリクエストの誤検知が増加）。7/7までは週次利用上限の最大50%まで込みで利用可、以降はusage credits経由（API直販レート入力$10/出力$50 per Mtok）。あわせてAmazon・Microsoft・Google等Glasswingパートナーと共同でjailbreak深刻度を4軸評価する業界横断フレームワークを提案し、再発防止を制度化する動きを見せた。

**影響** 3リポとも週後半に「決着」を報告したが速報タイミングにはズレがあった。[master][copilot]は7/1時点でも「Pentagon/NSA署名待ちで停止継続」と記録し復帰確認は7/2にずれ込んだ一方、[industry]は7/1のうちに商務省解除・復帰の一次情報を捕捉している。7/8に予定される政府発行ID・生体検証ポリシー施行が、今後のFable 5運用（本人確認要否）に影響する可能性が残る。

**行動指針** Fable 5利用組織は7/7の従量課金移行（$10/$50 per Mtok）に備えusage credits有効化を確認。Opus 4.8への自動フォールバック挙動を前提とした設計を継続。7/8のID検証ポリシー施行後の運用変更を注視する。

- https://www.anthropic.com/news/redeploying-fable-5
- https://www.cnbc.com/amp/2026/06/30/anthropic-says-trump-admin-has-lifted-export-controls-on-claude-fable-5-and-mythos-5.html
- https://www.anthropic.com/news/expanding-project-glasswing
- https://www.digitalapplied.com/blog/claude-fable-5-usage-credits-july-7-pricing-guide-2026

### 2. Claude Sonnet 5 GA（6/30）— Opus 4.8比で大幅安、エージェント用途特化

**事実** Anthropicが6/30にClaude Sonnet 5をGA。Free/Proのデフォルトモデルに昇格、Max/Team/Enterpriseでも利用可能。Claude Code v2.1.197（6/30）も既定モデルをSonnet 5に変更し、1Mトークンのネイティブコンテキストに対応した。

**根拠** 導入価格は$2/$10 per Mtok（8/31まで、以降$3/$15）でOpus 4.8比大幅ディスカウント。ベンチはagentic coding 63.2%（Opus 4.8 69.2%、Sonnet 4.6 58.1%）。新トークナイザ採用により同一入力でも1.0〜1.35倍のトークン数になり得る点に注意。あわせて研究者向けの「Claude Science」も投入（ツール統合・監査可能な成果物生成）。

**影響** [copilot][industry]は当初本リリースを取りこぼし、7/3にキャッチアップ報告する遅れが発生（注目度の高いニュースでも見逃しが起き得ることを示す事例）。週後半にはAnthropicの売上ランレートが$30B超に到達し自己申告ベースでOpenAIを逆転したと報じられ、Sonnet 5等の需要拡大が牽引役と分析されている。

**行動指針** エージェント常時稼働のコスト最適化としてSonnet 5導入を検討。新トークナイザによるコスト試算の見直しと、8/31の促進価格終了に向けた予算計画の確認を推奨。

- https://www.anthropic.com/news/claude-sonnet-5
- https://venturebeat.com/technology/anthropic-launches-claude-sonnet-5-at-a-steep-discount-to-its-top-model-as-the-company-races-toward-a-blockbuster-ipo
- https://techcrunch.com/2026/06/30/anthropic-launches-claude-sonnet-5-as-a-cheaper-way-to-run-agents/
- https://venturebeat.com/technology/anthropic-says-it-hit-a-30-billion-revenue-run-rate-after-crazy-80x-growth

### 3. Claude Code が1週間で6版リリース — Chrome拡張GA・自律push/PR・権限モードManual化・gateway新設

**事実** 週内にv2.1.196〜v2.1.201をリリース。Claude in Chromeが一般提供化（v2.1.198、7/1）。バックグラウンドエージェントがコード作業完了時に自動でcommit・push・draft PR作成するよう既定変更（従来は都度確認）。v2.1.200（7/3）でデフォルト権限モードが「default」から「Manual」に改称・変更され、AskUserQuestionダイアログの自動継続も既定で廃止。あわせてセルフホスト型の「Claude apps gateway」（社内IdP経由OIDC SSO）を新規提供開始した。

**根拠** 背景セッション・サブエージェントの安定性を集中修正（sleep/wake後の無言停止、stall再起動後のキャンセル済みターン再実行等）。Exploreサブエージェントが親セッションのモデルを継承するよう変更。Anthropicが3月にClaude Codeへ仕込んでいた「競合検出用の隠しコード」（steganographyマーカー）も批判を受けて削除された。

**影響** 承認待ちのボトルネックが外れ非同期エージェント運用が既定挙動化する一方、権限モードのManual既定化・AskUserQuestion自動継続廃止は「エージェントが勝手に進む」挙動を絞る安全側の変更で、自律実行の範囲拡大と要所での人間承認回帰が同時に進んだ週といえる。gatewayはデータ所在要件を持つ企業のオンプレ/自社クラウド統制ニーズに応える。

**行動指針** 自動化パイプラインはv2.1.200以降のManual既定化・AskUserQuestion挙動変更を前提にテストを更新。データ所在要件がある組織はClaude apps gateway導入を検討（要v2.1.195以降、Claude Platform on AWS上流はv2.1.198+）。

- https://code.claude.com/docs/en/changelog
- https://code.claude.com/docs/en/claude-apps-gateway
- https://claude.com/blog/introducing-the-claude-apps-gateway
- https://www.theregister.com/ai-and-ml/2026/07/01/anthropic-is-removing-its-covert-code-for-catching-chinese-competitors/5265366

### 4. Cursorに重大RCE脆弱性「DuneSlide」開示（CVSS 9.8）

**事実** Cato AI LabsがCursorの脆弱性2件（CVE-2026-50548 / CVE-2026-50549、いずれもCVSS 3.1で9.8）を開示。間接プロンプトインジェクション→サンドボックス脱出→開発者マシン上でのコマンド実行（RCE）が可能と判明した。

**根拠** 攻撃経路はMCP接続先やWeb検索が返すページに仕込まれた指示文（ユーザーは直接タイプしない）。50548は`run_terminal_cmd`のworking_directoryを非既定パスにすると無検証で書き込み許可に追加される点を悪用しサンドボックスヘルパー自体を上書き。50549はシンボリックリンク解決失敗時のフォールバックでin-projectパスを信用してしまう欠陥。Cursor 3.0（4/2）で修正済み、3.0未満は全バージョン影響。実攻撃の確認はなく研究開示。

**影響** MCP連携やWeb検索結果を介した間接プロンプトインジェクションがサンドボックス脱出・RCEに直結し得ることを実証した事例。同時期にDevinもSecurity Swarm（脆弱性発見・実行時実証・自動修正）を提供開始しており、AI開発ツールのセキュリティが攻守両面で前面に出た週となった。

**行動指針** 組織導入のCursorは3.0以上への更新有無を即時確認。MCP/Web検索結果を扱う他のAIコーディングツールについても、間接プロンプトインジェクション対策（サンドボックス境界の検証強化）を点検することを推奨。

- https://thehackernews.com/2026/07/critical-cursor-flaws-could-let-prompt.html
- https://www.prnewswire.com/news-releases/cognition-launches-devin-security-swarm-to-tackle-the-vulnerability-backlog-302814800.html

### 5. AI「導入体制」競争とインフラ資金流入の加速

**事実** Microsoftが$2.5Bを投じ「Frontier Company」を設立（7/2）、6,000人の業界・エンジニアリング専門家を顧客先に常駐させ本番導入まで伴走する専業オペレーティング会社を新設。AWSも2日前に$1Bの社内AI導入組織を発表済み。並行してデータセンター新興Crusoeが$3B調達交渉で評価額を約3倍（~$30B）に、Menlo Venturesが自社最大の$3Bファンドを組成、データセンター事業者Switchがa16z主導で$2B調達に着手（評価額~$50B）。

**根拠** Microsoft Frontier Companyのトップは元Microsoft Asia社長Rodrigo Kede Lima。顧客の独自データ/IPを他社モデル学習に使わない原則を明示。OpenAI・Anthropicも同種JV設立済みで大手が横並びで実装専業部隊に投資している。国内でもLayerX・ラクス・Sansan・freee・メルカリのAI責任者がトークンコストを人件費と並べて管理する実態が可視化されている（ITmedia、6/30）。

**影響** モデル性能競争から「導入を成功させる体制」へ競争軸が移行。効率シフト（token節約）潮流の裏で、計算基盤・実装体制への資本投下はむしろ加速している構図が浮き彫りになった。

**行動指針** コンサル提案では「トークンマネジメント/コスト可視化」訴求の材料として国内事例を活用できる。大手ベンダーの実装専業部隊とのパートナーシップ機会を評価しておくことを推奨。

- https://www.cnbc.com/2026/07/02/microsoft-commits-2point5-billion-6000-employees-ai-implementation-unit.html
- https://www.bloomberg.com/news/articles/2026-07-02/crusoe-in-talks-to-raise-3-billion-in-round-that-may-triple-firm-s-value
- https://menlovc.com/perspective/menlo-turns-50-and-announces-3b-in-fresh-capital-to-go-all-in-on-ai/
- https://www.bloomberg.com/news/articles/2026-07-02/data-center-firm-switch-seeks-2-billion-in-funding-round
- https://news.infoseek.co.jp/amp/article/itmedia_news_20260630027/

---

## Fable 5 / Mythos 5 停止から復帰までの週内経緯 — [master][copilot][industry]

| 日付 | 出来事 |
|---|---|
| 6/29（18日目） | 停止継続。Axios「今週中復旧」観測が浮上するも正式日程・条件は未確定 |
| 6/30（19日目） | 停止継続。Pentagon・NSAの最終署名待ちで足踏み。Anthropic公式Xも新規進展なしを確認するのみ |
| 7/1（20日目→復帰当日） | 米商務省が6/30付で輸出規制を解除、7/1 15:31 ETにFable 5がグローバル復帰。復帰当日午前時点では[master][copilot]とも「停止継続」の速報が先行し、確認は7/2にずれ込んだ |
| 7/2 | 復帰を全リポで確認。7/7まで週次利用上限50%込み、以降usage credits（$10/$50 per Mtok）。業界横断jailbreak深刻度フレームワークをAnthropicが提案 |
| 7/3〜7/5 | 新規進展なし。7/7の従量課金切替に向けた注意喚起が継続 |

---

## Claude / Anthropic アップデート — [master][copilot]

- **Claude Code v2.1.196〜v2.1.201**: 組織既定モデル設定、`claude mcp list`/`get`の自己承認MCPサーバ起動防止、Claude in Chrome GA、バックグラウンドエージェントの自律push/draft PR化、デフォルト権限モード"Manual"化、AskUserQuestion自動継続廃止、Sonnet 5セッションでのharness reminder調整
- **Claude apps gateway 新設**: セルフホスト型・社内IdP（OIDC）SSO、上流資格情報の自社インフラ封じ込め、IdPグループ単位のモデルallowlist、OTLPテレメトリ送出、spend上限設定。SAML/LDAP非対応・Windows非対応
- **Anthropic Enterprise強化**: 管理者向けリッチな利用分析、モデル単位entitlement制御、spendアラート追加
- **Anthropic × Samsung**: カスタムAIチップ製造で予備協議（2nmファウンドリ、OpenAI元チップ責任者Clive Chan採用）。用途・性能は未確定、AWS Trainium/Google TPU/Nvidia GPUは中核維持
- **steganographyマーカー削除**: 3月に仕込んでいた競合検出用隠しコードを7/1に撤去（The Register報道）

---

## OpenAI / GPT-5.6 動向 — [master][industry]

- Sol/Terra/Luna は約20組織への限定プレビュー継続、一般提供は「数週間内」観測（7/10-17レンジ）。価格 Sol $5/$30・Terra $2.5/$15・Luna $1/$6 per Mtok
- Sol は7月にCerebras上で最大750 tokens/秒のレーンを提供予定（$20B Cerebras推論契約に付随）。Terminal-Bench 2.1で91.9%、内部CTFで96.7%を記録しPreparedness「High」分類を越えたことがガバナンスゲートの根拠に
- Codex CLI は保守リリース中心（0.142.4〜0.142.5）、0.143.0-alpha系がalpha開発中
- GPT-4.5は8/26に完全廃止予定

## Google / Gemini 3.5 Pro — [master][industry]

- 6/30の「6月内公開」期限を逃し正式に7月へスリップ。Vertex AI限定Enterprise previewのみでGA日未定。理由はトークン効率・コーディング・長タスク性能のrefine
- Gemini中核研究者4名（Shazeer/Jumper/Adler/Pritzel）のAnthropic流出が続く一方、[master]は7/4付でNoam ShazeerがOpenAIへ移籍との報道も記録（研究者の移籍先情報にリポ間でズレあり、下記改善メモ参照）

## GitHub Copilot / VS Code — [master][copilot]

- CLI安定版がv1.0.66→v1.0.68まで進展: Claude Sonnet 5対応、kimi-k2.7-code対応、自動モデル選択、GitHub Actions内でPAT不要化（組み込み`GITHUB_TOKEN`）
- VS Code Browser tools GA（7/1、実ブラウザ操作）、Copilot Vision GA（画像・PDF添付、全プラン既定有効）
- GitHub Desktop 3.6: Copilotがコミットメッセージ生成・マージコンフリクト解消を担当。Git worktree対応

## Devin / Cognition — [master][copilot]

- **Devin Security Swarm 提供開始（7/1）**: 脆弱性の発見・実行時実証（隔離サンドボックスで再現）・自動修正PR起票まで。実世界50件ベンチで36件検出（テスト対象中最多）
- Classic環境設定が6/30廃止→declarative blueprintsへ移行（read-only参照は7/31まで）。Cascadeは7/1 EOL（Devin Localへ移行）
- Fable 5復帰を受けDevin Fusionユーザー向けに再展開を予定

## xAI / Grok — [master]

- Grok Voice Agent Builderがno-codeで一般提供（7/1、$0.05/分）。開発者向けだったVoice Agentを非技術者に開放
- 旗艦Grok 5（噂6T MoE、Colossus 2訓練）は週内未出荷

## Microsoft 365 Copilot / Copilot Studio — [copilot]

- **7/1にM365価格改定発効**: E3 $36→$39、E5 $57→$61、Copilot Business $18→$21。恒久バンドル新設（Business Standard with Copilot $23.50、Business Premium with Copilot $32）
- **Copilot Studio基盤 2026.6.2→2026.6.3（6/30）**: エージェントIDの破壊的変更（顧客指定ID識別子を不受理）、GPT-5 Mini fine-tunedモデルを既定有効化、Power Platform API新エンドポイント追加
- **新Copilot Studioが全世界Public Preview**（6/17発表を7/2に回収）: agentic orchestrator刷新、設定タブ9→4削減、GitHub Copilot/Claude Codeのスキルを取り込み可能
- **Copilot Cowork**: 6/16 GA、7/1から従量課金（Copilot Credits）開始。プラグイン発表（S&P Global/LSEG/Box/Harvey/monday.com等）。GA告知イベントは7/21予定
- **M365 Copilot「July 01」Release Notesバッチ**（7/5に回収）: AI生成コンテンツの透かしポリシー（video/audio対象、画像は対象外）、生成ファイルの秘密度ラベル自動継承、エージェントへのスケジュール実行（Power Automate依存脱却）、Outlook Copilot Chatの推論範囲が受信トレイ全体に拡大

## 市場・資金調達 — [industry]

- STARTRADERがOpenAI/Anthropicのプレ IPO CFD取引「OPENAIUSD」「ANTHUSD」を開始（6/29）
- Baseten $1.5B Series F、Nexthop AI $500M Series B、Yann LeCun共同創業のAdvanced Machine Intelligence $1.03Bシード（欧州スタートアップ史上最大のシード）
- Qualcomm、Modularを約$39億で買収（Nvidia CUDAロックイン対抗、Mojo言語+MAX推論エンジン）
- Linux Foundationが「Agent Name Service」立ち上げ意向を表明（DNS由来のエージェント検証済みID標準化）

---

## 来週の注目予定

- **7/7**: Fable 5 週次利用上限50%込みの制限が解除→usage credits（$10/$50 per Mtok）へ移行 / Copilot Studio 次ビルド見込み
- **7/8**: Anthropic 政府発行ID・生体情報検証ポリシー施行
- **7/14**: 破壊的変更 — Visio → Power Automate エクスポート機能廃止
- **7/15**: Claude Science（AI for Science）応募締切
- **7/17**: Claude Corps 第1期応募締切
- **7/10〜7/17**: GPT-5.6 一般提供観測レンジ / Gemini 3.5 Pro GA観測（7月中旬）
- **7/21**: Copilot Cowork GA 告知イベント
- **7/23**: OpenAI computer-use-preview シャットダウン
- **7/31**: Devin classic 環境設定の read-only 参照終了
- **7月中旬〜下旬**: 2026 Release Wave 2 計画ページ公開見込み
- **7月下旬〜8月**: M365 Copilot サービスプラン挙動変更（Premium/Basicのアクセス制御がサービスプラン主導に）
- **8/1**: covered frontier model フレームワーク60日 EO 期限
- **8/3**: 旧「Claude in Slack」アプリ退役
- **8/5**: Opus 4.1 Claude API 退役
- **8/26**: OpenAI Assistants API 廃止 / o3 退役 / GPT-4.5 完全廃止
- **8/31**: Sonnet 5 促進価格終了（$2/$10 → $3/$15）
- **9月**: iOS 27 / macOS 27 GA（AFM 3 本番）

---

## 改善メモ

- **[industry] ローカルクローンのmain停滞問題が再発継続**: 6/15以降ほぼ毎回記録されている、起動時にローカルcloneが古いmainで停滞する事象。今週も`claude/wizardly-davinci-0plqvc`ブランチ上での運用で回避したと記録あり。SessionStartフックでの`git fetch && git reset --hard origin/main`相当の自動化を改めて推奨
- **[copilot] RSS 403の復旧・再発が継続**: mc.merill.net / Tech Community board / Qiita / devblogs.microsoftが7/2に一斉復旧後、7/4〜7/5に再び断続403。WebSearchフォールバックで対応継続。B-005（Qiita取得方法のWebSearch優先化提案、4回目）は「復旧と再発を繰り返すため提案の価値は残る」と再確認
- **[industry] 全RSS/WebFetchが週を通じて403継続**: WebSearchで全件代替。B-004（`daily-sources.md`取得方法欄のWebSearch優先化提案）は今週で6回目の継続記録
- **Fable 5復帰の速報タイミングにリポ間でズレ**: 7/1時点で[master][copilot]は「Pentagon/NSA署名待ちで停止継続」と記録したが、[industry]は同日中に商務省解除・グローバル復帰の一次情報を捕捉していた。内容自体に矛盾はなく、確認の速報性の差として記録
- **[copilot] 重要リリースの取りこぼしが判明**: 新Copilot Studio発表（6/17）・Copilot Cowork GA（6/16）を7/2の「全ソースフル巡回」まで回収できていなかった。カバレッジ自己チェック（B-008）を初回実施し取りこぼしを回収。同様に[master]でもClaude Code v2.1.199/200を7/3時点で「新規なし」と誤記録し7/4に回収する事例があった
- **Gemini研究者の移籍先情報にリポ間で表記のブレ**: [master]（7/4付）はNoam ShazeerのOpenAI移籍を記録する一方、他リポは6/26既報の「Shazeer/Jumper/Adler/PritzelのAnthropic流出」を継続参照するのみで、移籍方向の記述に整合を要確認
