# 研究室チュートリアル

## はじめに

この文章では，大学の研究室に所属する学生に向けたチュートリアルや役立つ情報をまとめています．
同様の目的で書かれた定評のある書籍に

- [E・M・フィリップス，D・S・ピュー著，角谷 快彦訳，「博士号のとり方［第6版］―学生と指導教員のための実践ハンドブック―」，名古屋大学出版局（2018）](https://www.unp.or.jp/ISBN/ISBN978-4-8158-0923-2.html)

があり，私自身も大学院時代に読んで非常に学ぶところが大きかったです．
私自身が博士後期課程に進学して大学教員としてのキャリアを進むにあたり，精神的な心構えを学んだのは

- [ピーター・Ｂ・メダワー著，鎮目 恭夫訳，「若き科学者へ （新版）」，みすず書房（2016）](https://www.msz.co.jp/book/detail/08530/)

という本です．
原著は1981年に出版された古い本ですが，その内容はいまも普遍的に通じるものだと思います．
博士後期課程への進学を少しでも考えている人は読んでみてください．
また，ネットで読める文章には

- [kaityo256: lab_startup](https://kaityo256.github.io/lab_startup/)
  <!-- - 慶応大・渡辺先生の研究室チュートリアル集です． -->
- [Hiroyuki Ohsaki：充実した大学・大学院生活のための 100 のヒント (草稿)](https://lsnl.jp/~ohsaki/research/100-tips/)
  <!-- - 関西学院大・大崎先生の研究室生活を充実させるためのヒント集です． -->
- [発声練習：卒業論文、修士論文関連のエントリー](https://next49.hatenadiary.jp/entry/20080105/p3)

などがあり，どれも非常に有用です．
この文章も，将来的にはこれらと並ぶような情報を提供できれば，という目標のもと書き足していく予定です．

なお，本稿の内容はあくまでも理工学系で流体力学，とくに乱流の理論・数値計算系の研究をしてきた執筆者（[荒木 亮@東京理科大学](https://ryo-araki.github.io/)）が自身の経験をもとにまとめたものなので，分野や大学が違うとまた異なる文化があると思います．
また，論文雑誌の例や使ってきたソフトウェアなども執筆者の専門分野に偏ったものになっていることに注意してください．

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

私はLinux（Ubuntu）を入れたPCを研究に使っています．
理論や数値計算系，とくに一日中サーバやスパコンにつないでいるのであれば，研究用のPCをLinuxにするのは考慮に値する選択肢だと思います（が，バイアスがかかっているかもしれません）．
実験系は装置の制御ソフトがWindowsのみだったりするので要注意です．

私のPCの初期設定やソフトウェアの設定は[Ubuntu日本語Remixの初期設定とソフトウェアのインストール・設定](PC_initial_setup.md)にまとめています．
また，ソフトウェアの設定ファイルはGistで管理しており，その一覧は以下にまとめています：

<details>
<summary>設定ファイルのリスト</summary>

- [config.fish](https://gist.github.com/ryo-ARAKI/9d5e85d7be10863d515850b2ce2182e3)
  - [fish shell](https://fishshell.com/) の設定ファイル
- [LaTeX `.sty`](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df)
  - LaTeX の設定ファイル
  - [mystyle.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle-sty)
  - [mystyle_jpn.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_jpn-sty) ：和文用設定ファイル
  - [mystyle_beamer.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_beamer-sty) ：Beamer 用設定ファイル
  - [mystyle_beamer_jpn.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_beamer_jpn-sty) ：和文 Beamer 用設定ファイル
  - [mystyle_biblatex.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_biblatex-sty) ： BibLaTeX 用設定ファイル
  - [.latexmkrc_revtex](https://gist.github.com/ryo-ARAKI/8a256ef600325b0344bbc3990818b691#file-latexmkrc_revtex) ：欧文コンパイル用設定ファイル
  - [.latexmkrc_uplatex](https://gist.github.com/ryo-ARAKI/8a256ef600325b0344bbc3990818b691#file-latexmkrc_uplatex) ：和文コンパイル用設定ファイル
- [setting.json](https://gist.github.com/ryo-ARAKI/b4a54125e7922d2166f7fa7373c0f6dd)
  - エディタである [VSCode](https://code.visualstudio.com/) の設定ファイル
- [.screenrc](https://gist.github.com/ryo-ARAKI/07923755368e1f4ee0f67778a1cf2bca)
  - ターミナルエミュレーションソフトである [screen](https://www.gnu.org/software/screen/) の設定ファイル
- [starship.toml](https://gist.github.com/ryo-ARAKI/48a11585299f9032fa4bda60c9bba593)
  - ターミナルのプロンプトを装飾してくれる [Starship](https://starship.rs/) の設定ファイル
- [config](https://gist.github.com/ryo-ARAKI/f4031daf4d4c388838b123705aee8893)
  - ターミナルエミュレータである [Terminator](https://gnome-terminator.org/) の設定ファイル
- [.vimrc](https://gist.github.com/ryo-ARAKI/a9e64763c1f7d6eb1e210cb13388fd43)
  - エディタである [vim](https://www.vim.org/) の設定ファイル
- [.xbindkeysrc](https://gist.github.com/ryo-ARAKI/b17adac7419087a8ae821ebd1b30cd81)
  - 多ボタンマウスの Linux 用設定ファイル
  - Logitech MX Master 2S

</details>

### 数値計算コードの書き方

どのような分野でも，数値計算を使って研究を進める人は

- [伊理 正夫，藤野 和建，「数値計算の常識」，共立出版（1985）](https://www.kyoritsu-pub.co.jp/book/b10011417.html)

を読んでおくと良いでしょう．
非常に古典的な本なので，例えば当時と現在で計算機の性能には雲泥の差がありますが，数値計算を使う人にとっては「常識」であるべき事柄がよくまとまっています．


使用する言語は「言語ありき」ではなく自分の目標を最も簡単に達成できるものを選べばよいですが，例えば研究室内で使っている人がいないものを選ぶといろいろとしんどいと思います．
なお，私がおもに使っている言語は：

- Fortran：スパコンを使う大規模並列計算およびポスト解析
- Python：ローカルのパソコンで可能なデータ処理およびMatplotlibを用いた可視化，グラフ作成
- Julia：テスト計算や簡単なモデルの数値計算とポスト解析

ですので，これらを使うのであればサポートができます．
その三言語の勉強方法について，[プログラミングの勉強](howto_learn_coding.md)にまとめているので参照してください．

> [!NOTE]
> TBA：
>
> - 写経・自分なりに改善しつつ再実装すると勉強になるオープンソースのリポジトリ
> - 「モダンな」数値計算ソフトウェアの開発環境
> - サーバの使い方（ログイン/ファイル移動/計算ジョブの投入/...）

#### 数値計算のtips

- プログラミング言語ごとのtipsは[ryo-ARAKI: TIL](https://github.com/ryo-ARAKI/TIL)にまとめています．
- ポスト処理でデータを解析するコードとデータをプロットするコードは分割する．

  論文を書く段階になると図の微妙な修正を何度もすることになるので，そのたびにデータの解析からやり直していては時間がかかります．
  そこで，ポスト解析を終えて「このデータをプロットすればよい」段階で一旦データを吐いておき，別のスクリプトでそれを読み込んでプロットすると，グラフの微修正が容易です．
  Pythonなら `.npy` ，MATLABなら `.mat` など，各プログラミング言語で効率的に扱えるバイナリ形式があるのでそれを使うとよいでしょう．
- 色覚多様性に配慮したカラーマップを使う．

  とくにMATLABのデフォルトは[Jetカラーマップ](https://jp.mathworks.com/help/matlab/ref/jet.html)という明度が線形に変化せず，赤と緑が同時に使われているひどいものです．
  できる限り[Perceptually Uniform Sequential Colormap](https://matplotlib.org/stable/users/explain/colors/colormaps.html#sequential)を使うようにしてください．
  なお，カラーマップの選び方と色覚多様性については，例えば以下の文献を参照してください：

  - [Crameri et al., "The misuse of colour in science communication", Nat. Comm. (2020)](https://doi.org/10.1038/s41467-020-19160-7)
  - [森下，「科学的・非科学的カラーマップ」，測地学会誌（2021）](https://doi.org/10.11366/sokuchi.67.29)
  - [文部科学省，「色覚に関する指導の資料」](https://www.pref.osaka.lg.jp/attach/2470/00004402/sikikaku.pdf)

### 研究や論文執筆でのGitHubの使い方

 <!-- `howto_use_git_for_research.md` -->

研究でプログラムや原稿といったテキスト形式のソースコードを編集するときは，必ずバージョン管理ソフトを使いましょう．
そのご利益にはさまざまなものがありますが（参考：[kaityo256: 数値計算屋のためのGit入門](https://speakerdeck.com/kaityo256/starting-git)），

- いつでも（自分でマークした）過去のバージョンに戻すことができる．
- 複数の機能を並行して実装したり複数人で並行して開発することができる．

が非常に大きいです．
バージョン管理ソフトにもさまざまなものがありますが，もっとも広く使われている[Git](https://git-scm.com/)/[GitHub](https://github.co.jp/)を使うのがよいと思います．
簡単な使い方をするだけでもいくつかのコマンド（ `git add/commit/push/fetch/pull` ）を覚える必要があって勉強が大変ですが，すこしずつ慣れていきましょう．
Git/GitHubは分散型バージョン管理であることから，ローカルのマシン以外にバックアップをとれることも利点です．
（研究室外のサーバにおいてはいけないデータを扱う際には[GitLab](https://about.gitlab.com/ja-jp/)などオンプレミスな環境を利用しましょう．）

- [kaityo256: GitHub演習](https://github.com/kaityo256/github)

をやれば，以下にまとめたような用途でGitHubを使うには十分だと思います．

#### 研究コードの管理

GitHubを使って

1. 「正常に動く」コードを `master/main` ブランチに置く．
2. 別ブランチで新しい機能の実装やリファクタリング，バグを取るコードを書く．
3. 新しいコードが正常に動作することを確認したら `master/main` ブランチにマージする．

を繰り返せば，常に正常に動作するコードを維持しつつ開発を進めることができます．
また，

- [Issue](https://docs.github.com/ja/issues)や[Pull Request](https://docs.github.com/ja/pull-requests)を使ってバグ報告や新たに実装したい機能を管理する．
- [GitHub Actions](https://docs.github.com/ja/actions)を使ってテストやビルドをおこないつつコードを開発する．
- [Wiki](https://docs.github.com/ja/communities/documenting-your-project-with-wikis/about-wikis)を使ってコードのドキュメントを維持する

など，GitHubの豊富な機能を使うとより効率的な開発ができるので，ぜひチャレンジしてみてください．

#### 研究ノートの管理

日々の研究ノートを[Markdown](https://docs.github.com/ja/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)で書いてGitHubでホストしておくと便利です．
Markdownとは「文書を記述するための軽量マークアップ言語のひとつ（Wikipedia）」  で，

- プレーンテキストで書ける（=Gitで管理できる）
- 見出し/箇条書き/強調表示など文章の構造化が容易である（WYSIWYGでない）
- 表/数式/図の挿入など拡張も可能である
- HTMLやPDFなどさまざまな形式へ変換できる

といった特徴をもちます．
この文章もMarkdownで書いたものをGitHubでホストしています．
この利点を活かし，例えば：

- 指導教員をcollaboratorに入れておき，進捗を可視化する．
- 研究ノートを抜粋したものを[Marp](https://marp.app/)や[Pandoc](https://pandoc.org/)でスライド化し，進捗報告の資料にする．
- 日頃から書き溜めておいた内容を卒論や修論のLaTeXにコピペする．

といった使い方が考えられます．

#### 論文執筆

LaTeXで論文を執筆する際も，GitHubを使って

1. Issueに書くべき内容を書き出し，執筆計画を建てる．
2. 別ブランチで執筆を進めたり共著者からの添削を反映する．
3. `latexdiff-vc` を使って `master/main` ブランチとの差分PDFを出力する．
4. 満足いくものになったら `master/main` ブランチにマージする．

というワークフローを踏むことで効率的な執筆が可能になります．
GitHubを利用した卒論・修論執筆について，

- [立命館大学情報理工学部サイバーセキュリティ研究室：卒業論文のためのGitHub運用法](https://cysec.ise.ritsumei.ac.jp/2024/01/08/thesis-git-repository/)
- [komatsuna4747：Git/GitHubを用いて論文を執筆する](https://komatsuna4747.github.io/how-to-use-git/writing-paper.html)

などが参考になると思います．

----

## 論文や教科書の読み方関連

### 乱流と情報理論の勉強方法

ここでは，私の指導のもとで研究を進める学生さんがどのように研究に向けた準備をしていくかをまとめます．
私の興味は乱流を情報理論の立場から理解することにあります．
そこで，学生さんには乱流と情報理論を勉強してもらうことになります．
それぞれ：

- [乱流の勉強](howto_learn_turbulence.md)
- [情報理論の勉強](howto_learn_information_theory.md)

を参照してください．
また，研究手段としては理論解析と数値計算を主とします（修士課程までは実験もやっていたのでまたやりたいところですが，いまのところ具体的なプロジェクトはありません）．
プログラミングについてはすでに[数値計算コードの書き方](#数値計算コードの書き方)で述べましたし，いくつかの言語の具体的な勉強方法は[プログラミングの勉強](howto_learn_coding.md)を参照してください．

### 論文の探し方

 <!-- `howto_survey_previous_research.md` -->

あるトピックの先行研究を知りたいときは以下の手順を踏むとよい：

1. 研究室の中で探す
   1. 知っていそうな先輩に聞く：その分野の重要な研究者・論文や「分野の流れ」を教えてもらえるかもしれません．
   2. 研究室の既発表論文を調べる：わからないときに教員や先輩に訪ねやすい．
   3. 関連する分野の教科書を読む：その分野を創始した論文や重要な発展に寄与した原著論文が引用されているはず．
2. レビュー論文を探す

   レビュー論文：原著論文と教科書の中間の立ち位置で「あるトピックの過去数年〜数十年の進展」をまとめた論文のこと．
   分野の概観をつかみやすいので，教科書の次には（あるいは教科書がないような分野なら最初に）読むのがおすすめです．
   流体力学分野だとまずは[Annual Review of Fluid Mechanics](https://www.annualreviews.org/journal/fluid)で探すとよいでしょう．
   分野が違う人は[Annual Reviews系列](https://www.annualreviews.org/action/showPublications)から探すとよいと思います．
   他に流体力学（を含む物理学）系のレビューが載る雑誌には，

   - Annual Reviews系列の[Annual Review of Condensed Matter Physics](https://www.annualreviews.org/journal/conmatphys)
   - Nature系列の[Nature Reviews Physics](https://www.nature.com/natrevphys/)
   - American Physics Society（APS）系列の[Review of Modern Physics](https://journals.aps.org/rmp/)
   - Elsevier系列の[Physics Reports](https://www.sciencedirect.com/journal/physics-reports)

   などがあります．
1. 原著論文を探す

   流体力学分野で定評のある雑誌には

   - Cambridge University Pressの[Journal of Fluid Mechanics](https://www.cambridge.org/core/journals/journal-of-fluid-mechanics)
   - APSの[Physical Review Fluids](https://journals.aps.org/prfluids/)
   - American Institute of Physics（AIP）の[Physics of Fluids](https://pubs.aip.org/aip/pof)
   - 日本流体力学会の[Fluid Dynamics Research](https://iopscience.iop.org/journal/1873-7005)

   などがあります．
   <!-- Physical Review Letters/Physical Review E/Physical Review Research/Physica D/New Journal of Physics/... -->

異なる論文雑誌から横断的に論文を探せるサイトは：

- [Google scholar](https://scholar.google.co.jp/)

  「その論文を引用した論文」を網羅的に探しやすく，LaTeXで文献を引用する際に必要な `.bib` ファイルも（出版社のサイトでダウンロードできるものより）使いやすいと思う．
  お金を払わないと読めない論文もなんやかんや本文を読めるリンクが辿れたりします．
- [arXiv](https://arxiv.org/)

  査読を経て出版される前のプレプリントが読めますが，「正式に出版された原稿」ではないことに注意しましょう（出版された論文では細部が変わっていることがよくあります）．
  お金を払わないと読めない雑誌の論文も草稿段階の原稿がアップされていたりするので，うまく使いましょう．
  [arXiv Xplorer](https://arxivxplorer.com/)で効率的に検索できます．

  流体力学関連は[physics.flu-dyn](https://arxiv.org/list/physics.flu-dyn/recent)の新着論文をチェックしていればよいです．
- [Perplexity](https://www.perplexity.ai/)，[Elicit](https://elicit.org/)，[Typeset](https://typeset.io/)，[Consensus](https://consensus.app/)

  知りたいトピックを尋ねると **存在する** 文献を挙げてくれるAIを使ったウェブサイトです．
  なお，ChatGPTは存在しない文献を実在するかのように紹介してくるので，論文探しには使わないようにしましょう．
  他にもいろいろ便利なサービスが出てきているはずなので，見つけたら教えてください．
- [Connected Papers](https://www.connectedpapers.com/)

  論文を入力すると，その関連論文の相関図を出してくれます．
  そのトピックの研究を概観したいときに便利ですが，無料版だとかなり厳しい回数制限があるので注意しましょう．

新しい論文を効率的にチェックするためには，上に挙げた雑誌の新着論文をRSS通知で毎日確認するとよいです．
研究室のチャットツール（Slack，Teams等）にRSS通知をリンクすると，チャット上で議論することもできて有用だと思います（参考：[Slack に RSS フィードを追加する](https://slack.com/intl/ja-jp/help/articles/218688467-Slack-%E3%81%AB-RSS-%E3%83%95%E3%82%A3%E3%83%BC%E3%83%89%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B)）．

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

- A4一枚に背景，解いた問題，手法，主要なデータ，結論などをまとめる．
- 論文を片面印刷して見開きの左ページに原稿，右ページにノートをとる．
- LaTeXノートを作って式展開をすべて埋める．

などの方法があると思います．

### 論文紹介の準備方法

 <!-- `howto_review_paper.md` -->

研究室内での論文紹介の目的は，[論文の読み方](#論文の読み方)の繰り返しになりますが，その論文の内容を完璧にプレゼンすることよりも大きな研究の文脈上にその論文を位置づけることにあります（参考：[kaityo256：論文紹介のやり方](https://speakerdeck.com/kaityo256/how-to-review)）．

スライドづくりの一例：

1. 白紙のスライドに論文の図表を1枚/1スライドずつ貼る．
2. それぞれの図の考察をまとめ，スライドに書きこむ．
3. 理論など，図表以外の重要な情報のスライドを追加する．
4. 重要な先行研究を調べ，文脈の理解に必要な図などを引用したスライドを追加する．
5. 全体構成を見直し，本筋でないスライドを補遺に回す．

### 輪講の準備方法

 <!-- `howto_lecture_textbook.md` -->

輪講では，教科書をただ読み上げるのではなく，教科書の内容を自分なりに再構成して講義できるように準備しましょう（参考：[kaityo256：輪講の準備の仕方](https://speakerdeck.com/kaityo256/book-reading)）．

輪講資料づくりの一例：

1. 教科書の該当範囲（とそれ以前の範囲）を読み，議論の流れを把握する．
2. その教科書以外の資料を参照して内容を自分なりに再解釈する．
3. 式展開や論理展開の行間を埋める．

----

## 研究の進め方

### 日々の研究室生活の過ごし方

> [!NOTE]
> TBA：
>
> - 研究室に来て議論する
> - まずは手を動かしてみる
> - よい検索の方法
>   - 参考になるウェブサイト
>   - ChatGPTとのつきあい方
> - 研究の効率化に役立つツールやソフト
>
>   私は，こまごました研究上のtipsを[ryo-ARAKI: TIL](https://github.com/ryo-ARAKI/TIL)（TIL："Today I Learned"，今日学んだこと）にまとめています．
>   皆さんも同様のリポジトリを作って「何度も参照するけどそのたびにググるのが面倒なこと」などをまとめておくと便利です．
> - 先輩，指導教員へのよい質問のしかた
> - 指導教員以外のメンターをもつ
>   - できれば他大学の教員（指導教員の共同研究者）や院生（学会や夏の学校でつながりをつくる），最低でも研究室の先輩で自分のテーマを深く議論できる人
>   - フランスの博士後期課程では毎年所属の異なる研究者と進捗を議論し，指導教員抜きの場で抱えている困難や指導教員との関係について話す場があり，とてもよかった
> - 自律した研究者を目指す
>
>   「自分で立てる」ではなく「自分を律することができる」ようになってほしい．

### 進捗報告の準備方法

 <!-- `howto_present_progress.md` -->

研究を始めると，指導教員やメンターの先輩，ラボメートと定期的なミーティングをすることになると思います（参考：[kaityo256：研究発表の仕方](https://speakerdeck.com/kaityo256/happy-presentation)，[発声練習：良い進捗報告のやり方](https://next49.hatenadiary.jp/entry/20100528/p1)）．
進捗報告では，うまくいった進捗と同程度にいま詰まっている問題点を共有し，その解決策を議論することを心がけましょう．
進捗報告の資料は次のように構成するとよいでしょう：

1. 前回の進捗報告と，そこでの議論のまとめ
2. 前回の進捗報告で述べた「今後の研究計画」
3. 今回報告するトピックの一覧
4. それぞれのトピックで
   1. 何を目的として
   2. 何を実行して
   3. 何が得られて
   4. どう評価・考察したのか

   をまとめる．
5. 次回の進捗報告までの研究計画

資料を作る際は以下のことに気をつけましょう：

- 資料作りに時間をかけすぎない．

  決まったテンプレートに図やグラフを並べたもので十分ですし，必要ならそこに手書きで書き込みを入れても構いません．
  [Markdownでまとめた研究ノート](#研究ノートの管理)を[Marp](https://marp.app/)や[Pandoc](https://pandoc.org/)でスライド化するのもよいと思います．
- 資料は事前に指導教員やミーティング参加者に（PDF形式で）共有する．
  ミーティング後には議論した内容を資料に追記し，これも共有するようにしましょう．

----

## 対外発表や原稿執筆関連

原稿を書くときに共通のtips：

- [木下是雄，「理科系の作文技術」，中公新書（1981）](https://www.chuko.co.jp/shinsho/1981/09/100624.html)を読む．

  明快な文章を書くために必要なことがまとまっている古典的な本です．
  ある程度まとまった文章を初めて書く前に必ず読んでほしいです．
- 読者層を規定してから書き始める．

  その原稿を読む人のレベルや分野（学部生/院生/研究者，そのトピックの専門家/同じ分野の人/違う分野の人）から，どこまでを前提条件としてよいかを考える．
- 上から順に完成原稿を書こうとせず，何度も反復して徐々に全体の完成度を上げていくとよい．

  全体の構造を決める→各部に書くキーワードを配置する→文章を書いていく...と反復しつつ原稿の細部を詰めていくほうがよい原稿になると思う．

Gist で管理しているLaTeXテンプレートのリンク集を以下にまとめています：

<details>
<summary>LaTeXテンプレート</summary>

- [latex_template.tex](https://gist.github.com/ryo-ARAKI/9aa9ce4f0fab42a758e1370ad1eb4487#file-latex_template-tex) ：和文のテンプレート
- [beamer_template.tex](https://gist.github.com/ryo-ARAKI/9aa9ce4f0fab42a758e1370ad1eb4487#file-beamer_template-tex) ：スライドのテンプレート
- [beamer_template_poster.tex](https://gist.github.com/ryo-ARAKI/9aa9ce4f0fab42a758e1370ad1eb4487#file-beamer_template_poster-tex) ：ポスターのテンプレート
- [beamer_template_flash_talk.tex](https://gist.github.com/ryo-ARAKI/9aa9ce4f0fab42a758e1370ad1eb4487#file-beamer_template_flash_talk-tex) ：フラッシュトークのテンプレート
- [standalone_figure.tex](https://gist.github.com/ryo-ARAKI/9aa9ce4f0fab42a758e1370ad1eb4487#file-standalone_figure-tex) ：TikZ を用いたスタンドアロン図のテンプレート

</details>

### 学会発表の準備方法

 <!-- `howto_prepare_conference_presentation.md` -->


> [!NOTE]
> TBA：
>
> - なんのために学会発表をするのか？
> - 発表する学会をどう決めるか？

#### 発表タイトルの決め方

学会参加者はプログラムを見て気になる（聞きに行きたい）発表を決めるので，魅力的なタイトルをつけることは非常に重要です．
タイトルの付け方の一例：

1. 研究のキーワードをさまざまな視点からブレイン・ストームして書き出す．
   - 対称とする系，計算手法，注目するパラメータ，物理現象，応用先，...
2. それらをいろいろに組み合わせて，発表内容をもっともよく表すタイトル候補を考える．
   - 単語に形容詞をくっつけていく，何かを主張する文にする，...

学会発表のタイトルがどんなものかわからない，という人は先輩や指導教員に過去の発表タイトルについて尋ねてみてください．
自分が参加する学会の昨年度のプログラムを参考にするのもよいと思います．

#### 発表要旨の書き方

学会によって長さは異なりますが，申込み時に要旨，あるいは講演原稿や予稿と呼ばれる数百字〜数ページの文章を書く必要があります．
これは，タイトルを見て興味を持ってくれた人が発表を聞く前の予習として，あるいは発表を聞きながらその詳細を理解するために読む文章になります．
短いものは投稿論文のアブストラクト，長いものは短めの投稿論文の書き方を参考にするとよいでしょう（参考：[投稿論文の書き方](#投稿論文の書き方)）．
また，自分が参加する学会の昨年度の予稿集を参考にするのもよいと思います．

#### 学会スライドの作り方

普段の進捗報告と異なり，学会発表では

- 研究背景を必ずしも共有しない
- 自分の話を初めて聞く

聴衆を想定して発表する必要があります．
そこで，次の手順を踏んで発表スライドの第ゼロ稿を作るとよいでしょう：

1. 一番主張したい結果を決める．
2. 想定聴衆を設定する．
3. それらに合わせて発表のストーリーを考える．
4. 1つのメッセージ/トピックを1枚のスライドに割り振り，全体の構成を決める．
   - 例：スライド1枚につき理解してほしい図を1つ載せる．
   - スライド枚数は（基本的に）1分/1枚とする．
   <!-- - 試問や公聴会は時間が短いので枚数が多くなってもよいが，わかりやすい構成にはじゅうぶん注意する． -->
5. 各スライドに「それ単体で内容を理解するのに十分な」情報を書く．
6. まとめスライドに"Take-home message"を書く
   - 「ご清聴ありがとうございました」スライドは **絶対に** 使わない．

#### 学会ポスターの作り方

> [!NOTE]
> TBA：
>
> - ポスターの作り方
>   - 単体で理解できるように必要な情報をすべて盛り込む．
>   - アピールするトピックを絞って強調する．
>
> ポスターのtips：
>
> - ヘッダーに自分の顔写真を入れておく．
>   自分がポスターのそばにいないときに興味を持ってくれた人とあとで繋がれる確率を上げるため．
> - 追加資料へのリンクをQRコードにして入れておく．
>   例えば動画や三次元可視化，プレプリントなど，研究に興味を持ってもらえた人にアピールするための素材をリンクするとよい．

#### 学会発表の聞き方

学会に参加するときは，まずウェブサイトや当日の受付でもらえるプログラムをみて聞きたい発表に印を着けましょう．
場合によっては発表ごとにセッションを移動することになるかもしれません．

発表を聞くときは，批判的に（criticalに）聞くことを心がけましょう．
これは発表の粗さがしをしながら聞くということではなく，

- 自分がこの研究をしていたら何が気になるだろうか？
- 自分の研究に役立てられる知見はあるだろうか？

といった点を頭の隅におきながら聞く，ということです．
そうすると，質問も自然に浮かんでくると思います．
質疑応答中は，自分で積極的に質問するのと同時に他の聴衆からどんな観点からの質問が出たか，同じ疑問を自分は持てたかを振り返りながら議論に参加しましょう．

また，ラボメートが発表する際はどんな質問が出たか，ラボメートがどんな返答をしていたかのメモをとっておきましょう．
発表者は質問への対応でいっぱいいっぱいになってしまい，どんな質問が出たか，自分がどう返答したかも覚えていないことがあります！

この他に，「この人のスライド見やすいな/発表聞きやすいな」と思う発表者がスライドのデザインや発表にどんな工夫をしているのかを観察するのもとても大事です．

#### 懇親会の活用方法

学会の懇親会は，場合によっては学会のセッションと同じくらい大事です．
というのも，ここで作ったネットワークで共同研究が始まったり進学先，就職先が決まったりということが起きうるからです．
なので，懇親会でラボメートとずっと一緒にいるのは非常にもったいない過ごし方だと思います．
例えば：

- 発表に質問できなかった人と議論する．
- 自分の発表に質問してくれた人と議論する．
- 先輩・指導教員について回って他大の教員や院生を紹介してもらう．
- 同じ分野・同じ学年の院生さんを見つけてネットワークを作る．

などを目標にするとよいでしょう．
参加者はみんな「他大学の人と話してみたいけどきっかけがないな...」と思っているのでがんがん話しかけに行って大丈夫です．

### 卒論・修論論文の書き方

 <!-- `howto_write_thesis.md` -->

> [!NOTE]
> TBA：
>
> 執筆した卒業論文や修士論文，その口頭試問や公聴会で使うスライドを指導教員に見てもらう前に確認しておくべきことのチェックリスト：
>
> - [卒業論文・修士論文の自己チェックリスト](selfcheck_thesis.md)
> - [卒業論文・修士論文発表スライドの自己チェックリスト](selfcheck_defence.md)

### 投稿論文の書き方

 <!-- `howto_write_manuscript.md` -->

> [!NOTE]
> TBA
>
> - なんのために論文を書くのか？
> - 投稿する雑誌をどう決めるか？

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

Natureの[How to construct a _Nature_ summary paragraph](https://www.nature.com/documents/nature-summary-paragraph.pdf)という記事が非常に参考になると思います．

#### 本文の書き方

> [!NOTE]
> TBA

###  奨学金・研究費申請書の書き方

<!-- `howto_apply_grant.md` -->

> [!NOTE]
> TBA：
>
> - 「書けと言われていること」を書く．
> - 模式図を効果的に使う．
> - 審査員と共有できる前提・背景分野の知識を調べる．

----

## リンク集

以下の博士後期課程を終えた先達のブログ記事も参考になると思います：

- [A Survival Guide to a PhD](https://karpathy.github.io/2016/09/07/phd/)
- [Twenty things I wish I’d known when I started my PhD](https://doi.org/10.1038/d41586-018-07332-x)
  - 日本語訳：[研究生活の心構えー修士課程、博士課程に進学したあなたへー](https://www.chem-station.com/chemistenews/research/2019/03/phd.html)
- [What not to do in graduate school](https://doi.org/10.1038/d41586-019-02255-7)
- [Lessons from my PhD](https://austinhenley.com/blog/lessonsfrommyphd.html)
- [10 Tips for Research and a PhD](https://www.ruder.io/10-tips-for-research-and-a-phd/)
