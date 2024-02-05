# Ubuntu日本語Remixの初期設定とソフトウェアのインストール・設定

実行環境

```linux
$ lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 22.04.3 LTS
Release:	22.04
Codename:	jammy
```

## OSをWindowsからUbuntuに変更する

1. すべての機能が正常に動作していることを確認する
   - キーボード，カメラ，指紋認証，Wi-Fi，Bluetooth，...
2. BIOSを最新版に更新する
3. Ubuntuの最新のLTSをインストールする

## OS設定

1. システムを更新して再起動する

   ```linux
   sudo apt -y update
   sudo apt -yV upgrade
   sudo apt -yV dist-upgrade
   sudo apt -yV autoremove
   sudo apt autoclean
   sudo shutdown -r now
   ```

2. 必要なソフトウェアを追加する・不要なソフトウェアを削除する

   ```linux
   sudo apt -y install git
   sudo apt -y install curl
   sudo apt -y install vim
   sudo apt -y install evince  # PDFビューワ
   sudo apt -y install ffmpeg  # 画像処理
   sudo apt -y install terminator  # かっこいいターミナルエミュレータ
   sudo apt -y install fish  # モダンなシェル
   sudo apt -y install ubuntu-restricted-extras  # フォント・動画再生用コーデック
   sudo apt install -y fonts-ipafont && fc-cache -fv  # IPAフォント
   sudo apt -y install gnome-tweaks  # 詳細設定
   sudo apt -y install gnome-shell-extension-manager  # Gnome Extensions
   sudo apt -y purge thunderbird*  # デフォルトのメーラー
   ```

3. ホームディレクトリ下の日本語ディレクトリを英語に変換する

   ```linux
   $ LANG=C xdg-user-dirs-gtk-update
   ```

4. 日本語入力のため `fcitx-mozc` をインストールし，設定する

   ```linux
   $ sudo apt -y install fcitx-mozc
   $ im-config -n fcitx
   $ fcitx-configtool mozc &
   ```

5. 時計合わせのサーバをNICTへ変更する

   ```linux
   $ sudo sed -i 's/#NTP=/NTP=ntp.nict.jp/g' /etc/systemd/timesyncd.conf
   ```

6. デスクトップにゴミ箱を表示する

   ```linux
   $ gsettings set org.gnome.shell.extensions.ding show-trash true
   ```

7. デスクトップ背景を単色にする
   - HTMLカラーコードは例えば[日本の伝統色](https://nipponcolors.com/)から探す

   ```linux
   $ gsettings set org.gnome.desktop.background picture-uri ''
   $ gsettings set org.gnome.desktop.background color-shading-type 'solid'
   $ gsettings set org.gnome.desktop.background primary-color '#268785'  # 青碧
   ```

8. 設定アプリで調整する項目
   - スタイル：暗い（色は好みで）
   - マルチタスク：ホットコーナーを有効化する
   - 電源管理：バッテリー残量を表示する
9. Gnome-tweaksで調整する項目
   - ウィンドウ：ウィンドウ操作キー：Alt
   - ウィンドウ：ホバーでフォーカスを当てる
   - キーボードとマウス：追加のレイアウトオプション：Caps LockをControlとして扱う
   - キーボードとマウス：マウスクリックのエミュレーション：無効
   - トップバー：曜日
   - フォント：インターフェースのテキスト：IPA Pゴシック Regular 11
   - フォント：ドキュメントのテキスト：IPA Pゴシック Regular 11
   - フォント：等幅テキスト：Monospace Regular 13
   - フォント：レガシーなウィンドウタイトル：IPA Pゴシック Bold 11

### To Do

1. SSHの設定
   - 鍵の生成，登録
2. Git/GitHub
   - SSHでなくGitHub CLIで設定する

## VSCodeのインストールと設定

- snap版ではなくdeb版をインストールすること（前者だと日本語環境が作れない）
- 設定ファイルは[ソフトウェアの設定ファイル](https://github.com/ryo-ARAKI/TIL?tab=readme-ov-file#%E8%A8%AD%E5%AE%9A%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB)を参照せよ
- 導入している拡張機能は以下の通り：

  ```linux
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
