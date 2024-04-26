# Ubuntuの初期設定とソフトウェアのインストール・設定

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

## OSをWindowsからUbuntuに変更する

1. すべての機能が正常に動作していることを確認する
   - キーボード，カメラ，指紋認証，Wi-Fi，Bluetooth，...
2. BIOSを最新版に更新する
3. WindowsのBitLockerドライブ暗号化を解除し，BIOSでセキュアブートを無効化しておく
5. Ubuntuの最新版をインストールする
   - [Ubuntu Desktop](https://jp.ubuntu.com/download)もしくは[Ubuntu Desktop 日本語 Remix](https://www.ubuntulinux.jp/download/ja-remix)

## OS設定

1. システムを更新して再起動する

   ```bash
   sudo apt -y update
   sudo apt -yV upgrade
   sudo apt -yV dist-upgrade
   sudo apt -yV autoremove
   sudo apt autoclean
   sudo shutdown -r now
   ```

2. 必要なソフトウェアを追加する

   ```bash
   # 必須なもの
   sudo apt -y install git  # バージョン管理
   sudo apt -y install vim  # CUIエディタ
   sudo apt -y install curl # データ送受信
   sudo apt -y install cmake  # ビルドツール
   sudo apt -y install build-essential  # ビルドツール
   sudo apt -y install evince  # PDFビューワ
   sudo apt -y install ffmpeg  # 画像処理
   sudo apt -y install ubuntu-restricted-extras  # フォント・動画再生用コーデック
   sudo apt -y install gnome-tweaks  # 詳細設定
   sudo apt -y install gnome-shell-extension-manager  # Gnome Extensions
   # 個人の好み
   sudo apt -y install terminator  # かっこいいターミナルエミュレータ
   sudo apt -y install fish  # モダンなシェル
   sudo apt -y install peco  # CUI上のフィルタ
   sudo apt -y install fonts-ipafont fonts-ricty-diminished && fc-cache -fv  # IPAフォント
   sudo apt -y install unar  # ファイル解凍
   curl -fsSL https://install.julialang.org | sh  # Julia
   curl https://sh.rustup.rs -sSf | sh -s -- -y --no-modify-path  # Rust
   . "$HOME/.cargo/env"  # Rustのパスを通す
   cargo install starship --locked  # プロンプト装飾
   cargo install exa  # lsの代替
   ```

   TeXLiveはすごく時間がかかるので暇なときにやる

   ```bash
   sudo apt install texlive-full
   ```

3. （`.deb` から）必要なソフトウェアを追加する

   Chrome
   ```bash
   cd Downloads
   wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo dpkg -i google-chrome-stable_current_amd64.deb
   ```

   - VSCode：[公式サイトから](https://code.visualstudio.com/Download)deb版をインストールする（snap版だと日本語環境が作れない）
     - To Do： `curl` や `wget` を使う方法を調べる

4. ホームディレクトリ下の日本語ディレクトリを英語に変換する
   ※日本語 Remixをダウンロードした際のみ

   ```bash
   LANG=C xdg-user-dirs-gtk-update
   ```

5. 日本語入力を設定する
   - 参考：[Ubuntu 20.04 LTS：日本語環境にする](https://www.server-world.info/query?os=Ubuntu_20.04&p=japanese)
     - 注意：Mozcのデフォルト入力法を「直接入力」にするには `.config/mozc/ibus_config.textproto` に `active_on_launch: True` と追記すればよい．ソースを書き換えて再ビルドする必要はない

6. 時計合わせのサーバをNICTへ変更する

   ```bash
   sudo sed -i 's/#NTP=/NTP=ntp.nict.jp/g' /etc/systemd/timesyncd.conf
   ```

7. デスクトップ背景を単色にする
   - HTMLカラーコードは例えば[日本の伝統色](https://nipponcolors.com/)から探す

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
   - To Do：設定ファイルをgistに登録する
9.  Gnome-tweaksで調整する項目
   フォント：インターフェースのテキスト：IPA Pゴシック Regular
   フォント：ドキュメントのテキスト：IPA Pゴシック Regular
   フォント：等幅テキスト：Monospace Regular
   キーボード：追加のレイアウトオプション：Caps Lockを追加のControlとする
   ウィンドウ：ウィンドウ操作キー：Alt
   ウィンドウ：ホバーでフォーカスを当てる
   キーボードとマウス：マウスクリックのエミュレーション：無効
10. [GitHub CLI](https://docs.github.com/ja/github-cli/github-cli/about-github-cli)を使ったGitHubアカウントの認証
   ```bash
   sudo apt install gh
   gh auth login
   ```
   - Personal access tokens (classic)で最小権限（'repo', 'read:org', 'admin:public_key'）を選択してtokenを生成する
   - To do：Fine-grained tokensでの設定方法を調べる
   - To do：差分の表示方法を変える

### To Do

- SSH鍵の生成と登録
  - GitHub CLIでed25519プロトコルの鍵が生成されるのでこれを使い回せばよい
  - ※違うマシンでは違う鍵を使う

## VSCodeの設定

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

## 参考にしたページ

- [金子邦彦研究室：Ubuntu 22.04 のインストール直後の設定](https://www.kkaneko.jp/tools/ubuntu/ubuntu_setup.html)
- [@karaage0703：Ubuntuをちょっと使いやすくする設定集](https://qiita.com/karaage0703/items/705f1b750c486f00d554)
- 他にもいろいろなウェブサイトでLinuxの設定が紹介されているが，各項目が自分にとって有益かどうかをよく考慮してから実行すること．
