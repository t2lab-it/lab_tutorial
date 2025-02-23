# Ubuntu の初期設定とソフトウェアのインストール・設定

※完全な手順書ではなく備忘録に近いものなので，自身の環境に合わせて設定してください．

実行環境

```bash
$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 24.04 LTS
Release:	24.04
Codename:	noble
```

## OS を Windows から Ubuntu に変更する

1. すべての機能が正常に動作していることを確認する
   - キーボード，カメラ，指紋認証，Wi-Fi，Bluetooth，...
2. BIOS を最新版に更新する
3. Windows の BitLocker ドライブ暗号化を解除し，BIOS でセキュアブートを無効化しておく
4. Ubuntu の最新版をインストールする
   - [Ubuntu Desktop](https://jp.ubuntu.com/download)もしくは[Ubuntu Desktop 日本語 Remix](https://www.ubuntulinux.jp/download/ja-remix)

## OS 設定

1. システムを更新して再起動する

   ```bash
   sudo add-apt-repository -y ppa:apt-fast/stable
   sudo apt update
   sudo apt install -y apt-fast  # 並列apt
   sudo apt-fast -yV upgrade
   sudo apt-fast -yV dist-upgrade
   sudo apt-fast -yV autoremove
   sudo apt-fast autoclean
   sudo shutdown -r now
   ```

2. 必要なソフトウェアを追加する

   ```bash
   # 必須なもの
   sudo apt-fast-y install git  # バージョン管理
   sudo apt-fast-y install vim  # CUIエディタ
   sudo apt-fast-y install curl # データ送受信
   sudo apt-fast-y install cmake  # ビルドツール
   sudo apt-fast-y install build-essential  # ビルドツール
   sudo apt-fast-y install evince  # PDFビューワ
   sudo apt-fast-y install ffmpeg  # 画像処理
   sudo apt-fast-y install ubuntu-restricted-extras  # フォント・動画再生用コーデック
   sudo apt-fast-y install gnome-tweaks  # 詳細設定
   sudo apt-fast-y install gnome-shell-extension-manager  # Gnome Extensions
   sudo apt-fast-y install gnuplot  # 可視化
   sudo apt-fast-y install direnv  # 環境変数の設定
   # 個人の好み
   sudo apt-fast-y install terminator  # かっこいいターミナルエミュレータ
   sudo apt-add-repository ppa:fish-shell/release-3  # fishのリモートリポジトリを登録
   sudo apt-fast-y install fish  # モダンなシェル
   sudo apt-fast-y install peco  # CUI上のフィルタ
   sudo apt-fast-y install fonts-ipafont fonts-ricty-diminished && fc-cache -fv  # IPAフォント
   sudo apt-fast-y install unar  # ファイル解凍
   curl -fsSL https://install.julialang.org | sh  # Julia
   curl https://sh.rustup.rs -sSf | sh -s -- -y --no-modify-path  # Rust
   . "$HOME/.cargo/env"  # Rustのパスを通す
   cargo install --locked typst-cli  # LaTeXの代替になる新しい組版ソフト
   cargo install starship --locked  # プロンプト装飾
   cargo install git-delta  # gitの差分出力
   # 基本的なコマンドのRust再実装
   sudo apt-fast install bat  # catの代替
   sudo apt-fast install fd-find  # findの代替
   sudo apt-fast install ripgrep  # grepの代替
   cargo install du-dust  # duの代替
   cargo install eza  # lsの代替
   cargo install procs  # psの代替
   cargo install sd  # sedの代替
   ```

   TeXLive はすごく時間がかかるので暇なときにやる

   ```bash
   sudo apt-fast install texlive-full
   sudo kanji-config-updmap-sys haranoaji  # 日本語フォントとして原ノ味フォントを指定
   ```

3. （`.deb` から）必要なソフトウェアを追加する

   Chrome

   ```bash
   cd Downloads
   wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo dpkg -i google-chrome-stable_current_amd64.deb
   ```

   - VSCode：[公式サイト](https://code.visualstudio.com/Download)から deb 版をダウンロードしてインストールする（snap 版だと日本語環境が作れない）
     - To Do： `curl` や `wget` を使う方法を調べる
   - Zoom：[公式サイト](https://zoom.us/download?os=linux)から `zoom_amd64.deb` をダウンロードしてインストールする

4. ホームディレクトリ下の日本語ディレクトリを英語に変換する
   ※日本語 Remix をダウンロードした際のみ

   ```bash
   LANG=C xdg-user-dirs-gtk-update
   ```

5. 日本語入力を設定する

   - 参考：[Ubuntu 20.04 LTS：日本語環境にする](https://www.server-world.info/query?os=Ubuntu_20.04&p=japanese)
     - 注意：Mozc のデフォルト入力法を「直接入力」にするには `.config/mozc/ibus_config.textproto` に `active_on_launch: True` と追記すればよい．ソースを書き換えて再ビルドする必要はない

6. 時計合わせのサーバを NICT へ変更する

   ```bash
   sudo sed -i 's/#NTP=/NTP=ntp.nict.jp/g' /etc/systemd/timesyncd.conf
   ```

7. デスクトップ背景を単色にする

   - HTML カラーコードは例えば[日本の伝統色](https://nipponcolors.com/)から探す

   ```bash
   gsettings set org.gnome.desktop.background picture-options none
   gsettings set org.gnome.desktop.background color-shading-type 'solid'
   gsettings set org.gnome.desktop.background primary-color '#268785'  # 青碧
   ```

8. 設定アプリで調整する項目
   - Multitasking: Hot Corner: on
   - Multitasking: App Switching: Include apps from the curent workspace only
   - Appearance: Dark
   - Ubuntu Desktop: Show Home Folder: off
   - Ubuntu Desktop: Configure Dock Behavior: Show Trash: off
   - Ubuntu Desktop: Enhanced Tiling: off
   - Keyboard: Keyboard Shortcuts: Open the quick setting menu: disabled
   - Keyboard: Keyboard Shortcuts: Show the overview: Super+S
   - Accessibility: Seeing: Reduce Animation: on
   - Accessibility: Seeing: Large Text: on
   - Accessibility: Seeing: Cursor size: Medium
   - To Do：設定ファイルを gist に登録する
9. Gnome-tweaks で調整する項目
   フォント：インターフェースのテキスト：IPA P ゴシック Regular
   フォント：ドキュメントのテキスト：IPA P ゴシック Regular
   フォント：等幅テキスト：Monospace Regular
   キーボード：追加のレイアウトオプション：Caps Lock を追加の Control とする
   ウィンドウ：ウィンドウ操作キー：Alt
   ウィンドウ：ホバーでフォーカスを当てる
   キーボードとマウス：マウスクリックのエミュレーション：無効
10. [GitHub CLI](https://docs.github.com/ja/github-cli/github-cli/about-github-cli)を使った GitHub アカウントの認証

```bash
sudo apt-fast install gh
gh auth login
```

- Personal access tokens (classic)で最小権限（'repo', 'read:org', 'admin:public_key'）を選択して token を生成する
- To do：Fine-grained tokens での設定方法を調べる
- To do：差分の表示方法を変える

11. Git の設定

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

### To Do

- SSH 鍵の生成と登録
  - GitHub CLI で ed25519 プロトコルの鍵が生成されるのでこれを使い回せばよい
  - ※違うマシンでは違う鍵を使う

## 参考にしたページ

- [金子邦彦研究室：Ubuntu 22.04 のインストール直後の設定](https://www.kkaneko.jp/tools/ubuntu/ubuntu_setup.html)
- [@karaage0703：Ubuntu をちょっと使いやすくする設定集](https://qiita.com/karaage0703/items/705f1b750c486f00d554)
- 他にもいろいろなウェブサイトで Linux の設定が紹介されているが，各項目が自分にとって有益かどうかをよく考慮してから実行すること．

## 様々な設定ファイル

- [.bashrc](https://gist.github.com/ryo-ARAKI/d79182aa599dadf4b8549629a349511c)
  - bash shell の設定ファイル
- [config.fish](https://gist.github.com/ryo-ARAKI/9d5e85d7be10863d515850b2ce2182e3)
  - [fish shell](https://fishshell.com/) の設定ファイル
- [config](https://gist.github.com/ryo-ARAKI/f4031daf4d4c388838b123705aee8893)
  - ターミナルエミュレータである [Terminator](https://gnome-terminator.org/) の設定ファイル
- [starship.toml](https://gist.github.com/ryo-ARAKI/48a11585299f9032fa4bda60c9bba593)
  - ターミナルのプロンプトを装飾してくれる [Starship](https://starship.rs/) の設定ファイル
- [.gitconfig](https://gist.github.com/ryo-ARAKI/578c36fa78ee5e148d7452dcb12fbb3b)
  - Git の設定ファイル（非公開）
- [.screenrc](https://gist.github.com/ryo-ARAKI/07923755368e1f4ee0f67778a1cf2bca)
  - ターミナルエミュレーションソフトである [screen](https://www.gnu.org/software/screen/) の設定ファイル
- [.vimrc](https://gist.github.com/ryo-ARAKI/a9e64763c1f7d6eb1e210cb13388fd43)
  - エディタである [vim](https://www.vim.org/) の設定ファイル
- [keybindings.json & setting.json](https://gist.github.com/ryo-ARAKI/b4a54125e7922d2166f7fa7373c0f6dd)
  - エディタである [VSCode](https://code.visualstudio.com/) の設定ファイル
- [LaTeX `.sty`](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df)
  - LaTeX の設定ファイル
  - [mystyle.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle-sty)
  - [mystyle_jpn.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_jpn-sty) ：和文用設定ファイル
  - [mystyle_beamer.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_beamer-sty) ：Beamer 用設定ファイル
  - [mystyle_beamer_jpn.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_beamer_jpn-sty) ：和文 Beamer 用設定ファイル
  - [mystyle_biblatex.sty](https://gist.github.com/ryo-ARAKI/c4f55e2c4c57a5997700160cc6ea55df#file-mystyle_biblatex-sty) ： BibLaTeX 用設定ファイル
  - [.latexmkrc_revtex](https://gist.github.com/ryo-ARAKI/8a256ef600325b0344bbc3990818b691#file-latexmkrc_revtex) ：欧文コンパイル用設定ファイル
  - [.latexmkrc_uplatex](https://gist.github.com/ryo-ARAKI/8a256ef600325b0344bbc3990818b691#file-latexmkrc_uplatex) ：和文コンパイル用設定ファイル
  <!-- - [.xbindkeysrc](https://gist.github.com/ryo-ARAKI/b17adac7419087a8ae821ebd1b30cd81)
  - 多ボタンマウスの Linux 用設定ファイル
  - Logitech MX Master 2S
- [logid.cfg]()
  - マウスのボタン設定ファイル
  - Logitech MX Master 3S -->

## VSCode の設定

- 導入している拡張機能は以下の通り．先頭に `code --install-extension` をつけるとターミナルからインストールできる：

  ```bash
  $ code --list-extensions
  brunnerh.insert-unicode
  christian-kohler.path-intellisense
  donjayamanne.githistory
  eamodio.gitlens
  equinusocio.vsc-material-theme
  equinusocio.vsc-material-theme-icons
  esbenp.prettier-vscode
  fortran-lang.linter-gfortran
  ibm.output-colorizer
  james-yu.latex-workshop
  jprestidge.theme-material-theme
  julialang.language-julia
  kirozen.wordcounter
  marp-team.marp-vscode
  monokai.theme-monokai-pro-vscode
  mosapride.zenkaku
  ms-ceintl.vscode-language-pack-ja
  ms-python.debugpy
  ms-python.python
  ms-python.vscode-pylance
  ms-toolsai.jupyter
  ms-toolsai.jupyter-keymap
  ms-toolsai.jupyter-renderers
  ms-toolsai.vscode-jupyter-cell-tags
  ms-toolsai.vscode-jupyter-slideshow
  ms-vscode-remote.remote-ssh
  ms-vscode-remote.remote-ssh-edit
  ms-vscode.atom-keybindings
  ms-vscode.cpptools
  ms-vscode.remote-explorer
  nvarner.typst-lsp
  oderwat.indent-rainbow
  pkief.material-icon-theme
  sgryjp.japanese-word-handler
  shd101wyy.markdown-preview-enhanced
  streetsidesoftware.code-spell-checker
  torn4dom4n.latex-support
  vsls-contrib.gistfs
  yzhang.markdown-all-in-one
  ```

## GNOME shell extensions のリスト

- 設定ファイルは `~/.local/share/gnome-shell/extensions/` にあるが，単一のファイルではない（ので Gist 等に登録できない）
- 最初から入っている System extensions は Ubuntu Dock 以外をすべて off にしてよい

### [CoverflowAltTab](https://github.com/dmo60/CoverflowAltTab)

- Alt+Tab でのウィンドウ切り替えをより大きく表示する
- アプリアイコンのスタイル：オーバーレイ

### [Dash to Panel](https://github.com/home-sweet-gnome/dash-to-panel)

- アプリケーションランチャーとシステムトレイと融合する
- Install 後にエラーになるときは一度ログアウトしてサイドログインすれば直る

#### Position

- パネルを自動的に隠す：On
- Panel thickness: 64
- アプリケーションボタン：非表示
- アクティビティボタン：非表示
  - 設定アプリの「マルチタスク」で設定済
- デスクトップボタン：非表示

#### Style

- アプリのアイコンにマウスを当てたときのアニメーションを有効にする：On
- 実行中インジケーターの位置：上
- 実行中インジケーターのスタイル（フォーカス）：ソリッド
- 実行中インジケーターのスタイル（非フォーカス）：ダッシュ

#### Behavior

- アイコンをワークスペースごとに表示：On

### [Emoji Copy](https://github.com/FelipeFTN/Emoji-)

- 絵文字の検索

### [RunCat](https://github.com/win0err/gnome-runcat)

- CPU 負荷をグラフィカルに表示する
- Sleeping threshold = 20
- Displaying items = Character only

### [Tactile](https://t.co/jyTjYaAHvV)

- ウィンドウをタイル状に配置する
- Layout 1: 6×2（プライマリモニタ）
- Layout 2: 1×3（縦置きのサブモニタ）
- Advanced
  - Text color: #FEFAFB
  - Border color: #FED716
  - Background color: #26306B（半透明）
  - Grid size: 6×3
- 色は例えば[日本の伝統色](https://nipponcolors.com/)から探す

### おすすめ拡張機能を紹介している記事

- [Ubuntu 日和：拡張機能で GNOME Shell を派手にしたり便利にしたり](https://pc.watch.impress.co.jp/docs/column/ubuntu/1440667.html)（2022）
- [GNOME42 に対応したベストな 拡張機能 (失敗しない Linux のカスタマイズ)](https://www.gustavprogress.com/gnome42%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%9F%E3%83%99%E3%82%B9%E3%83%88%E3%81%AA-%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BD-%E5%A4%B1%E6%95%97%E3%81%97%E3%81%AA%E3%81%84linux%E3%81%AE%E3%82%AB/)（2022）
- [おすすめ GNOME Shell Extensions 11 選](https://sy-base.com/myrobotics/ubuntu/mybest_extensions/)（2017）
