# 情報理論の勉強

情報系でない人が情報理論を勉強するときは，まず

- [予備校のノリで学ぶ「大学の数学・物理」，「【サプライズ】物理学のための情報理論入門 @東京理科大学」](https://youtu.be/mPU-7gGjp5Q?si=3gT90-fvMZg3ZpUw)

を観て Shannon エントロピや相互情報量といった基本的な量をしっかり理解しましょう．
その際，

- [甘利「情報理論」，ちくま学芸文庫（2011）](https://www.chikumashobo.co.jp/product/9784480093585/)の 1 章
- [沙川「非平衡統計力学」，共立出版（2022）](https://www.kyoritsu-pub.co.jp/book/b10012378.html)の補遺 A

を傍らに置いておくとさらに良いでしょう．
他に日本語で読めるまとまった資料として

- [シャノン「通信の数学的理論」，ちくま学芸文庫（2009）](https://www.chikumashobo.co.jp/product/9784480092229/)
- 伊藤「非平衡科学」の[講義資料](https://sosuke110.com/noneq-phys.pdf)

などがあります．
情報理論で登場するいろいろな量は，紙とペンでの導出と並行して実際のデータを触りながら勉強していくと理解が進むと思います．
そこで，

- Java [Java Information Dynamics Toolkit (JIDT)](https://jlizier.github.io/jidt/)
- Julia [CausalityTools.jl](https://juliadynamics.github.io/CausalityTools.jl/dev/)
- Python [dit: discrete information theory](https://dit.readthedocs.io/en/latest/)

などのパッケージを使って教科書に出てきた例を実装しながら勉強するのをおすすめします．

英語が苦でない人は，2023 年の Les Houches サマースクールでのチュートリアル講義

- [Tohme & Bialek, "A brief tutorial on information theory", SciPost Physics Lecture Notes (2023)](https://arxiv.org/abs/2402.16556)

が対話形式で書かれており，おすすめです．
また，教科書として出版される予定の

- [Falkovich, "Physical Nature of Information"](https://www.weizmann.ac.il/complex/falkovich/sites/complex.falkovich/files/uploads/PNI22.pdf)
- [Y. Polyanskiy and Y. Wu. "Information Theory: From Coding to Learning," Cambridge University Press](https://people.lids.mit.edu/yp/homepage/papers.html)（[出版社のページ](https://www.cambridge.org/highereducation/books/information-theory/CFF2F02ED54398148B7D8AA26E55B2BC)）

の二冊も気になっています．
前者は物理現象とのつながり，後者はコーディングに重点が置かれているようです．

最後に，この分野で有名な教科書に

- [Cover & Thomas "Elements of Information Theory" 2nd Edition, Eiley-Interscience (2006)](https://onlinelibrary.wiley.com/doi/book/10.1002/047174882X)
  - [山本，古賀，有村，岩本（訳） 「情報理論―基礎と広がり」，共立出版（2012）](https://www.kyoritsu-pub.co.jp/book/b10008178.html)

がありますが，大著なので通読するというよりも気になったトピックを調べる辞書として使うのがよいと思います．
