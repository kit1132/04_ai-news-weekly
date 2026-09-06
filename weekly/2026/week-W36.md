# AI ニュース週次サマリー — 2026-W36（2026-08-31 〜 2026-09-06）

> 生成日時: 2026-09-07（JST）

## 今週のハイライト

### 1. OpenAI が GPT-6 Astra を出荷 — GitHub Copilot でも1日で既定オン化した — [master][industry]

**要点**: OpenAI が9/3にサイバー能力で「Critical」に達した GPT-6 Astra を出荷し、9/4に GitHub Copilot でも既定オンで GA した。審査通過前提のモデルが、止めない限り自動で入るモデルへ変わった。

**詳細**: 単価は短文脈で入力$10／出力$50、長文脈（272Kトークン超）で$20／$75と Sol 比2.5倍。コンテキスト105万トークン、知識カットオフは2026-04-30。`temperature`／`top_p`は非対応で tool calling は Responses API 必須という制約が入る。Copilot 側の対象は Pro+／Max／Business／Enterprise（Pro は対象外）で、管理者がポリシーを個別に無効化しない限り既定で有効になる。system card は chain-of-thought の監視可能性が従来モデル比で大幅に低下したと明記している。

- https://developers.openai.com/api/docs/models/gpt-6-astra
- https://developers.openai.com/api/docs/pricing
- https://github.blog/changelog/2026-09-04-gpt-6-astra-is-generally-available-in-github-copilot
- https://deploymentsafety.openai.com/gpt-6-astra

### 2. Claude Fable 5.1 が GA — キャッシュ単価75%減と引き換えに既存実装が壊れる — [master][copilot][industry]

**要点**: Anthropic が9/1に Fable 5.1 を GA した。基本料金は据え置きのままキャッシュ読み取りが$1→$0.25に下がる一方、強制ツール呼び出しと履歴書き換えは400エラーになる破壊的変更が入った。

**詳細**: モデル ID は `claude-fable-5-1`。基本入力$10／出力$50は不変で、キャッシュ読み取りだけ他モデルの0.1倍に対し0.025倍に下がった。`tool_choice` の `any`／`tool` 指定は400を返し strict tool use か structured outputs への移行が要る。9/2に Claude Code の既定 Fable モデルとなり、9/3に GitHub Copilot でも GA したが、既定はデータ保持ありで ZDR 契約下では年内は個別免除、以後は Enterprise Frontier Safeguards が必要になる。

- https://platform.claude.com/docs/en/release-notes/api
- https://platform.claude.com/docs/en/models/fable-5-1/whats-new-fable-5-1
- https://github.blog/changelog/2026-09-01-claude-fable-5-1-generally-available-in-github-copilot

### 3. インフォスティーラーが Claude のセッションを乗っ取った — 2FA を有効にしていても端末感染時点で認証が迂回される — [master][industry]

**要点**: Anthropic が8/30、盗まれたセッション Cookie でアカウントを乗っ取られた利用者へ連絡を始めた。2要素認証を経ずに有料枠を消費でき、防御前提が「2FAで足りる」から「端末感染で認証状態ごと持ち去られる」へ変わった。

**詳細**: 確認されたマルウェアは Windows 側が Vidar・LummaC2・StealC・RedLine・Acreed、Mac 側が Atomic Stealer（AMOS）。Anthropic は侵害セッションの強制サインアウト、保存済み支払い方法の削除、不正課金の返金を実施し、Claude 本体・基盤の侵害ではなく利用者端末の感染が原因であると明示している。サインアウトはマルウェア自体を除去しないため、再ログイン前の端末スキャンとメールアカウントのパスワード再設定・2FA有効化が推奨される。使っていないのに週次枠が減る挙動が兆候にあたるが、影響ユーザー数は週末時点でも公表されていない。

- https://www.bleepingcomputer.com/news/artificial-intelligence/anthropic-warns-infostealer-malware-is-hijacking-claude-sessions-to-drain-usage/
- https://www.helpnetsecurity.com/2026/08/31/claude-accounts-compromised-through-infostealer/
- https://securityaffairs.com/198166/ai/infostealers-are-hijacking-claude-sessions-and-draining-subscriptions.html

### 4. OpenAI が Cursor へのモデル提供を11月12日で打ち切る — 親会社の変更が供給停止の引き金になった — [industry]

**要点**: OpenAI が8/28、SpaceX による Cursor 買収を理由にモデル提供を11/12で打ち切ると告知した。新モデルも提供しないため、OpenAI モデル前提の構成は約2カ月半で移行が要る。

**詳細**: SpaceX は6/16に$60Bの全株式交換で Cursor の親会社 Anysphere を買収すると発表し、8/14に完了。OpenAI はその2週間後の8/28に change-of-control 条項を行使し、契約上最大の予告期間である11/12を遮断日とした。理由として「Elon Musk の各社が契約に違反してきた経験」を挙げ、契約巻き取り中は新モデルも提供しないとしている。OpenAI モデルは Cursor の利用トラフィックの約5%にとどまり、Grok・Composer・Claude・Gemini は引き続き選べる。Cursor の有料開発者は100万人超とされる。

- https://openai.com/index/our-decision-on-cursor-following-its-acquisition-by-spacex/
- https://www.cnbc.com/2026/08/29/openai-cursor-spacex-model-access.html
- https://forkast.news/openais-cursor-termination-turns-model-supply-into-a-competitive-weapon/

### 5. GitHub Copilot が PR を承認できるようになった — 承認人数で品質を担保する運用の前提が崩れた — [master][industry]

**要点**: GitHub が9/1、Copilot code review に merge requirement へ数える承認提出の権限を持たせた。既定オフだが、承認人数で品質を担保してきたレビュー運用は有効化の可否を組織として決める必要が生じた。

**詳細**: 対象は Copilot Pro／Pro+／Max／Business／Enterprise。既定では Copilot は承認せず、全レビューの overview コメントに入る「承認アセスメント」単体は merge requirement に数えない。実際の承認提出可否は enterprise（許可・拒否の決定）・organization（全社有効化／リポジトリ委譲／無効化）・repository（オン・オフと Copilot が承認できるファイルパスの制限）の3階層で設定する。新規コミットが push されると Copilot の承認は人間のレビュアーと同じく自動的に取り消される。

- https://github.blog/changelog/2026-09-01-copilot-code-review-can-now-approve-pull-requests

## Claude Code / Claude Developer Platform

### 週内に v2.1.252〜v2.1.261 まで6回のリリースを重ね、権限まわりの修正と統制機能の追加が続いた — [master][industry]
- Anthropic は auto モードの権限厳格化から無人ホスト向け機能まで、版ごとに統制機能を積み増した。
  - `2.1.257`（9/1）: auto モードの containment escape ルールが厳格化され、クラウドメタデータからの認証情報取得や egress 回避は環境が想定内と示さない限り自動承認されなくなった
  - `2.1.258`（9/1）: macOS 12 での起動失敗と、スケジュール実行セッションが `user messages must have non-empty content` で失敗する不具合を修正した
  - `2.1.259`（9/2）: 組織が MCP サーバーを一括配布できる `managedMcpServers` と、無人ホスト向けの `--permission-prompts none` を追加した
  - `2.1.260`（9/3）: Bash 権限チェックの脆弱性を修正した一方、`2.1.259` で入れた `Read()` 拒否ルールのオプション値ファイルへの適用は差し戻された
  - `2.1.261`（9/4）: 未使用スキルを洗い出す `/skill-doctor` と、組織ポリシーの読み込み失敗を可視化する `/status`／`claude doctor` 表示を追加した
- https://code.claude.com/docs/en/changelog

### npm の stable は週を通じて 2.1.236 のまま動かず、latest との差が16版から25版へ広がった — [master]
- npm の `dist-tags` は `stable` が `2.1.236` のまま更新されず、`latest` との差は8/31時点の16版から9/6時点で25版まで開いた。8/28の `2.1.251` に入った symlink 経由の権限境界修正群は、stable 固定の組織へ週末になっても届いていない。

### モデル退役ページに claude-fable-5-1 が Active として加わり、Active モデルは11件になった — [master]
- モデル退役ページには `claude-fable-5-1` が Active として加わった（暫定退役日 2027-09-01 以降）。いずれの日付も「not sooner than」であり確定日ではない。

## Claude 製品 / Anthropic

### Anthropic が Enterprise Frontier Safeguards（EFS）を発表し、ゼロデータ保持の意味を変えた — [master][industry]
- Anthropic はセッション乗っ取り対応（ハイライト3参照）に加え、9/1に EFS を発表した。監視ログを顧客所有の AWS S3／Azure Blob／GCS へ顧客の暗号鍵で保存し、Anthropic は誤用検知ロジックだけをそこに対して動かす方式で、ゼロデータ保持の意味を「Anthropic 側に何も残らない」から「顧客クラウドに残り Anthropic が読む」へ変えた。提供は今秋から段階的で、それまでは適格顧客が Fable 5／5.1 の ZDR を暫定的に受けられる。

### Anthropic が commerce agents blueprint とフェルマーの最終定理の完全形式化証明を公開した — [master][industry]
- 9/2: 小売・旅行・通信向けの commerce agents blueprint を公開し、Shopify・Priceline・Visa 等と連携する実装一式を GitHub で配布した
- 9/4: Claude によるフェルマーの最終定理の Lean 4 形式化を公開した。モジュール60,475個・定理29,511個の完全な機械検証済み証明で、`axiom`／`sorry` 等を一切含まない

### 政府対応は1日で「信頼する」発言が打ち消され、指定継続の前提に戻った — [master][industry]
- 商務長官 Lutnick が9/2に「Anthropic を信頼する」と述べたが、9/3に国防総省の Michael 次官が supply-chain risk 指定の継続を明言し、1日で打ち消された。指定は8/27の連邦地裁による違法判断後も D.C. の訴訟決着まで残る前提に戻っている。

### 資金調達でクレジット枠拡大と Lambda との大型クラウド契約が判明した — [master][industry]
- リボルビング・クレジット・ファシリティを$150億へ拡大中（Morgan Stanley 主導）とされ、Nvidia 出資の Lambda とは約$350億のクラウド契約（Hut8が開発するテキサス州データセンター・約350MW）を結んだと報じられ、直近のクラウド契約は計$1,750億に達したとされる。

### 8月 Risk Report が一次未読のまま21日連続に達した — [master][industry]
- ⚠️ 8月 Risk Report は週末時点で21日連続一次未読である。

## GitHub Copilot（開発者向け）

### PR レビュー承認機能が公開され、新規申込の再開も同日に告知された — [master][industry]
- GitHub は9/1、Copilot code review に merge requirement へ数える承認提出の権限を持たせ（ハイライト5参照）、同日 Business／Enterprise 向け新規申込の再開も告知した。⚠️ 8/31時点では9/1を「新規シート前払い化」と記録していたが、実際は新規申込の再開であり、シート前払い必須化は10/1の既存顧客向けである。

### 複数組織所属者のモデルアクセス決定権が請求元組織へ一本化された — [master][industry]
- 9/1、複数組織でシートを持つ利用者のモデルアクセスを、請求を負担する組織の設定だけで決めるよう変更した。所属先のいずれかが有効化していれば使えた従来の運用から、決定権が請求元組織へ一本化された。

### enterprise-managed の既定モデル指定とコンテンツ除外ポリシーが GA した — [master][industry]
- 9/2、enterprise-managed settings で管理者が新規会話の既定モデルを指定できるようになり（GA）、Copilot アプリ・CLI 向けのコンテンツ除外ポリシーも GA した。

### Claude Opus 4.7 ほか3モデルの10/2廃止と Gemini 3.8 Flash の GA が同日に告知された — [master][industry]
- 9/3、Claude Opus 4.7・Gemini 3.5／3.6 Flash・Kimi K2.7 Code の10/2廃止を告知し、同日 Gemini 3.8 Flash を GA した（管理者が個別に無効化しない限り既定で有効）。

### GPT-6 Astra が Copilot で GA した（ハイライト1参照）— [master][industry]
- 9/4、GPT-6 Astra を GA した。

### Copilot CLI が v1.0.82 から v1.0.84-1 まで進み、GitHub CLI の署名鍵失効も判明した — [master][industry]
- Copilot CLI は週内に `v1.0.82`（8/29）→ `v1.0.83`（9/4、CIMD対応・`claude-fable-5.1`対応・廃止モデルのピッカー除去など6版分を集約）→ `v1.0.84-1`（9/4、GPT-6 Astra 対応）まで進んだ。
- ⚠️ GitHub CLI（`gh`）の Linux パッケージ署名鍵は9/5に失効し、2026年4月8日より前に APT／RPM で導入して以降キーリング設定を更新していない環境は、以後の取得が検証エラーで止まる。

## Microsoft 365 Copilot / Power Platform

### Power Platform の開発・トライアル環境で GitHub Copilot ハーネスが従量課金化した — [copilot][industry]
- Power Platform では9/1から開発環境・トライアル環境の GitHub Copilot ハーネスが従量課金に入り、作成した時点から Copilot Credits を消費するようになった。無償で試作できるという前提は終わり、環境への前払いクレジット割当やテナントプールからの引き当てオフなど6つの統制経路が整理された。

### Release Wave ページが一時404を経てリネームと判明し、判定方式ごと廃止されると分かった — [copilot][industry]
- Release Wave のページは9/3に一時404となったが、9/4に URL のリネーム（`microsoft-power-automate` → `power-automate` 等）と判明した。再ビルド後の再集計では8月期日8件のうち達成1件・未達7件・期日延期1件（Jul→Sep）が確定している。⚠️ この判定経路自体が9/6に廃止されると判明した。2026 Release Wave 2の告知は行われず、Release Planner は11/15に退役し、新規ロードマップは今後 AI at Work roadmap へ集約される。半期単位の緑チェックで GA を追う運用は組み直しが要る。

### Fable 5.1 と GPT-6 Astra が Copilot Studio のモデル一覧に載らないまま提供開始した — [copilot][industry]
- Claude Fable 5.1（9/2に Cowork と Copilot Studio で提供開始）と GPT-6 Astra（9/4）はいずれも、Copilot Studio のモデル可用性一覧（`authoring-select-agent-model`）に行が追加されないまま提供が始まっており、一覧に載っていないことは使えないことを意味しなくなった。⚠️ Copilot Studio の GitHub Copilot ハーネスは GA（8/3）から34日連続で `(Production-ready preview)` の表記が残っており、9/2の月次記事が GA と明記した内容と食い違ったままである。

### SharePoint クラシックページの2段階退役と Power Automate ヘルプチャットボット削除が判明した — [copilot]
- SharePoint ではクラシックページと custom scripting の退役が2段階（2027-03-01・2028-10-01）で告知され、理由として初めて「Copilot のグラウンディング精度を下げる」ことが明記された。Power Automate メーカーポータルでは9/9に PVA ヘルプチャットボットが全ページから削除される。

## OpenAI / Codex / ChatGPT

### API のエラーコード分離と Responses API への3制御追加、Codex CLI の複数回更新が続いた — [master][industry]
- OpenAI は GPT-6 Astra 出荷（ハイライト1参照）に加え、週内に API と Codex CLI の機能追加を重ねた。9/2に API のエラーコードを分離し、急激なトラフィック増加は `429` の `slow_down`、モデル過負荷は `503` の `server_is_overloaded` で呼び分けられるようになった。9/3には Responses API へ、ツール実行中もモデルが作業を続ける async tool calling、WebSocket 経由で生成中に指示を追加できる mid-turn steering、キャッシュを保ったまま effort を変更できる mid-conversation reasoning effort の3制御を追加した。Codex CLI は `0.151.0`（8/29）から `0.153.4`（9/4、GPT-6 Astra 対応）まで週内に複数回の安定版更新を重ねた。

### Cyber モデルの単価が一部確定し、広告事業は開始200日未満で年換算$10億に到達した — [master][industry]
- 料金面では Cyber モデル節の単価が一次で確定し、`gpt-5.6-cyber` は入力$12.50／出力$75と判明したが、`gpt-5.4-cyber` は週末時点でも単価欄が空のままである。広告事業は開始200日未満で年換算売上$10億に到達し、9/4にセルフサービスの Ads Manager をインド・欧州・中東北アフリカへ拡大した。

### ChatGPT for Healthcare が Epic の電子カルテと連携した — [master][industry]
- ChatGPT for Healthcare は Epic の電子カルテと連携した（読み取り専用）。米国の病院の約4割で使われる Epic 経由で患者コンテキストを会話に持ち込めるようになった。

### 退役期限は変更なく、9月中も複数到来する — [master]
- ⚠️ 退役期限に変更はなく、直近は9/24（Videos API・Sora 2系）、9/28（`gpt-3.5-turbo-instruct` 等）が今月中に到来する。

## Google / Gemini

### Gemini 3.8 Flash が GA し、Flash 系最上位モデルが20日で入れ替わった — [master][industry]
- Google は9/1に Gemini 3.7／3.6 Flash と3.5 Flash-Lite へ agentic video understanding を追加し、モデルが必要な区間だけを読みに行く方式で長尺動画のトークン消費を最大88%・コストを最大66%削減できるとした。9/2には `gemini-3.8-flash` を GA し、単価は3.7 Flash と同額（$0.75／$3.75、2026年12月31日まで）のまま Terminal-Bench 2.1が81.6%→90.8%へ上がったとされる（ベンチマーク値は二次情報）。Flash 系の最上位モデルは3.7から3.8へ20日で入れ替わった。9/3には GitHub Copilot でも Gemini 3.8 Flash が提供開始された。

### Gemini 3.5 Pro の GA 未ローンチが継続している — [master][industry]
- ⚠️ Gemini 3.5 Pro の GA は週末時点でも未ローンチが継続している。音楽生成の Lyria 3.5（9/3 public preview）は本サマリーの対象領域外として記録に留める。

## Cursor / xAI / Devin

### Cursor が self-hosted machines と Grok Bot の Android 版を追加した（OpenAI の供給停止についてはハイライト4参照）— [master][industry]
- Cursor は9/2に self-hosted machines に対応し、AWS Lambda・Coder・Cloudflare・Daytona・Modal 等のサンドボックス上でツール実行を自社インフラに完全に留められるようになった。同日 Grok Bot の Android 版も公開し、モバイルからのタスク指示とデスクトップでの継続実行に対応した。

### Grok 4.7 は予告から進展がなく、Devin の提供元は評価額$47Bへの調達交渉が報じられた — [master][industry]
- xAI の Grok 4.7 は9/2に Musk が X 投稿で予告した内容（パラメータ2.1兆・公開見込み9/11〜9/12）から進展がなく、⚠️ 公式の裏づけはなく一次3ホスト（`x.ai`／`docs.x.ai`／`grok.com`）はいずれも到達不可のままである。公式提供中の最上位は Grok 4.6（8/12・$2／$6）のままである。Devin は CLI・ドキュメントとも一次への到達が週を通じてできず、Bloomberg は提供元 Cognition の調達交渉が評価額$47B（5月時点$26Bから）へ切り上がっていると9/2に報じた。

## MCP / エージェント標準

### WebMCP Challenge の提出が締め切られ、MCP・A2A の更新は乏しいまま週を終えた — [master]
- WebMCP Challenge の提出締切は9/4に経過し、受賞発表は9/23・賞金総額$35,000である。MCP 公式ブログ（`blog.modelcontextprotocol.io`）は8/22の記事が週を通じて最上位のままで新規更新はない。A2A（Agent2Agent）の AAIF 参加は週末時点でも未確定である。

## オープンウェイト / ローカル LLM

### DeepSeek が画像対応の V4-Flash-Vision-Exp を公開し、Qwen の非公開→公開切り替えが検出網の穴を明らかにした — [master]
- DeepSeek は8/31に `DeepSeek-V4-Flash-Vision-Exp` の重みを MIT ライセンスで Hugging Face へ公開し、画像を読むエージェント基盤を自社環境に置ける選択肢が増えた（総パラメータ284B・context100万トークンは二次情報）。Qwen は自動運転向けの `Qwen-Drive-1.0-4B`（作成8/27）を非公開作成後に公開へ切り替えており、この種の切り替えは `createdAt` 降順の巡回だけでは検出できないことが週内に判明した。それ以外の主要8組織（Qwen／moonshotai／deepseek-ai／meta-models／mistralai／zai-org／openai／google）に新規公開はなかった。

## Apple / クラウド

### Apple が Intel 版 macOS への Rosetta サポート終了を予告し、AWS Bedrock は主要モデルを初日提供し続けている — [master]
- Apple は9/1に Intel 版 macOS アプリ向け Rosetta サポートの終了を予告し、macOS 27が Rosetta を搭載する最後のリリースになる。特別イベントは既報どおり9/9 10:00 PT に開催される。AWS Bedrock は主要モデルの初日提供を続けており、Fable 5.1（9/1）・GPT-6 Astra（Codex CLI 経由・9/4）とも初日から利用できた。

## 企業構造・規制・資本市場

### Sony Music Publishing と Warner Chappell Music が Anthropic を著作権侵害で提訴した — [industry][master]
- Sony Music Publishing と Warner Chappell Music が8/28に Anthropic を著作権侵害で提訴し、Dario Amodei と Benjamin Mann を個人としても被告に加えた。Universal・BMG・Round Hill に続き大手出版社3社すべてが Anthropic と係争状態に入ったことになる。請求は故意侵害1曲あたり最大$150,000の法定損害賠償である。

### サイバー攻撃対策の公開書簡・GenAI.mil拡大・DOJ声明が相次いだ — [industry][master]
- 8/27: Google・OpenAI・Anthropic を含む100社超が AI を使ったサイバー攻撃への「防御の総動員」を求める公開書簡に署名した
- 8/31: 米国防総省が GenAI.mil に OpenAI の ChatGPT Mil と xAI の Grok for Government を追加し、対象を300万人超に広げた。⚠️ Anthropic は指定継続（本サマリー「Claude製品/Anthropic」参照）により本発表に含まれていない
- 9/1: 米司法省が NYT 対 OpenAI の著作権訴訟で OpenAI／Microsoft 側に立つ statement of interest（拘束力なし）を提出した

### データセンター新興2社が大型調達を発表した — [industry]
- データセンター新興の Crusoe が評価額約$300億で$30億超を調達し（9/3成立）、AI 半導体の Gimlet Labs も評価額$30億で$300M を調達したと報じられた（一次未確認）。

## 市場データ・調査

### McKinsey 調査でエージェントのスケール率は伸びたが EBIT 寄与は横ばいだった — [industry]
- McKinsey の State of AI 2026（8/25公開・世界1,719名調査）によれば、大企業でエージェントを1機能以上へスケールした割合は27%→40%へ伸びた一方、EBIT への何らかの寄与を認めるのは37%で前年並みにとどまった。EBIT の5%以上を帰属させる「AI高パフォーマー」はわずか6%である。完全なスケールを阻む最上位の要因は、約3分の2が挙げるセキュリティ・リスク懸念である。

### Gartner 予測で AI 支出が2026年に$2.59兆に達する見込みが示された — [industry]
- Gartner の予測では、世界の AI 支出が2026年に$2.59兆（前年比+47%）、うち AI 最適化 IaaS が$420億（同+96%）とされ、既収録の AI モデル・プラットフォーム支出$640億と合わせてインフラ・IaaS・モデルの3階層で数字が揃った。⚠️ Similarweb の生成AIトラフィックシェアは二次情報間で数値が割れており（ChatGPT 53.9%対52.7%等）、一次未読のため引用は保留する。

## 来週の注目予定

- 9/8: M365 Copilot Release Notes の次バッチ（隔週想定）／Power Platform Released Versions の定例更新日
- 9/9: Apple 特別イベント（10:00 PT）／GLM-5.3-Flash の Z.ai 経由50%割引終了／Power Automate メーカーポータルの PVA ヘルプチャットボット削除
- 9/10: MAI-Code-1-Flash が全 Copilot 体験から廃止
- 9/12: Grok 4.7 の公開予定（Musk の投稿のみが出所・公式の裏づけなし）
- 9/13: Claude Code の週次上限50%増が終了
- 9/14: Claude Code の標準週次上限が恒久的に+25%（現行比では約17%減）
- 9/17: OpenAI DevDay Exchange の応募締切
- 9/21: Anthropic ウェルビーイング研究助成の応募締切
- 9/23: WebMCP Challenge の受賞発表
- 9/24: OpenAI の Videos API と Sora 2系が退役
- 9/28: GitHub Copilot のチャット3面統合／code review 既定 Balanced 化／チャットのデータ保持がアカウント存続期間へ／OpenAI の `gpt-3.5-turbo-instruct` 等4モデル停止
- 9/29以降: `claude-sonnet-4-5-20250929` の暫定退役日（確定日ではない）
- 9/30: Gemini の旧 `gemini-omni-flash-preview` 廃止／2026 Wave 1 の対象期間終了
- 9月中: Release Plans on Learn の新規掲載停止／Copilot Tuning の Public Preview 再開／Copilot デスクトップアプリの広範展開（中旬）
- 10/1: GitHub Copilot Business／Enterprise の既存顧客前払い必須化／Apple の EU 向け新ビジネス条件発効／CSP software の価格改定
- 10/2: GitHub Copilot が Gemini 3.5／3.6 Flash・Kimi K2.7 Code・Claude Opus 4.7 を全体験から廃止
- 10/5: Anthropic ウェルビーイング研究助成の full proposal 提出期限
- 10/15以降: `claude-haiku-4-5-20251001` の暫定退役日
- 10/16-11/11: OpenAI DevDay Exchange 8都市（東京は10/20）
- 10/23: OpenAI のレガシースナップショット退役
- 10/27-29: Power Platform Community Conference 2026（ラスベガス）
- 10/31: OpenAI の既存 evals が読み取り専用化
- 秋: Anthropic Enterprise Frontier Safeguards の段階提供開始
- 11/15: Microsoft Release Planner の退役（Release Wave 全体の廃止に伴う）
- 11/21: GPT-5.6 Sol の暫定値下げ有効期限
- 11/24以降: `claude-opus-4-5-20251101` の暫定退役日
- 11/30: OpenAI の Reusable prompts・Evals・Agent Builder が停止
- 12/1: OpenAI の GPT Image 系が停止
- 12/2: EU AI Act の生成コンテンツ標識義務の猶予終了
- 12/11: OpenAI の旧スナップショット退役
- 12/31: Gemini 3.8／3.7 Flash の導入価格終了／GitHub Copilot の Fable 5.1・5に対する ZDR 暫定免除終了
- 2027-01-06: OpenAI で大半ユーザーの新規ファインチューニングジョブ作成が終了
- 2027-01-20: OpenAI の audio／realtime 系退役
- 2027-02-26: OpenAI の文字起こし4モデル退役
- 2027-03-01: SharePoint クラシックページ退役フェーズ1
- 2028-10-01: SharePoint クラシックページ退役フェーズ2

## 改善メモ

- 利用枠・料金変更の検知経路（`x.com/@ClaudeDevs` 相当）をソース一覧に追加する（[master]）
- DeepSeek 公式 news（`api-docs.deepseek.com/news/`）、OpenAI 退役ページ（`developers.openai.com/api/docs/deprecations`）、`deploymentsafety.openai.com` をそれぞれ一次ソースとして登録する（[master]）
- Claude モデルドキュメントの追跡 URL をモデル固有ページからモデル非依存の一覧＋`whats-new` へ差し替える（[master]）
- `claude.com/blog` の取得を日付フィルタ付きから全 href の列挙へ固定し、Anthropic の research 公表は `github.com/anthropics/<リポジトリ>` から一次確認する経路を整備する（[master]）
- Copilot Studio 課金3ページ・Release Wave 関連ページの URL 移設（301 ではなく404で消える）に伴い、追跡 URL を新パスへ随時差し替える運用を徹底する（[copilot]）
- ⚠️ 二次報告の裏取りを Release Notes 単独で行うと、実際にロールアウト済みの機能を落とすことが判明した。月次まとめ記事等の副次ソースも突合対象に加える（[copilot]）
- モデルの提供開始判定を、更新が遅れがちな Learn のモデル一覧から Tech Community の「Available today:」記事へ主軸を移す（[copilot]）
- Power Platform 非推奨一覧の確認頻度を週次から毎日へ引き上げる（[copilot]）
- ⚠️ **矛盾の記録**: [copilot] は9/2の月次記事で Copilot Studio の GitHub Copilot ハーネスを GA と明記した一方、[copilot] 自身が追う一次ドキュメント（What's New）は週末時点でも34日連続で `(Production-ready preview)` 表記のままである。GA 可否の一次情報源が社内で割れた状態が続いている
- ⚠️ [master] と [industry] は共通して、同一主題の一次・二次ホストが同時にゲートウェイ拒否される型が週内に複数回再発したことを継続課題として記録している
