# プログラミングの勉強

ここでは，プログラミングの具体的な勉強方法についてまとめます．

<!--
目次：

- [プログラミングの勉強](#プログラミングの勉強)
  - [Julia](#julia)
  - [Fortran](#fortran)
  - [Python](#python)
 -->

## Julia

私は B4 でまず勉強する言語として Julia をおすすめします．
これは MIT の研究者によって開発が進められ，2018 年にバージョン 1.0 が公開された新しい言語です．
開発に際しての基本的な理念として「貪欲」というキーワードがあり，既存の言語のさまざまな利点を取り込もうとしてきました．
公式ブログの"[Why We Created Julia](https://julialang.org/blog/2012/02/why-we-created-julia/)"という文章にその意図がまとめられているのでぜひ読んでみてください．
Julia の勉強法としては，まず

- [JuliaLang.org: Getting Started](https://docs.julialang.org/en/v1/manual/getting-started/)
- [進藤 裕之，佐藤 建太，「1 から始める Julia プログラミング」，コロナ社（2020）](https://www.coronasha.co.jp/np/isbn/9784339029055/)
  - ただし Julia v1.2 というやや古いバージョンに基づいて書かれていることに注意してください．
- [永井 佑紀，「Julia ではじめる数値計算入門」，技術評論社（2024）](https://gihyo.jp/book/2024/978-4-297-14128-8)

などで基本的な使い方や数値計算の基礎を学んだのち，

- [永井 佑紀，「1 週間で学べる！ Julia 数値計算プログラミング」，講談社（2021）](https://www.kspub.co.jp/book/detail/5282823.html)（[サポートページ](https://cometscome.github.io/YukiNagai/ja/books/greenjulia/)）
<!--
- [小高 知宏「Julia による数値計算とシミュレーション」，オーム社（2023）](https://www.ohmsha.co.jp/book/9784274230493/)
  -->

などでさまざまな数値計算プログラムを組んでみると一通り使えるようになるのではないでしょうか．
とくに数値流体解析については

- [CFD_Julia](https://github.com/surajp92/CFD_Julia)（解説論文：[Pawar & San, Fluids (2019)](https://doi.org/10.3390/fluids4030159)）
- [CFD-Julia-12-steps-to-Navier-Stokes](https://github.com/Wallace-dyfq/CFD-Julia-12-steps--o-Navier-Stokes-Equations)（[CFD Python](https://github.com/barbagroup/CFDPython)の Julia 言語移植版）

に追加機能を加えたりリファクタリングしつつ再実装するのがとてもいい勉強になると思います．

この他にも，公式サイトの

- [チュートリアルのリンク集](https://julialang.org/learning/tutorials/)
- [Julia を利用した講義のリンク集](https://julialang.org/learning/classes/)

から膨大な資料を入手できますし，検索すれば日本語の講義資料や記事もでてくると思います．
ただし，使われているバージョンに注意して「古い」書き方を学んでしまわないように注意しましょう．
最近出版された和書や開催されたワークショップの動画

- [佐藤 建太，「Julia プログラミング大全」，講談社（2023）](https://www.kspub.co.jp/book/detail/5318195.html)
- [後藤 俊介，「実践 Julia 入門」，技術評論社（2023）](https://gihyo.jp/book/2023/978-4-297-13350-4)
- [九州大学，「数学と物理における Julia の活用」（2023）](https://joint.imi.kyushu-u.ac.jp/post-14811/)とその[動画](https://joint.imi.kyushu-u.ac.jp/post-9030/)
<!--
- 降籏 [数値計算法基礎 (2023)](http://www.cas.cmc.osaka-u.ac.jp/~paoon/Lectures/2023-8Semester-NA-basic/)
- Hiroi [お気楽 Julia プログラミング超入門](http://www.nct9.ne.jp/m_hiroi/light/julia.html)
  -->

も参考になると思います．

Julia を使った大規模数値計算はまだ資料が少ないですが，阪大の[SQUID](http://www.hpc.cmc.osaka-u.ac.jp/squid/)システムを使った以下の記事

- [宮武 勇登，「SQUID で Julia プログラミング」，サイバーメディア HPC ジャーナル（2022）](https://ir.library.osaka-u.ac.jp/repo/ouka/all/89337/hpc12_003.pdf)

が参考になります．

## Fortran

Fortran を使って大規模な並列数値計算を実行したい人は，まず

- [牛島 省，「数値計算のための Fortran90/95 プログラミング入門(第 2 版)」，森北出版（2020）](https://www.morikita.co.jp/books/mid/084722)，
  <!-- - 演習問題の解答・解説書もあるそうです． -->
- [Amano，「Fortran 演習 （地球惑星物理学演習）」](https://amanotk.github.io/fortran-resume-public/index.html)

などを読んで言語を一通り学んだのち，

- [片桐 孝洋，「スパコンプログラミング入門：並列処理と MPI の学習」，東京大学出版局（2013）](https://www.utp.or.jp/book/b306506.html)（著者による[サポートページ](http://abc-lib.org/TodaiSuppankai/index.html)）
- [青山，「並列プログラミング虎の巻 MPI 版」](https://www.hpci-office.jp/documents/HPC_Programming_Seminar/mpi-all_20160801_20181206.pdf)
- [東京大学情報基盤センター，「講習会教育教材」](https://www.cc.u-tokyo.ac.jp/events/lectures/materials/)
  - [MPI「超」入門（FORTRAN 編）](https://www.cc.u-tokyo.ac.jp/events/lectures/13/MPIprogf.pdf)
  <!--
- [MPI リファレンス](http://www.cv.titech.ac.jp/~hiro-lab/study/mpi_reference/index.html)
- JAMSTEC [Fortran90 講座](https://www.jamstec.go.jp/es/jp/simschool/f90learning/index.html)の 7 章
  -->

などを読んで並列計算の勉強をしましょう．

- 神戸大学の [HPC サマースクール](http://www.eccse.kobe-u.ac.jp/simulation_school/)
- 理研の配信講義 [計算科学技術特論](https://www.r-ccs.riken.jp/outreach/schools/20230413-1/)（リンクは 2023 年度版）
- 大阪大学サイバーメディアセンターの [講習会・セミナー](http://www.hpc.cmc.osaka-u.ac.jp/lecture_event/)
- [計算物理 春の学校](https://compphysspringschool2024.github.io/homepage2024/)（リンクは 2024 年開催）

へ参加するのもよいと思います．

## Python

Python を使った数値計算や可視化・グラフ作成については膨大な書籍や Web サイトが存在します．
私が勉強した本よりも新しいバージョンの Python に基づいた良質なコンテンツがあるはずなので，自分に合うものを選んで勉強してください（良いものを見つけたら教えてください）．

- [Numpy](https://numpy.org/ja/)，[Scipy](https://scipy.org/)，[Pandas](https://pandas.pydata.org/)など数値計算，データ処理のためのライブラリ
- [Matplotlib](https://matplotlib.org/)などデータ可視化のためのライブラリ

を勉強すると良いと思います．
とくに数値流体解析については

- [CFD Python](https://github.com/barbagroup/CFDPython)（解説論文[Barba and Forsyth, Journal of Open Source Education (2018).](https://doi.org/10.21105/jose.00021)）

に追加機能を加えたりリファクタリングしつつ再実装するのがとてもいい勉強になると思います．

<!--
- 中久喜「科学技術計算のためのPython入門 ――開発基礎、必須ライブラリ、高速化」，技術評論社（2016）
-->
