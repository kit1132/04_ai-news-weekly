# AI ニュース週次サマリー — 2026-W25（2026-06-15 〜 2026-06-21）

> 入力: 取得成功 21 / 21
> 生成日時: 2026-06-21（JST）

## 今週のハイライト

### 1. Fable 5 / Mythos 5 世界停止 10 日目 — Amazon 通報が発端、Anthropic 幹部が DC で直接交渉

**事実** 6/12 の米商務省（BIS）指令から 10 日目の 6/21 時点でも Fable 5 / Mythos 5 は全顧客で停止中。Anthropic は Opus 4.8 への自動ルーティングを継続。6/21、Anthropic 上級技術スタッフをワシントンへ派遣し Commerce 担当者と対面交渉を開始。6/20 に Fable 5 課金分（6/9-14）の返金期限が到来。

**根拠** Fortune（6/14）報道で Amazon 研究者が Mythos の安全機構をジェイルブレイクで突破し Andy Jassy CEO が直接米当局へ通報したことが発端と判明。David Sacks（Trump AI 顧問）は「脆弱性パッチ後できるだけ早期に規制解除したい」（G7、6/18）。Anthropic は「ジェイルブレイクは narrow・既知・競合モデルにも存在」と公然と異議。予測市場（Kalshi / Polymarket）は US 顧客向け復旧を 7/1 までに 57%、7/17 までに 75% と織り込む。

**影響** Trump 政権が英国の免除要請を拒否→英 MPs が批判。EU・フランス・インド・英国が AI 主権懸念を表明。G7 エビアン・サミット（6/15-17）で Altman・Hassabis・Amodei が史上初めて共同登壇し「AI・サイバーセキュリティ宣言」を採択。6/22 の Fable 5 試食期間終了・6/23 の usage credits 必要化は停止解除まで実質保留。

**行動指針** Opus 4.8 をデフォルトとした設計・テストを継続。6/22-23 のマイルストーンは停止解除まで確定しないため実際の対応は公式発表を待つ。Anthropic 公式・大手メディア・予測市場の日次クロスチェックを継続。

- https://fortune.com/2026/06/14/how-a-warning-from-amazon-led-the-white-house-to-shut-down-anthropics-mythos-model/
- https://www.androidauthority.com/anthropic-fable-5-ai-models-optimistic-return-3679377/
- https://news.kalshi.com/p/fable-5-odds-anthropic-access-restored-july-57-percent

### 2. Anthropic ソウルオフィス開設 + 韓国大手一斉 Claude 導入 — IPO 前の APAC 拡大戦略

**事実** 6/17-18、Anthropic が東京・ベンガルールに次ぐ APAC 3 拠点目としてソウルオフィスを正式開設（責任者 KiYoung Choi）。NAVER（全エンジニア組織に Claude Code）、Samsung SDS（Samsung Electronics 全体）、LG CNS（LG Group 全体）、Nexon（ライブサービスゲーム開発）、Hanwha Solutions（AWS Bedrock 経由）、Channel Corp（23 万超事業者）が同時に Claude 導入を発表。

**根拠** 韓国 MSIT と AI 安全性 MOU を締結。国家 AI 研究ラボ NAIRL（KAIST / 高麗大 / 延世大 / POSTECH）の研究者最大 60 名に Claude を提供（alignment / robustness 研究）。Anthropic は 6/1 に IPO 予備目論見書提出済み（trillion-dollar 規模観測）。John Jumper（AlphaFold 主導、Nobel 賞）が Google DeepMind から転籍し研究力を強化。

**影響** 米輸出規制下での「AI 主権」を意識したアジア事業拡大。韓国の主力企業を一挙に取り込みシェアを確立。Claude Corps（1,000 名の若手をNPO配置、$85K + $10K グラント）と並んで IPO に向けたエコシステム形成が加速。

**行動指針** Claude Code の組織全体展開事例として NAVER・Samsung SDS の導入規模を参照。IPO 後の pricing / tier 変更リスクに備えた契約条件の確認を推奨。

- https://www.anthropic.com/news/seoul-office-partnerships-korean-ai-ecosystem
- https://www.kedglobal.com/artificial-intelligence/newsView/ked202606180004

### 3. Microsoft Work IQ API GA — KPMG が全世界 27.6 万人に Agent 365 展開

**事実** 6/16 に Work IQ API が GA。A2A・リデザインされたリモート MCP サーバー・REST API エンドポイントで、エージェントが M365 のメール・カレンダー・チャット・ファイル・組織データへ標準アクセス可能。課金は Copilot Credits の従量制（per-user ライセンス不要）。KPMG は Agent 365 を全世界 138 カ国 27.6 万人超へ展開（6/9 発表、今週 catch-up）。

**根拠** Learning Agent（M365 Copilot 内）が役割ベースのスキル開発を業務フローに統合。Agent 365 ガバナンスが Intune + Defender 連携でパブリックプレビュー入り。M365 E5 が 6/1 より新規 Agent 365 購入の必須条件。KPMG は「ガバナンス・監査機能そのものが購買ドライバー」と強調。

**影響** Gartner 予測では 2026 年末までに企業アプリの 40% が AI エージェントを内包（2025 年は 5% 未満）。Work IQ GA はその加速装置。エンタープライズ AI がコスト中心から統治・管理コスト込みの総所有コスト評価に転換しつつある。

**行動指針** 新規 Agent 365 購入は M365 E5 前提を確認。7/1 の E3（$36→$39）/ E5（$57→$61）価格改定前に契約見直しを。

### 4. MCP Enterprise-Managed Authorization stable 化 — Okta ゼロタッチ SSO で組織 MCP 管理が本格化

**事実** 6/18-19、MCP の「Enterprise-Managed Authorization」拡張が stable 化。Okta（初の対応 IdP）の Cross App Access 経由で、IT 管理者が一度プロビジョニングすれば、エンドユーザーは初回ログインだけで接続済み MCP コネクタへゼロタッチ自動接続。対応クライアントは Anthropic（Claude chat / Claude Code / Cowork）+ VS Code。対応コネクタは Asana / Atlassian / Canva / Figma / Granola / Linear / Supabase（Slack 近日対応）。

**根拠** Team / Enterprise プラン向け。個別 OAuth 設定作業を IdP 側に集約し、組織規模での Claude エージェント展開のハードルを下げる構造。

**影響** エンタープライズの「MCP コネクタ棚卸し・権限統制」を IdP に集約する標準パターンが確立。Work IQ GA との組み合わせで「エージェントが社内データに安全にアクセスする」インフラが揃った。

**行動指針** Okta を IdP とする組織は Cross App Access 設定を検討。Slack 対応を待って全社 MCP 統合ロードマップを策定する選択肢も有効。

### 5. Claude Code v2.1.183 auto mode が破壊的 git コマンドをブロック + GPT-5.6 ローンチ目前

**事実（Claude Code）** v2.1.183（6/19 stable）: auto mode でユーザーが明示要求しない限り、`git reset --hard` / `git checkout -- .` / `git clean -fd` / `git stash drop` / `git commit --amend`（エージェント作成コミット以外）/ `terraform destroy` / `pulumi destroy` / `cdk destroy` をブロック。モデル非推奨警告を stderr 出力。`attribution.sessionUrl` 設定でコミット/PR からセッションリンク除去可能。`/config key=value` 構文（v2.1.181 より）でプロンプトから設定即変更。

**事実（GPT-5.6）** OpenAI チーフサイエンティストが GPT-5.5 比「meaningful leap」と表明（6/16）。Polymarket は 6/22-28 のローンチを 83%（出来高 $96 万）で織り込み。明日 6/22 からウィンドウに入る。

**影響** Claude Code の破壊的コマンドブロックはエージェントの作業消失事故を直接防止する安全網。GPT-5.6 が来週デビューすれば Claude / Gemini との能力比較ラウンドが即始まる。

**行動指針** `claude` エージェントを自動化パイプラインに組み込む際、v2.1.183 以降では破壊的操作がブロックされることを前提にテストを更新。GPT-5.6 リリース後はベンチマーク比較の公表を待ち、モデル選定の見直しを検討。

- https://code.claude.com/docs/en/changelog

---

## Fable 5 / Mythos 5 停止：輸出規制と地政学的波紋

### 週内経緯 — [master][copilot]

| 日付 | 出来事 |
|---|---|
| 6/15（Day 3）| 停止継続。Anthropic Agent SDK 課金分離が発効 |
| 6/16（Day 4）| Work IQ API GA。停止継続、復旧日未発表 |
| 6/17（Day 5）| Sacks が「trusted partner のジェイルブレイク発見・当局報告」を公表。UK 免除要請を Trump が拒否 |
| 6/18（Day 6）| G7 エビアン AI 宣言採択。Sacks「パッチ後に規制解除」。Ciauri（ソウル会見）「coming days に非常に自信がある」 |
| 6/19（Day 7）| Fortune 報道: Amazon 研究者→ Jassy 通報が発端と判明。予測市場 57%（7/1）/ 67%（7/10）/ 75%（7/17）。ソウルオフィス開設 |
| 6/20（Day 8）| 停止継続。6/9-14 課金分の返金期限（6/20）到来。MCP Enterprise Auth stable 化 |
| 6/21（Day 10）| Anthropic 上級技術陣を DC へ派遣・対面協議開始。停止継続、確定復旧日なし |

- G7 エビアン（6/15-17）: Altman・Hassabis・Amodei が史上初の共同登壇、「AI・サイバーセキュリティ宣言」採択 — [master][industry]
- EU・フランス・インド・英国が AI 主権懸念・戦略的依存リスクを表明 — [master][copilot][industry]
- ⚠️ [industry]-06-20 digest に「復旧済み（〜6/18）」との記述あり。[master]・[copilot] では 6/21 時点でも未復旧を一貫記録。二次情報源に基づく誤情報の可能性あり、本サマリーは公式 + 予測市場を一次情報として「6/21 時点未復旧」を採用する

---

## Claude / Anthropic アップデート

### Claude Code v2.1.176〜v2.1.183 — [master]

- **v2.1.176（6/15）**: セッションタイトルを会話言語で生成。Fable 停止組織向け Auto モードフォールバック改善
- **v2.1.178（6/15）**: permission rule の引数マッチング構文追加。ネスト skill コンテキストロード。subagent 処理改善
- **v2.1.179（6/18）**: 接続ドロップ修正、WSL2 スクロール修正、JetBrains ターミナル表示修正
- **v2.1.181（6/17 stable）**: `/config key=value` でプロンプトから設定即変更。`sandbox.allowAppleEvents`（macOS Apple Events opt-in）。`CLAUDE_CLIENT_PRESENCE_FILE`（モバイル push 通知抑制）。Bun 1.4 バンドル更新。長段落の行単位ストリーミング。thinking 中 API 切断時 auto-retry。subagent パネル（idle 30 秒で auto-hide・最大 5 行）
- **v2.1.183（6/19 stable）**: auto mode が破壊的 git / IaC コマンドをブロック（→ハイライト参照）。モデル非推奨 stderr 警告。`attribution.sessionUrl` 追加。`/config --help`。subagent spawn 時 400 エラー修正、vim カーソル、Windows Terminal TUI 破損修正
- https://code.claude.com/docs/en/changelog

### Anthropic 課金分離（6/15 発効）— [master][copilot]

- Agent SDK / `claude -p` / Claude Code GitHub Actions / SDK 認証サードパーティアプリが通常サブスク枠から分離
- Pro $20/mo・Max 20x $200/mo のクレジット枠を消費（API 標準レート）、枠枯渇後はオーバーフロー課金を手動有効化しない限り停止（繰越なし）
- 開発者コミュニティ: 「事実上の値上げ」と反発
- 対話利用（チャット・ターミナルの Claude Code）は影響なし

### MCP Enterprise-Managed Authorization（stable）— [master]

- Okta（初の対応 IdP）Cross App Access 経由でゼロタッチ SSO
- Claude chat / Claude Code / Cowork + VS Code が対応クライアント
- コネクタ: Asana / Atlassian / Canva / Figma / Granola / Linear / Supabase（Slack 近日）
- Team / Enterprise プラン向け

### Anthropic IPO / 人材動向 — [master][industry]

- 6/1 に IPO 予備目論見書提出済み、trillion-dollar 規模デビュー観測
- John Jumper（AlphaFold 主導、Nobel 賞）が Google DeepMind から Anthropic へ転籍
- Claude Corps: 1,000 名の若手プロを NPO に配置（$85K + $10K グラント + Claude トークン予算、12 ヶ月）

---

## Microsoft / Copilot アップデート

### Work IQ API GA（6/16）— [copilot]

- A2A / リデザインされたリモート MCP サーバー / REST API の 3 方式でエージェントが M365 データにアクセス
- 課金: Copilot Credits（クエリコスト変動 + アクション/ツールコスト固定、per-user ライセンス不要）
- Learning Agent（M365 Copilot 内）: 役割ベースのスキル開発を業務フローに統合
- Agent 365 ガバナンス: Intune + Defender でポリシー制御（パブリックプレビュー）
- 新規 Agent 365 購入は 6/1 より M365 E5 必須

### KPMG の大規模 Agent 365 展開（6/9 発表 catch-up）— [industry]

- 全世界 138 カ国 27.6 万人超に Microsoft Agent 365 + M365 Copilot を展開
- 購買ドライバーは「エージェント管理・監査機能そのもの」—単一アシスタントではなくガバナンスと監査が主役
- Audit / Tax / Advisory / クライアントサポートに横断適用

### M365 Copilot / Copilot Studio — [copilot]

- Copilot in SharePoint がオプトインからオプトアウトに移行（6 月中旬ロールアウト）—テナント/サイト単位でオフ可。意図せぬ AI 機能露出を避けたい組織は事前ガバナンス確認を
- 6/30: Copilot Studio Teams クラシック作成終了・感度ラベル GA
- 7/1: M365 価格改定（E3 $36→$39、E5 $57→$61、Copilot Business $18→$21）

---

## OpenAI アップデート

### ChatGPT Scheduled Tasks 専用ページ（6/17）— [master]

- サイドバーに「Scheduled」ページを新設、一覧・次回実行時刻・pause/resume/edit/delete を一元管理
- 監視タスク: Web 検索・接続アプリの変化を検知し「報告すべき変化がある時だけ通知」
- Pulse を sunset し proactive update を Scheduled Tasks に統合（Pro は 14 日間移行期間）
- タスクは最低 1 時間に 1 回実行、放置タスクは auto-pause
- https://9to5mac.com/2026/06/17/openai-launches-scheduled-tasks-in-chatgpt-details-here/

### ChatGPT リリースノート（6/19）+ Codex アップデート — [master]

- 発音ヘルプ: 60 以上の言語で音声 + テキスト両方で会話内提示
- World Cup 対応・iOS 写真アップロード高速化
- Android（有料プラン）: 送信ボタン長押しで 1 回だけのモデル選択。コンポーザに inline mentions、Plugins メニュー刷新
- **Codex（macOS）Record & Replay**: 実演ワークフロー → 再利用可能 skill（`.SKILL.md`）に変換。変数入力（日付・ファイル名等）で自動実行—RPA の代替用途
- Codex: 一括アクション（bulk actions）、thread handoff（ローカル ⇄ リモートホスト）、SSH ディープリンク改善、Browser Use セッション永続化
- Role-specific plugins for ChatGPT Business（Sales / Data Analytics / Product Design / Creative Production / Investment Banking / Public Equity Investing）
- EEA / UK / スイスで Computer Use（macOS / Windows）・Chrome 拡張・Memories・Chronicle を解禁
- https://help.openai.com/en/articles/6825453-chatgpt-release-notes

### OpenAI Partner Network / GPT-5.6 / GPT-4.5 退役 — [master][industry]

- Partner Network: $150M 投資、年末までに 30 万人の認定コンサルタント（BCG / Accenture / Bain がローンチパートナー）—モデル競争からの実装・運用シフト
- GPT-5.6: チーフサイエンティストが「GPT-5.5 比 meaningful leap」と表明（6/16）。Polymarket が 6/22-28 ローンチに 83%（出来高 $96 万）を織り込み
- GPT-4.5: 6/27 に ChatGPT から退役
- OpenAI はトークン価格引き下げを検討中（Anthropic の競合圧力に対抗）— [industry]

---

## Google / Gemini アップデート

### Gemini CLI → Antigravity CLI 移行（6/18 実施）— [master][industry]

- 消費者向け（Google AI Pro/Ultra/無料 / Gemini Code Assist 個人版 / GitHub 統合）が 6/18 からリクエスト停止
- 代替は Antigravity CLI（クローズドソース Go 製、OSS 非公開）—開発者コミュニティから反発
- エンタープライズ（Gemini Code Assist Standard/Enterprise・有料 API キー）は Gemini CLI を継続利用可
- マルチエージェント・オーケストレーション前提設計へ移行
- https://ostechnix.com/google-is-replacing-gemini-cli-with-google-antigravity/

### Gemini モデル動向 — [master][industry]

- **Gemini 3.5 Flash**: 機能管理トグル廃止（6/16）→ 全リージョンで常時有効化（always-on default）
- **Gemini 3.5 Pro**: 6/21 時点も限定 Vertex AI プレビューのみ。GA 未定（Pichai「来月まで待って」）。2M コンテキスト / Deep Think
- **Gemini 画像プレビュー**: gemini-3.1-flash-image-preview / gemini-3-pro-image-preview が 6/25 廃止

---

## 開発ツール

### Cursor v3.8（6/18）— [master]

- `/automate` skill 追加: 自然言語からトリガー・指示・ツールを自動構成
- GitHub / Slack 向け新トリガー（Slack は指定絵文字リアクションで automation を起動）
- Computer use 対応
- Cloud agents: 専用 VM での並列実行 + 再利用 snapshot、セットアップ 10 分以内
- Design Mode: UI 要素を直接選択・注釈してエージェント編集を誘導
- SDK: auto-review / nested subagents / run correlation ID
- https://cursor.com/changelog

### Google Deployment Simulation（6/16 公開）— [industry]

- 過去の会話ログを新候補モデルでリプレイし、リリース前に挙動を検証する手法
- モデル更新時のリグレッション検知に有用（要一次資料での裏取り）

---

## 業界動向・市場

### 資金調達・人材移動 — [industry]

- **Prometheus（Jeff Bezos 物理 AI）**: $12B の追加調達、評価額 $41B。ジェット・エンジン〜創薬のエンドツーエンド設計・製造（Vik Bajaj / Verily 共同創業者が主導）
- **John Jumper**: AlphaFold 主導・Nobel 賞受賞者が Google DeepMind（約 9 年）→ Anthropic へ転籍
- **DeepSeek**: 6 月エンタープライズトレンドベンダー首位—コスト最適化優先へのシフトを示唆

### AI 信頼性とユーザー乖離 — [industry]

- **Pew Research（2026 年 6 月）**: 米国成人の 49% が AI チャットボット利用。一方「AI が社会的利益をもたらす」と信じるのはわずか 16%
- 「採用は声高、信頼は静か」—ガバナンス・社会的影響への懸念が長期的な成長障壁に

### 市場シェア・インフラ — [master][industry]

- **Similarweb AIトラッカー（2026 年 4 月）**: ChatGPT 54.7% / Gemini 27.4% / Claude 8.2% / DeepSeek 4.1% / Grok 2.8%
- **クラウドインフラ Q1 2026**: 四半期売上 $1,290 億（前年比 +35%）。AWS 28% / Azure 21% / GCP 14%
- **Gartner 予測**: 2026 年末までに企業アプリの 40% が AI エージェントを内包（2025 年は 5% 未満）
- **日本市場（MM 総研 2025 年 8 月）**: 生成AI 個人利用率 21.8%、市場規模 1,679 億円（2024）→ 5,618 億円（2030）予測

---

## 来週の注目予定

- **6/22（明日）**: Fable 5 試食期間終了（停止中のため実質日程は停止解除まで保留）/ OpenAI GPT-5.6 ローンチ予測ウィンドウ開始（〜6/28、Polymarket 83%）
- **6/23**: Fable 5 利用に usage credits 必要化（停止中のため要再確認）
- **6/25**: gemini-3.1-flash-image-preview / gemini-3-pro-image-preview 廃止
- **6/27**: GPT-4.5 が ChatGPT から退役
- **6/30**: Devin クラシック環境セットアップ廃止 / GPT-5.2・GPT-5.3-Codex 新規 API リクエスト不可化 / Copilot Studio Teams クラシック作成終了・感度ラベル GA / Security Copilot E5 展開完了 / M365 価格ロックイン期限
- **〜7/1（予測・未確定）**: Fable 5 / Mythos 5 US 顧客向け復旧（市場本命 57%）/ Claude Partner Network 初回階層昇格レビュー / Devin Cascade 完全廃止
- **7/1**: M365 価格改定発効（E3 $36→$39、E5 $57→$61、Copilot Business $18→$21）/ Cursor 新価格
- **7/10 / 7/17**: Fable 5 復旧予測の中間マイルストーン（67% / 75%）
- **7/17**: Claude Corps 第 1 期応募締切
- **8/5**: Claude Opus 4.1 が Claude API から退役
- **8/26**: OpenAI Assistants API 廃止 / o3 退役

---

## 改善メモ

- **[master] ローカル main 乖離問題（3 週連続発生）**: origin/main と共通祖先を持たないまま digest 生成を開始する事故が 6/19・6/20・6/21 と 3 日連続。`git reset --hard origin/main` で復旧後に生成。**SessionStart hook に `git fetch origin main && git reset --hard origin/main` を追加することを強く推奨**—CLAUDE.md の「main 直 push」ルールだけでは初期乖離を防げない（本提案は 3 回目の記録、hook への恒久化を要請）
- **[copilot][industry] RSS フィード全滅が常態化**: GIGAZINE / The Decoder / VentureBeat / hnrss.org 等が全 403。WebSearch + major media のフォールバック運用を継続中。`daily-sources.md` の取得方法欄を「WebSearch 優先」に変更することを推奨
- **Anthropic 公式（anthropic.com/news）**: 全週を通じて WebFetch が 403。WebSearch + Korea JoongAng Daily / Fortune / Android Authority 等で代替（安定）
- **Claude Code Changelog（WebFetch）**: 全週を通じて安定。v2.1.183 が最新を確認済み（6/21 時点）
- **[industry] 03 リポ 6/20 digest で「Fable 5 復旧済み（〜6/18）」との記述を検出**: [master]・[copilot] では 6/21 時点でも未復旧を一貫記録。二次情報源に基づく誤情報の可能性が高く、本サマリーは公式 + 予測市場を一次として「6/21 時点未復旧」を採用。両論として上記「週内経緯」セクションに記録済み
- **Fable 5 / Mythos 5 停止情報の精度**: 「48 時間で復旧」報道は Anthropic 非公式 X アカウントが発端で誤情報として除外。公式 + 大手メディア + 予測市場のクロスチェック体制を継続
