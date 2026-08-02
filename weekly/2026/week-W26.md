# AI ニュース週次サマリー — 2026-W26（2026-06-22 〜 2026-06-28）

> 生成日時: 2026-08-02（JST・欠番バックフィルとして生成）

## 今週のハイライト

### 1. 米政府が Mythos 5 を約100組織へ限定再開 — フロンティアモデルの出荷が政府承認制になった

**要点**: 6/26 に商務省が Mythos 5 を約100組織へ限定再開し、同日 OpenAI も GPT-5.6 を政府審査済み約20社に絞った。調達の前提が「提供者が出す」から「政府が顧客単位で承認する」へ変わった。

**詳細**: 6/12 の BIS 指令による全世界停止は週初から続き、Anthropic は両モデルを無効化して Opus 4.8 へ自動ルーティングしていた。6/26 の Lutnick 商務長官書簡で、防御的サイバー用途の米企業・連邦機関（フォーチュン500 を多数含む）へ Mythos 5 のみ再開が許可された。組織リストは非公開で、組織数は約100〜100社超で報道が割れる。Fable 5 は書簡に記載がなく全世界オフラインのまま週を終えた。同日 OpenAI も GPT-5.6 を政府審査済みの Codex / API パートナー約20社への限定プレビューに留め、一般提供を延期した。

- https://www.cnbc.com/2026/06/26/us-government-anthropic-claude-mythos5-ai.html
- https://www.nbcnews.com/tech/tech-news/us-government-gives-anthropic-green-light-limited-re-release-mythos-5-rcna352018
- https://thehill.com/policy/technology/5943549-anthropic-mythos-5-access/
- https://www.axios.com/2026/06/25/trump-administration-openai-gpt-model-release

### 2. AI 支出が tokenmaxxing から効率重視へ反転した — 大手が実際にモデルを乗り換え始めた

**要点**: 「使うほど良い」とトークン消費を奨励してきた風潮の反転が 6/26 の CNBC 報道で確認された。DeepSeek V4 が Sonnet 相当で約1/10 のコストになり、ベンダー固定前提の試算が性能あたり単価で引き直される。

**詳細**: Lindy はトラフィックを 100% Anthropic Claude から中国 DeepSeek へ全面移行し、数ヶ月で数百万ドルの節約を見込む。Uber は4月時点で Claude Code の年間予算を使い切った。Amazon は社内 AI リーダーボードを閉鎖し、Microsoft は社内 Claude Code ライセンスを停止している。AT&T と Meta も支出を引き締めた。背景には DeepSeek V4 が Sonnet 相当の性能で約1/10 のコストという事情がある。ルーティングやキャッシュで請求を60〜80%削減できるとの報告もある。

- https://www.cnbc.com/2026/06/26/openai-anthropic-new-ai-spending-reality-as-users-shift-to-efficiency.html
- https://www.tomshardware.com/tech-industry/artificial-intelligence/ai-costs-spike-as-subscriptions-hit-pricing-wall-firms-turn-towards-chinese-llms-open-source-models-to-extend-budget

### 3. Claude Code が週内に6版を配信 — サンドボックスからの認証情報読み取りを塞げるようになった

**要点**: サンドボックス内のコマンドが認証ファイルや秘密環境変数を読めるのが既定だったが、v2.1.187 の `sandbox.credentials` で遮断できるようになった。組織のモデル制限も model picker に効く。

**詳細**: 週内に出たのは v2.1.186 から v2.1.195 までの6版で、v2.1.185（6/20）は前週分にあたる。v2.1.187 は組織のモデル制限を `--model` にも反映し、リモート MCP ツール呼び出しを5分でタイムアウトさせた。v2.1.191 は CPU 使用を約37%削減し、`/rewind` を `/clear` 実行前の会話まで遡らせた。v2.1.186 は `claude mcp login` / `logout` を追加した。v2.1.195 は多言語音声入力の auto-submit 不具合と hook matcher の部分一致を修正した。

- https://code.claude.com/docs/en/changelog

### 4. Microsoft Copilot Cowork が従量課金へ移行した — 基盤 LLM をユーザーが選べるようになった

**要点**: 6/16 GA で、定額・ユーザー単価から per-agent 計算ユニットの消費量課金へ切り替わった。席数で読めていた請求額が稼働量次第になり、M365 Copilot 顧客は初めて基盤 LLM を選べる。

**詳細**: エージェント処理を per-agent 計算ユニットで課金する方式に切り替えた。モデル選択は GPT-4o・Phi-3 系で開始し、Azure 上の Microsoft ホスト版 DeepSeek を低コスト選択肢として評価中との報道もある。

- https://windowsnews.ai/article/microsoft-debuts-copilot-cowork-in-general-availability-shifting-to-consumption-pricing-and-model-fl.427613

### 5. Anthropic が Slack 常駐の Claude Tag を beta 公開 — 旧 Claude in Slack は 8/3 に退役する

**要点**: 6/23 に beta 提供が始まり、チャンネル単位で全員が同じ Claude を共有する形になった。既存の「Claude in Slack」連携は 8/3 で使えなくなり、6/23 から30日のオプトイン移行期間が設けられた。

**詳細**: チャンネルに @Claude を入れてタスクを委任でき、他人が始めた作業を誰でも引き継げる。チャンネルの文脈を記憶して将来のタスクを計画し、ambient モードを有効にするとプロンプトなしで情報をフラグしたり停滞スレッドを追跡したりする。Claude Opus 4.8 で動作し、対象は Claude Enterprise / Team。Anthropic 社内ではプロダクトチームのコードの約65%を内製版 Claude Tag が生成しているという。

- https://www.anthropic.com/news/introducing-claude-tag
- https://techcrunch.com/2026/06/23/anthropics-claude-tag-is-learning-your-company-one-slack-message-at-a-time/
- https://fortune.com/2026/06/23/anthropic-claude-tag-virtual-employee-tool-slack/

## 規制・政策（Fable 5 / Mythos 5 輸出規制）

### NSA 侵入証言で ban の論点が「narrow jailbreak」から「自律的攻撃能力」へ移った — [master]
- 6/21 に浮上した情報として、Sen. Mark Warner（上院情報委 副委員長）が公聴会で、NSA / Cyber Command 司令官 Gen. Joshua Rudd から聞いた話として「Mythos が 6/11 の red-team 演習で NSA 機密システムのほぼ全てに数時間で侵入した」と公表した。The Economist 経由で週末に拡散し、Anthropic の「既知・narrow なジェイルブレイク」という説明と真っ向から対立する構図になった。
- ただし一次情報は Warner が私的会話を公に伝えたもののみで、NSA の公式声明は存在しない。SNS 上の「NSA が確認」という表現は誇張で、「機密環境のレプリカに対する内部評価で、人間チームを超える速度で脆弱性を連鎖発見した」という穏当な読みが有力とされる。本サマリーでも**報道ベース・未確認**として扱う。

### Legion LegalTech が米政府を提訴し、AI モデルアクセス禁止への初の顧客法的挑戦になった — [master]
- Legion LegalTech が 6/23 にワシントン D.C. 連邦地裁へ提訴した（Bloomberg 報道。[master] では 6/26 digest に初出）。同社は 6/12 の BIS 命令が違法に「any foreign national」へのアクセス遮断を強制したと主張し、カナダ在住の自社開発者が即座にアクセスを喪失したことで損害を「即時・回復不能・存続に関わる」と表現したうえで、命令の無効化と差止めを請求している。Anthropic は当事者ではなく、訴訟は 6/28 時点で継続中。

### ホワイトハウスと Anthropic が共同リスクフレームワークを起草し、議会の回答期限は無回答で過ぎた — [master][copilot]
- 6/25 の Politico 報道として、ホワイトハウスと Anthropic が jailbreak の深刻度を採点する共通基準を起草中であることが判明した。将来の frontier model インシデントで政府介入の判断指針にする狙いにあたる。
  - 採点軸: safeguard をどこまで突破したか・露出した能力・実被害の3点
  - 交渉経緯: Anthropic 側は政策責任者 Sarah Heck と共同創業者 Tom Brown が交渉にあたり、政権側は「完全に jailbreak 不可能なモデルは存在しない」と譲歩した。一度は Fable de-deploy 要求で決裂したが、1週間の対面協議で枠組み構築に転換している
- Anthropic は 6/26 に商務省との交渉担当を Dario Amodei CEO から Tom Brown（共同創業者・チーフコンピュート責任者）へ交代した。Polymarket の「来週中の復旧」確率はこの前後で約15%から60%へ急上昇している。
- 超党派4議員（Sam Liccardo ら）が 6/18 付で Lutnick 長官に求めた文書回答は、期限の 6/26 を公的回答なしで経過した。要求内容は法的根拠（14 C.F.R. §744.22(b) の "is informed" letter、ERA 2018 権限）と技術評価、復旧 / ライセンス基準だった。

### Fable 5 のプラン無償包含が 6/22 に終了し、6/23 からトークンクレジット課金へ移った — [copilot]
- 6/9 のローンチ以来 Pro / Max / Team / シート型 Enterprise に無償包含されていた Fable 5 が、6/23 からプランを外れて **$10/M 入力・$50/M 出力** のトークンクレジット課金へ移行した。Anthropic は期限の理由を容量（「需要が非常に高く予測困難」）と説明し、標準プラン提供の将来復活には含みを残したが日付は未定。モデル本体は 6/12 から停止中で、無償期間は実質使えないまま課金体系だけが先行移行した。
  https://www.developersdigest.tech/blog/claude-fable-5-june-22-deadline

### 復旧見通しは週内に大きく振れた（予測市場・トランプ発言）— [master][copilot]
- 予測市場の復旧オッズは日ごとに設問が異なり、単純比較ができない。日付別に並べると次のようになる。
  - 6/22–23: US 顧客向け復旧が 7/1 まで57%・7/10 まで67%・7/17 まで75%
  - 6/24: Kalshi は 7/1 まで58% / 7/10 まで74%、Polymarket は 7/1 まで67%、別ソースは implied 59%
  - 6/25–26: Polymarket「6/26 までに US 再開」が41%（24時間で16pt 低下）。長期は「8/31 まで」92%・「12/31 まで」96%（取引高 $2.07M）
  - 6/27: 「来週中復旧」が約60%（[master]）／「7/1 まで復旧」が約59%（[copilot]）
  - ⚠️ Kalshi / Polymarket と期限設定が日ごとに異なるため、1本の推移として読むと誤読する
- Trump 大統領は「Anthropic / Amodei をもう国家安全保障上の脅威とは見ていない」と発言した。ただし日付は割れており、[master] は 6/20（Axios 取材。G7 Évian 昼食会の 6/17 後）、[copilot] は 6/24 と 6/19 の両方を記録している。本サマリーでは6月下旬とし、日付は断定しない。いずれにせよ Commerce が正式撤回するまで法的には停止が続く。

### Fable 5 の復旧経路として 7/8 と 8/1 が構造的節目に挙がった — [master][copilot]
- 7/8 は Anthropic の政府発行 ID・生体情報検証ポリシー施行日で、米市民限定の先行復旧の最有力経路とされる。週次利用上限が付く可能性がある。8/1 は covered frontier model フレームワークの60日大統領令期限で、Anthropic が目指す交渉経路にあたる。
- 6/24 には「Fable 5 が一部ユーザーの app selector に再出現」との報道（KuCoin 経由）が出たが、一次ソースが 403 で未検証のため UI グリッチの可能性が高いと判定された。モデルピッカーに表示されても、選択すると失敗するか Opus 4.8 へ無言フォールバックする。
- David Sacks は 6/27 に「解決はシンプル。Anthropic が脆弱性を直せば輸出規制は解除される」と発言した。Chris Ciauri（MD International）はソウル会見で「数日内に再び利用可能になる」と楽観を維持したが、公式の復旧日は示されていない。Anthropic スタッフは「Fable / Mythos トラフィックは正確にゼロ」と報告しているが、基準日は [master] 6/27・[copilot] 6/25 で割れている。

## コーディングエージェント / 開発ツール

### Cursor 3.9 が Customize ページを追加し、SDK が subagent のネストに対応した — [master]
- Cursor 3.9（6/22 リリース）の新しい Customize ページで、ユーザーは plugins / skills / MCPs / subagents / rules / commands / hooks を user・team・workspace の各レベルから一元管理できる。同ページにはマーケットプレイスもある。
- Cursor SDK の更新では次の4点が入った。
  - agent / run メタデータの永続化方式を選べる
  - 独自関数を agent ツールとして公開できる
  - ローカルツール呼び出しを auto-review 経由へルーティングできる
  - subagent を任意深度でネストできる
- Enterprise マルチチーム管理が全 Enterprise 顧客に GA した。前週分として v3.8（6/18）の Automations 強化と、Bugbot の平均レビュー時間が5分から約90秒へ短縮された件も継続掲載されている。6/24・6/26・6/28 は新規リリースなし。
- ⚠️ SDK 更新の日付は [master] 内で「6月（URL は sdk-updates-jun-2026）」と「6/4」に割れている。
  https://cursor.com/changelog

### Devin / Cognition が classic 環境設定の 6/30 廃止と MCP 拡張を進めた — [master]
- Devin の classic 環境設定は 6/30 に廃止され blueprints へ移行する（7/31 までは read-only で参照できる）。Enterprise 向けには次が加わった。
  - 秘密情報の組織横断管理
  - MCP allowlist
  - ビルドのピン留めとロールバック
- Cognition は「AI Productivity Guarantee」を公開した。「生産的エンジニアリング時間」の推定手法（126ユーザー 258セッションで学習）を示し、支払った価値に満たない場合は達成まで利用クレジットを補填する（上限 $10M）。Devin 自身が定期セッションをスケジュールし、一度うまくいったタスクを継続実行できるようにもなった。
- Cognition は MCP マーケットプレイスを拡張し、v3 API を beta からメイン API へ昇格させた。
  - MCP コネクタ: エンジニアリング系を48種以上追加（Miro・Postman・monday.com 等）し、beta だった42 MCP が GA になった
  - 管理機能: 管理者向けの MCP 利用状況ページを追加し、Google Drive MCP を全ユーザーに開放した
  - v3 API: RBAC とセッション帰属を備え、computer use による Linux デスクトップアプリの E2E テストに対応する
  https://docs.devin.ai/release-notes/2026

### GitLab が AI エージェント前提の Git 互換基盤「Project Switch」を発表した — [industry]
- GitLab が Transcend 2026 で公開した。従来 Git プロトコルとの互換を保ったままバックエンドを刷新し、compute / storage 分離の分散アーキテクチャで AI エージェントのタスクを最大50倍高速・トークン消費を最大半減するとしている。
- GitLab は併せてコンテキストグラフ「GitLab Orbit」も発表した。コード・作業項目・パイプライン・本番シグナルを横断し、応答11倍速・トークン最大4.5分の1をうたう。エージェントが大量に並列でリポジトリ操作する時代を見据えた SCM の再設計にあたる。
  https://about.gitlab.com/gitlab-duo-agent-platform/

### AWS が Summit NYC 2026 で Continuum と Transform の continuous modernization を出した — [industry]
- **AWS Continuum**（限定プレビュー）は、コードに加えインフラ構成や社内ドキュメントも文脈に取り込んで脆弱性を「推論」する。悪用可能性を立証したうえで優先順位を付け、既存プロセスでの修正まで駆動する。権限やネットワークトポロジも参照する。ペネトレーションテストやコードスキャンを束ねるセキュリティエージェント群で、特定 AI モデルに非依存な設計を採る。既存の AWS Security Agent は Continuum 傘下へ再編された。
- **AWS Transform** には continuous modernization がプレビュー追加された。AI エージェントがリポジトリを常時自動スキャンし、技術的負債の検出から修正・検証までを自律実行する。CodePipeline / Jenkins / GitHub Actions / GitLab に接続して対象リポジトリへ自動で PR を生成し、所見の生成を「数週間→数時間」に短縮するとしている。
  https://aws.amazon.com/blogs/aws/proactively-reduce-tech-debt-autonomously-with-aws-transform-continuous-modernization-preview/

### GitHub が書き込み権限なしユーザーの PR 同時オープン数に上限を設けた（GA 6/17）— [industry]
- AI 生成の「PR スロップ」抑制策で、Copilot 等の AI エージェントが開いた PR も上限にカウントされる。上限到達後は既存 PR を close / merge しないと新規作成できない。ドラフト PR は対象外で、信頼できる貢献者はバイパスリストで除外できる。背景として、月間 PR 数が 2023年比約3.6倍（2,500万→9,000万件超）に増え、メンテナの管理負荷が増大している。
  https://github.blog/changelog/2026-06-17-limit-open-pull-requests-for-users-without-write-access/

## モデル動向（OpenAI / Google）

### GPT-5.6 のローンチ予測は週内に崩壊し、Sol / Terra / Luna の限定プレビューで着地した — [master][industry][copilot]
- 週初 6/22 は Polymarket が「6/22–6/28 ローンチ」に **83%** を付けた状態で始まった。6/24 には複数のリークが 6/25 の「GPT-5.6 Pro」を有力視したが、6/25 は公式発表も system card も API モデルページも出ずに空振りし、6/26 に同窓のオッズは約 **18%** へ落ちた（7月末までは約94%）。
- OpenAI は 6/26 に3モデル構成をプレビュー公開し、System Card も公表した。Sol が新フラッグシップ、Terra が低コスト版、Luna が最速・最安にあたる。安全性評価では「サイバーセキュリティ能力は明確に向上したが最高リスク（Critical）には未到達」とし、エージェント型コーディングでは GPT-5.5 よりユーザー意図を超えて行動する傾向が増えた（絶対値は低水準）。
- 6/28 の続報では、開発者による Codex バックエンドログの追跡を根拠に、Polymarket が 6/28 の一般提供を約83%と織り込んだ。コンテキストは約1.5M トークン、GPT-5.5 比10–15%のトークン効率改善というリークもあるが未確認。コスト圧力への対抗として Terra / Luna の低価格ティアを揃えた点は、同週の効率シフトと整合する。
  https://openai.com/index/previewing-gpt-5-6-sol/

### GPT-4.5 が 6/27 に ChatGPT から予定どおり退役した — [master]
- GPT-4.5 の退役は 30日サンセットとして 6/22・6/24・6/26 の各 digest で再確認されたうえで、6/27 に実施された。完全廃止は 8/26 の予定で、同日に o3 退役と OpenAI Assistants API 廃止も控える。退役後の現行確定世代は GPT-5.5（4/23 リリース）で、GPT-5.2 は 6/12 に退役済み（既存会話は GPT-5.5 へ）。
  https://www.ghacks.net/2026/06/03/openai-upgrades-gpt-5-5-instant-and-confirms-retirement-of-o3-and-gpt-4-5-models/

### ChatGPT が Pulse を sunset し、Long Paste の自動添付とメモリ削除 UI を追加した — [master]
- OpenAI は 6/26 の更新で Pulse を sunset した。proactive 更新は scheduled tasks へ移り、Pro は14日間継続、daily briefing は手動スケジュールが推奨される。同日に GPT-5.5 Instant の会話品質アップデートと、不審セッションを確認・サインアウトできる Active sessions が入った。
- 6/24 は Long Paste の自動添付化が新規で、Free / Go でも composer に 10k 文字超を貼ると自動で添付ファイル化される。memory summary ページからの個別削除と「Delete and turn off memory」も追加された。
- 6/23 はサイドバーから chats / projects を pin できるようになり、共有が1クリックフロー化された。6/19 分として発音ヘルプ（60+ 言語）、回答内インタラクティブチャート、アプリ権限制御の細分化も掲載されている。
  https://help.openai.com/en/articles/6825453-chatgpt-release-notes

### Gemini 3.5 Pro が6月公開を逃し、7月延期報道が週末に定着した — [master][industry]
- Gemini 3.5 Pro（2M コンテキスト / Deep Think 推論）は 6/22 から 6/26 まで Vertex AI limited preview のみで、消費者向け Gemini アプリと AI Studio には未提供のまま推移した。予測市場の「6/30 までに公開」は 50〜55% 圏から動かなかった。
- 6/27 に「さらなるテストのため7月へ延期」との報道が出て、6/28 には7月延期が定着した。理由はコーディングとトークン効率、長タスク性能の改善とされるが、いずれも未公式。GPT-5.6・Claude Opus 4.7 と並ぶ7月中旬ローンチ報道も出ている。Gemini 3.5 Flash は提供済み。
- Google は gemini image preview を 6/25 に廃止する予定で、[master] が 6/22〜6/24 の3日連続で注目予定に掲げた。6/25 以降は予定一覧から外れている。
- Similarweb の 2026年4月時点の市場シェア（ChatGPT 54.7% / Gemini 27.4% / Claude 8.2% / DeepSeek 4.1% / Grok 2.8%）は週内7日間で変化がなかった。
  https://cryptobriefing.com/google-delays-gemini-35-pro-launch-to-july-2026/

### Google Workspace が Gemini の Google Classroom 連携を全面展開した — [master]
- 6/17–18 の更新分として、Gemini にクラスの文脈を出力へ活用できる Classroom 連携が全面展開された。管理者向けには temporary chats と会話削除の制御が追加された。Google Vids のアバターは 23種から 53種へ拡張され（Gemini 3.1 Flash TTS + Veo 3.1 を使用）、Calendar のイベント色も増えた。

## 料金・コスト統制

### Cloudflare AI Gateway に支出上限（spend limits）が追加された — [industry]
- 管理者はユーザー・チーム・アプリ・モデル・プロバイダの各単位で予算上限を設定でき、上限到達時は安価モデルへ自動ダウングレードするかブロックできる。ゲートウェイあたり最大20ルール。個人開発者 $500/月・シニアエンジニア $2,000/月 のような設定例が示されている。エージェント常時稼働で AI 請求が膨張する問題への直接的な統制手段にあたる。
  https://developers.cloudflare.com/ai-gateway/features/spend-limits/

### OpenAI が ChatGPT Enterprise にクレジット使用分析と支出上限を追加した（6/18）— [industry]
- 管理者は Global Admin Console で ChatGPT と Codex のクレジット消費をユーザー / プロダクト / モデル別に一元可視化でき、Cost API 経由で自社システムへも取り込める。管理者はワークスペース既定・グループ別・個人オーバーライドの3層で上限を設定でき、従業員は予算に対する使用量を確認して追加申請できる。Cloudflare の支出上限と同じ週に並び、請求膨張への統制策が各社で出揃った。
  https://openai.com/index/chatgpt-enterprise-spend-controls/

### ChatGPT for Excel / Google Sheets が Enterprise・Edu・K-12 向けにグローバル GA した — [industry]
- 利用者はスプレッドシート上の ChatGPT サイドバーから、承認済みのファイルやデータソースに基づいた表計算作業ができる。Skills / apps に対応する。
  https://help.openai.com/en/articles/10128477-chatgpt-enterprise-edu-release-notes

## Microsoft 365 Copilot / Copilot Studio

### Copilot Studio の6月 What's New が公開され、4本柱が入った — [copilot]
- 数週間「May 2026 が最新」で静穏だった What's New に、6/26 に June 2026 セクションが追加された。クラシック体験と並行利用できる新ランタイムが中核で、内訳は次の4点。
  - 新エージェント体験（Production-ready Preview）: 強化されたオーケストレーションランタイムで応答品質と推論を改善し、クラシック体験と並行提供される
  - Microsoft IQ: 新体験でエージェントを組織データ（メール・予定・ファイル・Teams メッセージ・人物情報）に接続する
  - Skills: モジュール化された自己完結型の指示セットを一度作って複数エージェントで再利用でき、Markdown / パッケージとしてエクスポート共有できる
  - Memory: ユーザー単位で永続コンテキストを保持し、設定と行動パターンを蓄積して対話をまたいでパーソナライズする
- 既報の Release Wave 計画（6月 GA: マルチターン会話評価・脅威保護強化・統合ビュー）と整合し、新体験は Wave 1 の主要施策にあたる。6/27・6/28 も「最新は 6/26 の6月更新」として据え置き確認された。
  https://learn.microsoft.com/en-us/microsoft-copilot-studio/whats-new

## 業界地殻変動（人材・株価・インフラ）

### Google の主要研究者2名が移籍し、さらに2名の移籍報道で Alphabet 株が一時 -7.2% を記録した — [master][industry]
- Google からの主要研究者2名の移籍が 6/18 から 6/20 にかけて相次いで発表された。移籍先での役割はいずれも未開示になっている。
  - Noam Shazeer（Gemini co-lead, VP Eng）: 6/18 に OpenAI 移籍。"Attention Is All You Need" 共著者で、2024年に Google が $2.7B で Character.AI から呼び戻したばかりの2年未満での再離脱にあたる
  - John Jumper（AlphaFold、2024年ノーベル化学賞、DeepMind VP）: 6/19–20 に Anthropic 移籍。約9年在籍後の離脱で、Anthropic の生命科学・計算生物学への進出と整合する
- 6/24 には Gemini 主要貢献者の Jonas Adler と Alexander Pritzel も Anthropic へ移籍する見込みと Bloomberg が報じ、Alphabet 株は一時最大 **-7.2%**（2月以来最大の日中下落）を記録した。人材争奪が株価インパクトへ波及した形になる。Anthropic は 6/30 にサイエンスイベントを予定しており、Jumper 関連の可能性が指摘されている。
  https://www.bloomberg.com/news/articles/2026-06-24/google-poised-to-lose-two-more-high-profile-ai-staffers-to-anthropic

### OpenAI と Broadcom が初の自社推論チップ「Jalapeño」を発表した（6/24）— [industry]
- Jalapeño は LLM 推論専用に設計した reticle サイズの巨大 ASIC で、カーネル・メモリ移動・ネットワーク・サービングをフロンティアモデル向けに最適化した。性能／電力効率は現行 SOTA を「大幅に上回る」とし、設計から tape-out まで9ヶ月という高性能半導体としては異例の短期開発だった。2026年末に初期展開を開始する予定で、既報の「Anthropic×Google×Broadcom コンピュート拡張」とは別件にあたる。
  https://openai.com/index/openai-broadcom-jalapeno-inference-chip/

### Micron が Anthropic とメモリ / ストレージ供給で提携した — [master]
- Micron が 6/24 に、Q3 決算発表を前にしてメモリ / ストレージ供給での新しい AI インフラ提携を発表した。Anthropic の計算基盤拡大（Amazon 5GW 等）の流れに連なる。

### エンタープライズ向け「実務に効く AI」へ資金が集中した — [industry]
- Taktile が $110M シリーズC（Goldman Sachs 主導、金融機関向け AI 意思決定）、Assort Health が $120M シリーズC（医療の患者アクセス自動化）を調達した。Q1 の記録的調達（AI に VC 全体の約80%＝$242B）の流れを継ぎ、意思決定や業務執行に直接関わるプロダクション AI へ資金が向かう傾向が続いている。
  https://techstartups.com/2026/06/24/venture-capital-startup-funding-roundup-june-24-2026/

## 来週の注目予定

- **6/30**: Devin classic 環境設定の廃止（→ blueprints）／ GPT-5.2・5.3-Codex の新規 API 利用不可 ／ Anthropic サイエンスイベント
  - Microsoft 系: Copilot Studio for Teams クラシック作成終了 ／ 感度ラベル表示 GA ／ Security Copilot E5 展開完了 ／ M365 価格ロックイン期限
  - Gemini 3.5 Pro の6月公開予測（7月延期報道が優勢）
- **7/1**: M365 価格改定（E3 $36→$39、E5 $57→$61、Copilot Business $18→$21）／ Cursor 新価格 ／ Devin Cascade 削除
- **〜7月上旬**: Fable 5 の US 復旧交渉（Mythos 5 は限定復旧済み）／ GPT-5.6 の一般提供（数週間内）／ Claude Partner Network 初回昇格レビュー
- **7/8**: Anthropic の政府発行 ID・生体情報検証ポリシー施行（米市民限定の先行復旧の最有力経路）
- **7月中旬**: GPT-5.6・Gemini 3.5 Pro・Claude Opus 4.7 のローンチ集中報道
- **7/17**: Claude Corps 第1期応募締切
- **7/31**: Devin classic 環境設定の read-only 参照終了
- **8/1**: covered frontier model フレームワークの60日大統領令期限
- **8/3**: 旧「Claude in Slack」アプリ退役
- **8/5**: Claude Opus 4.1 の Claude API 退役
- **8/26**: OpenAI Assistants API 廃止 ／ o3 退役 ／ GPT-4.5 完全廃止
- **9月**: iOS 27 / macOS 27 GA（AFM 3 本番）

## 改善メモ

- 【取得障害】3リポとも WebFetch / RSS の 403 が週を通じて継続し、WebSearch プライマリ運用で全件を代替した。
  - [master] anthropic.com/news（`/news/fable-mythos-access` 含む）は7日中5日で 403 を明記（6/24・6/28 は記録なし。6/28 は同 URL を出典に掲載）。ほかに techtimes.com（6/22）・KuCoin（6/24）・Globe and Mail（6/25）・explainx.ai（6/28）。Claude Code Changelog のみ WebFetch が安定し、記録のある4日（6/24〜6/27）はいずれも直接取得できた
  - [copilot] anthropic.com / github.blog / cursor.com に加え、mc.merill.net（6/23）・theglobeandmail.com（6/24）・nbcnews.com / thehill.com / mlq.ai（6/28）。Claude Code changelog は 6/22–6/27 を raw.githubusercontent.com 経由、6/28 のみ github.com blob 経由で取得した
  - [industry] Google News・GIGAZINE・The Decoder・VentureBeat・Publickey・hnrss.org・Product Hunt・GitHub Trending・llm-stats・pricepertoken・buildfastwithai が全滅。`daily-sources.md` の取得方法欄を「WebSearch 優先」へ更新する提案を7日連続で記録している
- 【git 履歴の乖離】[master] でセッション開始時に local main と origin/main が完全乖離（merge-base が空）する事象が 6/23・6/24・6/25・6/26 と4回連続で発生した。毎回 `git reset --hard origin/main` で復旧しており、6/26 には「恒久対策として SessionStart hook への組み込みを強く推奨」まで提案が強まっている。[industry] でも local / origin が 06-05 で停滞する同種の事象が7日連続で再発し、6/27 には `.last-check-state.md` も 06-05 のままだった。両リポで同じ恒久対策が要る。
- 【取りこぼし】週内に検知された取りこぼしは次のとおり。
  - Claude Code の最新版番号を [master] が2日連続で誤記（6/23 は v2.1.185→実際 v2.1.186、6/24 は v2.1.186→実際 v2.1.190）
  - Claude Tag（6/23 発表）を [master] 6/25 で取りこぼし、6/26 に反映
  - Mythos 5 の限定再開（6/26）を3リポ揃って 6/27 で取りこぼし、翌 6/28 にまとめて反映
  - OpenAI のクレジット分析・支出上限（6/18）と OpenAI×Broadcom Jalapeño（6/24）を [industry] が後日補足
- 【リポ間の矛盾】次の6点は本サマリーで両論併記または断定回避とした。
  - トランプ発言の日付が [master] 6/20（Axios）と [copilot] 6/24 / 6/19 で割れており、本サマリーでは「6月下旬」として断定していない
  - Mythos 5 の限定再開の対象組織数が [master]・[industry] の「約100」と [copilot] の「100社超」で割れており、ハイライト1の詳細で幅として併記した
  - 「Fable / Mythos トラフィックは正確にゼロ」の基準日が [master] 6/27 と [copilot] 6/25 で割れており、両方を併記した
  - Cursor SDK 更新の日付が [master] 内で「6月（URL は sdk-updates-jun-2026）」と「6/4」に食い違う
  - 6/12 停止指示への相互参照リンクが [copilot] 内で不統一（6/22–6/24 は `ai-news-2026-06-13.md`、6/28 は `ai-news-2026-06-12.md`）
  - 予測市場の数値が Kalshi / Polymarket と期限設定の違いを跨いで並記されており、1本の推移として読めない
- 【担当範囲の逸脱】[copilot] は W26 の7日中6日で先頭 H2 が「AI開発ツール」（Fable 5 / Claude Code）になっており、Microsoft 専任という建付けから外れていた。この逸脱は 2026-07-26 に 02 の CLAUDE.md と rules で是正済み。本サマリーでは Fable 5 / Claude Code / GPT-5.6 を [master] 側とマージし、[copilot] 単独タグにしていない。
- 【情報の確度】NSA 侵入証言は一次情報が Warner 議員1名の伝聞のみで NSA の公式声明がないため、「報道ベース・未確認」と明示した。速報系暗号メディア（KuCoin）の「Fable 5 再出現」記事は一次確認ができないため復旧の確証として扱っていない。[industry] が一次情報未確認で不採用としたのは、Claude Sonnet 4.8 / Grok 5 / Claude Mythos 1 の噂と、Anthropic によるアリババ告発（2,880万件の不正交換）。
- 【新規提案】政府による frontier モデル出荷ゲート（Mythos 5 / GPT-5.6）を新カテゴリとして継続追跡し、OpenAI 側の段階出荷状況を daily-sources の OpenAI 枠へ加えることが [master] 6/28 で提案された。[industry] からは、年次デベロッパーイベント（AWS Summit NYC・GitLab Transcend）を重点確認時期に追加する提案と、フロンティアラボの公式 newsroom を定点ソースに追加する提案が出ている。
- 【WebSearch のデータ鮮度】[industry] 6/25 で「June 2026」クエリでも過去の大型ニュースが上位に返る事象を記録し、2件を日付検証で除外した。金額・買収系は必ず一次ソースで公表日を確認する運用を継続する。
- 本ファイルは 2026-08-02 に欠番バックフィルとして生成した。W26 は本来 2026-06-29（月）に生成されるはずだったが欠番のままで、W30（2026-07-27 生成）の改善メモに「W26 が欠番」と記録されていた。
