# lab_tutorial

## はじめに

この文章では，大学の研究室に初めて所属する学生さんに向けたチュートリアルや役立つ情報をまとめています．
同様の目的で書かれた定評のある書籍に

- [E・M・フィリップス，D・S・ピュー著，角谷 快彦訳，「博士号のとり方［第6版］―学生と指導教員のための実践ハンドブック―」，名古屋大学出版局（2018）](https://www.unp.or.jp/ISBN/ISBN978-4-8158-0923-2.html)

があり，私自身も大学院時代に読んで非常に学ぶところが大きかったです．
また，ネットで読める文章には

- [kaityo256: lab_startup](https://github.com/kaityo256/lab_startup)
  - 慶応大・渡辺先生の研究室チュートリアル集です．
- [Hiroyuki Ohsaki：充実した大学・大学院生活のための 100 のヒント (草稿)](https://lsnl.jp/~ohsaki/research/100-tips/)
  - 関西学院大・大崎先生の研究室生活を充実させるためのヒント集です．
- [発声練習：卒業論文、修士論文関連のエントリー](https://next49.hatenadiary.jp/entry/20080105/p3)

などがあり，どれも非常に有用です．
この文章も将来的にはこれらと並ぶような情報を提供できれば，という目標のもと少しずつ書き足していく予定です．

## 目次

- [PC・ソフトウェア関連](#PC・ソフトウェア関連)
- [論文や教科書の読み方関連](#論文や教科書の読み方関連)
- [研究の進め方](#研究の進め方)
- [対外発表や原稿執筆関連](#対外発表や原稿執筆関連)
- [リンク集](#リンク集)

----

## PC・ソフトウェア関連

### PCの設定方法

 <!-- `howto_setup_PC.md` -->

- Linuxの設定方法
  - [執筆者（荒木）の初期設定](https://github.com/ryo-ARAKI/TIL/blob/master/linux/initial_setup.md)
  - SSH/GitHub/VSCode/...の設定方法

### 数値計算コードの書き方

 <!-- `howto_develop_numerical_simulation_code.md` -->

- ポスト処理でデータを解析するコードとデータをプロットするコードは分割する．
  - 論文を書く段階になると図の微妙な修正を何度もすることになるので，そのたびにデータの解析からやり直していては時間がかかる．
  - ポスト解析を終え，「このデータをプロットすればよい」段階で一旦データを吐いておき，別のスクリプトでそれを読み込んでプロットする．
    - Pythonなら `.npy` ，MATLABなら `.mat` など，各プログラミング言語で効率的に扱えるバイナリ形式があるのでそれを使う．
- 色覚多様性に配慮したカラーマップを使う．
  - とくにMATLABは[Jetカラーマップ](https://jp.mathworks.com/help/matlab/ref/jet.html)が規定でひどい．
  - [Perceptually Uniform Sequential Colormap](https://matplotlib.org/stable/users/explain/colors/colormaps.html#sequential)を使う．

### 研究や論文執筆でのGit/GitHubの使い方

 <!-- `howto_use_git_for_research.md` -->

- [数値計算屋のためのGit入門](https://speakerdeck.com/kaityo256/starting-git)
- 研究コード：Issue/Pull Requestを使って「常に動く」コードを `main` ブランチに置く
- 論文：別ブランチで執筆や添削の反映→ `latexdiff-vc` を使って `main` ブランチとの差分PDFを出力する

----

## 論文や教科書の読み方関連

### 論文の探し方

 <!-- `howto_survey_previous_research.md` -->

あるトピックの先行研究を知りたいときは以下の手順を踏むとよいでしょう：

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
  - 査読を経て出版される前のプレプリントが読めるが，「正式に出版された原稿」ではないことに注意する．
  - お金を払わないと読めない論文も草稿段階の原稿がアップされていたりする．
  - 流体力学関連は[physics.flu-dyn](https://arxiv.org/list/physics.flu-dyn/recent)をみればよい．
  - [arXiv Xplorer](https://arxivxplorer.com/)で効率的に検索できる．
- [Perplexity](https://www.perplexity.ai/)，[Elicit](https://elicit.org/)，[Typeset](https://typeset.io/)，[Consensus](https://consensus.app/)
  - 知りたいトピックを尋ねると **存在する** 文献を挙げてくれる．
  - ChatGPTは存在しない文献を紹介してくるので論文探しには使わないこと．
  - 他にもいろいろ便利なサービスが出てきているはずなので，見つけたら教えてください．
- [Connected Papers](https://www.connectedpapers.com/)
  - 注目したい論文を入力すると，関連論文の相関図を出してくれる．
  - 無料版だとかなり厳しい回数制限があるので注意．

新しい論文を効率的にチェックするためには，上に挙げた雑誌の新着論文をRSS通知で毎日確認するとよいです．
研究室のチャットツール（Slack，Teams等）にRSS通知をリンクすると，チャット上で議論することもできて有用だと思います．

### 論文の読み方

<!-- `howto_read_paper.md` -->

研究をするにあたって論文を読む習慣をつけることはきわめて重要です．
論文を読む際は，その研究の詳細を理解するのと同じくらい，大きな研究の流れにその論文を位置づけることが大切です．
すなわち，[kaityo256：論文の読み方](https://speakerdeck.com/kaityo256/how-to-survey)にあるようにその論文を中心にしたより古い&新しい論文の樹形図を作ることを目標に論文を読むことが大切です．
<!-- そのためには，その論文が引用している&その論文を引用している文献を反復的に渉猟することが必要です． -->

論文を読む際，私は

1. タイトル（で論文のリンクを踏むかどうかを決める）
2. アブストラクト（で本文を読むかどうかを決める）
3. 図（を順に見ていってどんな系を対象にしているのか，どんな量を解析しているのかを確認する）
4. 結論（で自分が図から把握した議論と整合しているかを確認する）
5. 結果・考察（で詳しい結果の議論と考察をフォローする）
6. 手法（で理論的な背景をフォローする）

という順で読んでいます．
これ以外にもいろいろな読み方があるので，自分にあった方法を見つけてください．

読んだ論文は自分の言葉でまとめておくと，卒論や修論でレビューする際にとても役に立ちます．
いろいろな人が論文のまとめ方を紹介していますから，自分にあった方法を見つけるとよいでしょう．
例えば：

- A4一枚に背景，解いた問題，手法，主要なデータ，結論などをまとめる
- 論文を片面印刷して見開きの左ページに原稿，右ページにノートをとる
- LaTeXノートを作って式展開をすべて埋める
- TBA

などの方法があると思います．

### 論文紹介のやり方

 <!-- `howto_review_paper.md` -->

研究室内での論文紹介の目的は，[論文の読み方](#論文の読み方)の繰り返しになりますが，その論文の内容を完璧にプレゼンすることよりも，大きな研究の文脈上にその論文を位置づけることにあります（参考：[kaityo256：論文紹介のやり方](https://speakerdeck.com/kaityo256/how-to-review)）．

スライドづくりの一例：

1. 博士のスライドに論文の図表を1枚/1スライドごとに貼る
2. それぞれの図で主張されていることをまとめ，スライドに書きこむ
3. 図表以外の重要な情報を追加する
4. 重要な先行研究を調べ，文脈の理解に必要な図などを加える
5. 全体構成を見直し，本筋でないスライドを補遺に回す

### 輪講の準備方法

 <!-- `howto_lecture_textbook.md` -->

- [kaityo256：輪講の準備の仕方](https://speakerdeck.com/kaityo256/book-reading)

輪講資料づくりの一例：

1. 教科書の該当範囲（とそれ以前の範囲）を読み，議論の流れを把握する
2. その教科書以外の資料を参照して内容を自分なりに再解釈する
3. 式展開や論理展開の行間を埋める

- 輪講資料には教科書と同じことを書かないよう注意する

----

## 研究の進め方

### 研究時間のマネジメント方法

- [ryo-ARAKI: TIL](https://github.com/ryo-ARAKI/TIL)
  - 私が「今日学んだこと（Today I Learned：TIL）」をまとめています．
  - 皆さんも同様のリポジトリを作って「何度も参照するけどそのたびにググるのが面倒なこと」などをまとめておくと便利です．

### 進捗報告の準備方法

 <!-- `howto_present_progress.md` -->

研究を始めると，指導教員やメンターの先輩，ラボメートと定期的なミーティングをすることになると思います．
忙しい先生とはなかなか話す時間が取れませんから，以下の点に注意して効率的に議論を進められるようにしましょう：

- [kaityo256：研究発表の仕方](https://speakerdeck.com/kaityo256/happy-presentation)
- 進捗報告ではいま詰まっている問題点を共有し，その解決策を議論する．
  - 進捗報告では，うまくいったことの報告よりむしろうまくいかなかった点の議論に時間を使いましょう．
- 資料作りに時間をかけすぎない．
  - 進捗をうむ研究ではなく，その報告資料の準備に時間をかけすぎるのは非常にもったいないです．
  - 資料は決まったテンプレートに図やグラフを並べたものでよいですし，必要ならそこに手書きで書き込みを入れても構いません．
  - 指導教員は前回の議論の内容を忘れていますから，資料の冒頭に前回の議論のまとめをつけるとよいと思います．
  - 作った資料は事前に指導教員やミーティング参加者に（PDF形式で）共有しましょう．また，ミーティング後には議論した内容を資料に追記し，これも共有するようにしましょう．
- とれたデータだけでなく，その解釈も考えておく．
  - 「こんなデータが取れました」だけでは「そこからどんな物理がわかるの？」となるので，データはつねに解釈と同時に提示するようにしましょう．
<!-- - 直近のn週間でやったこと/詰まったことだけでなく，次のn週間でやりたいことも考えておく -->

----

## 対外発表や原稿執筆関連

原稿を書くときに共通のtips：

- 何度も原稿を反復して徐々に全体の完成度を上げていくとよい．
  - ↔上から順に完成原稿を書こうとしない．
  - まず研究背景を完璧に書いて，次に手法を完璧に書いて，...はおすすめしない．
  - 全体の構造を決める→各部に書くキーワードを配置する→文章を書いていく...と反復しつつ原稿の細部を詰めていくほうがよい原稿になると思う．

### 学会発表の準備方法

 <!-- `howto_prepare_conference_presentation.md` -->

#### 発表タイトルの決め方

学会参加者はプログラムを見て気になる（聞きに行きたい）発表を決めるので，魅力的なタイトルをつけることは非常に重要です．
タイトルの付け方の一例：

1. 研究のキーワードをさまざまな視点からブレイン・ストームして書き出す
   - 対称とする系，計算手法，注目するパラメータ，物理現象，応用先，...
2. それらをいろいろに組み合わせて，発表内容をもっともよく表すタイトル候補を考える
   - 単語に形容詞をくっつけていく，何かを主張する文にする，...

学会発表のタイトルがどんなものかわからない，という人は先輩や指導教員に過去の発表タイトルについて訪ねてみるとよいでしょう．
自分が参加する学会の昨年度のプログラムを参考にするのもよいと思います．

#### 発表要旨の書き方

学会によって長さは異なりますが，申込み時に要旨，あるいは講演原稿や予稿と呼ばれる数百字〜数ページの文章を書く必要があります．
これは，タイトルを見て興味を持ってくれた人が発表を聞く前の予習として，あるいは発表を聞きながらその詳細を理解するために読む文章になります．
短いものは投稿論文のアブストラクト，長いものは短めの投稿論文の書き方を参考にするとよいでしょう（参考：[投稿論文の書き方](#投稿論文の書き方)）．

#### 学会スライドの作り方

普段の進捗報告と異なり，学会発表では

- 研究背景を必ずしも共有しない
- 自分の話を初めて聞く

聴衆を想定して発表する必要があります．
そこで，次の手順を踏んで発表スライドの第ゼロ稿を作るとよいでしょう：

1. 一番主張したい結果を決める．
2. それに合わせて発表のストーリーを考える．
3. 1つのメッセージ/トピックを1枚のスライドに割り振り，全体の構成を決める．
   - 例：スライド1枚につき理解してほしい図を1つ載せる．
   - スライド枚数は（基本的に）1分/1枚とする．
   <!-- - 試問や公聴会は時間が短いので枚数が多くなってもよいが，わかりやすい構成にはじゅうぶん注意する． -->
4. 各スライドに「それ単体で内容を理解するのに十分な」情報を書く．

#### 学会発表の聞き方

学会に参加するときは，まずウェブサイトや当日の受付でもらえるプログラムをみて聞きたい発表に印を着けましょう．
場合によっては発表ごとにセッションを移動することになるかもしれません．

発表を聞くときは，批判的に（criticalに）聞くことを心がけましょう．
これは発表の粗さがしをしながら聞くということではなく，

- 自分がこの研究をしていたら何が気になるだろうか？
- 自分の研究に役立てられる知見はあるだろうか？
- TBA

といった点を頭の隅におきながら聞く，ということです．
そうすると，質問も自然に浮かんでくると思います．
質疑応答中は，自分で積極的に質問するのと同時に他の聴衆からどんな観点からの質問が出たか，同じ疑問を自分は持てたかを振り返りながら議論に参加しましょう．

また，ラボメートが発表する際はどんな質問が出たか，ラボメートがどんな返答をしていたかのメモをとっておきましょう．
発表者は質問への対応でいっぱいいっぱいになってしまい，どんな質問が出たか，自分がどう返答したかも覚えていないことがあります！

この他に，「この人のスライド見やすいな/発表聞きやすいな」と思う発表者がスライドのデザインや発表にどんな工夫をしているのかを観察するのもとても大事です．

#### 懇親会の過ごし方

学会の懇親会は，場合によっては学会のセッションと同じくらい大事です．
というのも，ここで作ったネットワークで共同研究が始まったり進学先，就職先が決まったりということが起きうるからです．
なので，懇親会でラボメートとずっと一緒にいるのは非常にもったいない過ごし方だと思います．
例えば：

- 発表に質問できなかった人と議論する．
- 自分の発表に質問してくれた人と議論する．
- 先輩・指導教員について回って他大の教員や院生を紹介してもらう．
- 同じ分野・同じ学年の院生さんを見つけてネットワークを作る．

などを目標にするとよいでしょう．
参加者はみんな「他大の人と話してみたいけどきっかけがないな...」と思っているのでがんがん話しかけに行って大丈夫です．

### 卒論・修論論文の書き方

 <!-- `howto_write_thesis.md` -->

- [卒業論文・修士論文の自己チェックリスト](https://github.com/ryo-ARAKI/lab_tutorial/blob/master/selfcheck_thesis.md)
  - 執筆した卒業論文や修士論文を指導教員に見てもらう前に確認しておくべきことのリスト．
- [卒業論文・修士論文発表スライドの自己チェックリスト](https://github.com/ryo-ARAKI/lab_tutorial/blob/master/selfcheck_defence.md)
  - 卒業論文や修士論文の口頭試問や公聴会で使うスライドを準備する際のチェックリスト．

### 投稿論文の書き方

 <!-- `howto_write_manuscript.md` -->

#### 論文タイトルの決め方

[論文の探し方](#論文の探し方)で紹介したような方法で論文を検索すると，まずはタイトルのキーワードから読むか読まないかを決めると思います．
すなわち，論文の内容を適切に表した魅力的なタイトルをつけることは自分の研究をアピールする上で非常に重要です．
基本的には学会発表のタイトルと同じように考えればよいので，[発表タイトルの決め方](#発表タイトルの決め方)を参考にするとよいでしょう．

#### アブストラクトの書き方

論文のアブストラクトは，タイトルで興味を持ってくれた人が本文を読むかどうかを決めるために読む大切な文章です．
基本的には以下の構成に従って，各項目を1〜2文ずつ書いていくとよいでしょう：

1. 分野の背景と問題の定義
2. 詳しい動機と先行研究
3. リサーチクエスチョン
4. 研究手法
5. 主結果とその詳細
6. インパクトと将来への展開

#### 本文の書き方

TBA

###  奨学金・研究費申請書の書き方

<!-- `howto_apply_grant.md` -->

- 「書けと言われていること」を書く．
- 模式図を効果的に使う．
- 審査員と共有できる前提・背景分野の知識を調べる．

----

## リンク集

- [ピーター・Ｂ・メダワー著，鎮目 恭夫訳，「若き科学者へ （新版）」，みすず書房（2016）](https://www.msz.co.jp/book/detail/08530/)
  - 私自身が博士後期課程に進学して大学教員としてのキャリアを進むにあたり，精神的な心構えを学んだ本です．

以下の博士後期課程を終えた先達のブログ記事も参考になると思います：

- [A Survival Guide to a PhD](https://karpathy.github.io/2016/09/07/phd/)
- [Twenty things I wish I’d known when I started my PhD](https://doi.org/10.1038/d41586-018-07332-x)
  - 日本語訳：[研究生活の心構えー修士課程、博士課程に進学したあなたへー](https://www.chem-station.com/chemistenews/research/2019/03/phd.html)
- [What not to do in graduate school](https://doi.org/10.1038/d41586-019-02255-7)
- [Lessons from my PhD](https://austinhenley.com/blog/lessonsfrommyphd.html)
- [10 Tips for Research and a PhD](https://www.ruder.io/10-tips-for-research-and-a-phd/)
