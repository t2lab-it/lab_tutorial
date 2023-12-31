# lab_tutorial

研究室のチュートリアル資料

----

## PC・ソフトウェア関連

### PCの設定方法

 <!-- `howto_setup_PC.md` -->

- Linuxの設定方法
  - [執筆者（荒木）の初期設定](https://github.com/ryo-ARAKI/TIL/blob/master/linux/initial_setup.md)
  - SSH/GitHub/VSCode/...の設定方法

### 数値計算コードの書き方

 <!-- `howto_develop_numerical_simulation_code.md` -->

### 研究や論文執筆でのGit/GitHubの使い方

 <!-- `howto_use_git_for_research.md` -->

- 研究コード：Issue/Pull Requestを使って「常に動く」コードを `main` ブランチに置く
- 論文：別ブランチで執筆や添削の反映→ `latexdiff-vc` を使って `main` ブランチとの差分PDFを出力する

----

## 論文や教科書関連

### 論文の探し方

 <!-- `howto_survey_previous_research.md` -->

あるトピックの先行研究を知りたいときは：

1. 研究室の中で探す
   1. 知っていそうな先輩に聞く：その分野の重要な研究者や「分野の流れ」を教えてもらえるかも．
   2. 関連しそうな研究室の既発表論文を調べる：わからないときに教員や先輩に訪ねやすい．
   3. 関連する分野の教科書を読む：その分野を創始した論文や重要な発展に寄与した原著論文が引用されているはず．
2. レビュー論文を探す
  - レビュー論文：原著論文と教科書の中間で「あるトピックの過去十年〜数十年の進展」をまとめた論文で分野の概観をつかみやすい．
  - 流体力学分野だとまずはAnnual Review of Fluid Mechanicsで探すとよい．
  - 他にもAnnual Review of Condensed Matter Physics，Nature Reviews Physics，Review of Modern Physics，Physics Reports，...など．
3. 原著論文を探す
  - 流体力学分野だとJournal of Fluid Mechanics，Physical Review Fluids，Physics of Fluids，Fluid Dynamics Researchなどが定評のある雑誌．
  - 他にもPhysical Review Letters/E/Research，...など．

異なる論文雑誌から横断的に論文を探せるサイトは：

- [Google scholar](https://scholar.google.co.jp/)
  - 「その論文を引用した論文」を網羅的に探しやすい．
  - `.bib` ファイルも（出版社のサイトより）使いやすいと思う．
  - お金を払わないと読めない論文もなんやかんや本文を読めるリンクがついていたりする．
- [arXiv](https://arxiv.org/)
  - 査読を経て出版される前のプレプリントが読める．
  - 「正式に出版された原稿」ではないことに注意する．
  - お金を払わないと読めない論文も草稿段階の原稿がアップされていたりする．
  - 流体力学関連は[physics.flu-dyn](https://arxiv.org/list/physics.flu-dyn/recent)をみればよい．
  - [arXiv Xplorer](https://arxivxplorer.com/)でarXivから効率的に検索できる．
- [Perplexity](https://www.perplexity.ai/)，[Elicit](https://elicit.org/)，[Typeset](https://typeset.io/)，[Consensus](https://consensus.app/)
  - 知りたいトピックを尋ねると **存在する** 文献を挙げてくれる．
  - ChatGPTは存在しない文献を紹介してくるので論文探しには使わないこと．
- [Connected Papers](https://www.connectedpapers.com/)
  - 注目したい論文を入力すると，関連論文の相関図を出してくれる．
  - 無料版だとかなり厳しい回数制限があるので注意．

###  論文の読み方

<!-- `howto_read_paper.md` -->

- [kaityo256：論文の読み方](https://speakerdeck.com/kaityo256/how-to-survey)
- その論文が引用している&その論文を引用している文献をチェックして大きな研究の文脈上に位置づける
- 多読：論文雑誌の新着論文をRSS通知で毎日確認する
  - Teamsをリンクしたい
- 多読：タイトル→アブストラクト→図→結論→手法
- 精読：論文を片面印刷して見開きの左ページに原稿，右ページにノートをとる
- 精読：LaTeXノートを作って式展開をすべて埋める

### 論文紹介のやり方

 <!-- `howto_review_paper.md` -->

- [kaityo256：論文紹介のやり方](https://speakerdeck.com/kaityo256/how-to-review)
- 論文を紹介する≠その論文の内容を完璧に披露する
- 論文を紹介する=大きな研究の文脈上にその論文を位置づける
- 論文のつながりを可視化できるサービスをリストする

### 輪講の準備

 <!-- `howto_lecture_textbook.md` -->

- [kaityo256：輪講の準備の仕方](https://speakerdeck.com/kaityo256/book-reading)

----

## 対外発表や原稿執筆関連

原稿を書くときに共通のtips：

- 何度も原稿を反復して徐々に全体の完成度を上げていくとよい．
  - ↔上から順に完成原稿を書こうとしない．
  - まず研究背景を完璧に書いて，次に手法を完璧に書いて，...はおすすめしない．
  - 全体の構造を決める→各部に書くキーワードを配置する→文章を書いていく...と反復しつつ原稿の細部を詰めていくほうがよい原稿になると思う．

### 進捗発表の準備

 <!-- `howto_present_progress.md` -->

- [kaityo256：研究発表の仕方](https://speakerdeck.com/kaityo256/happy-presentation)
- 進捗発表=いま詰まっている問題点の共有・議論
  - ↔進捗発表≠うまくいったことの報告

### 学会発表の準備

 <!-- `howto_prepare_conference_presentation.md` -->

学会スライドの作り方：

1. 一番主張したい結果を決める．
2. それに合わせて発表のストーリーを考える．
3. 1つのメッセージ/トピックを1枚のスライドに割り振り，全体の構成を決める．
  - 例：スライド1枚につき理解してほしい図を1つ載せる．
  - スライド枚数は（基本的に）1分/1枚とする．
    - 試問や公聴会は時間が短いので枚数が多くなってもよいが，わかりやすい構成にはじゅうぶん注意する．

学会発表の聞き方：

- 批判的に聞く
  - 自分がこの研究をしていたら何が気になるだろう？
- 「この人のスライド見やすいな」と思う発表者がどんな工夫をしているのかを観察する．
- 質疑応答中はどんな観点からの質問が出たか，同じ疑問を自分は持てたかを振り返る．
- ラボメートの発表での質疑はメモをとっておく．

懇親会の過ごし方：

- 発表に質問できなかった人と議論する．
- 自分の発表に質問してくれた人と議論する．
- 先輩・指導教員について回って他大の教員や院生を紹介してもらう．
- 同じ分野・同じ学年などでネットワークを作る．
- みんな「他大の人と話してみたいけどきっかけがないな...」と思っているのでがんがん話しかけに行く．

### 卒論・修論論文の書き方

 <!-- `howto_write_thesis.md` -->

- [卒業論文・修士論文の自己チェックリスト](https://github.com/ryo-ARAKI/lab_tutorial/blob/master/selfcheck_thesis.md)
  - 執筆した卒業論文や修士論文を指導教員に見てもらう前に確認しておくべきことのリスト．
- [卒業論文・修士論文発表スライドの自己チェックリスト](https://github.com/ryo-ARAKI/lab_tutorial/blob/master/selfcheck_defence.md)
  - 卒業論文や修士論文の口頭試問や公聴会で使うスライドを準備する際のチェックリスト．

### 投稿論文の書き方

 <!-- `howto_write_manuscript.md` -->

###  奨学金・研究費申請書の書き方

<!-- `howto_apply_grant.md` -->

- 「書けと言われていること」を書く．
- 模式図を効果的に使う．
- 審査員と共有できる前提・背景分野の知識を調べる．

----

## リンク集

- [kaityo256: lab_startup](https://github.com/kaityo256/lab_startup)
  - 慶応大・渡辺先生の研究室チュートリアル集
- [ryo-ARAKI: TIL](https://github.com/ryo-ARAKI/TIL)
  - 執筆者（荒木）が「今日学んだこと（Today I Learned：TIL）」をまとめているリポジトリ
