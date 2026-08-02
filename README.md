# environment

Macの開発環境を管理するリポジトリ。

## 管理方針

| 対象 | 管理方法 |
|---|---|
| macOS標準コマンド | macOS |
| 一般的なCLI | Homebrew |
| Node.js・npm・JS系CLI | Volta |
| プロジェクト依存 | 各プロジェクト内 |
| GUIアプリ | App Store または公式サイト |

## Homebrew

管理対象は `Brewfile` に記録する。

```sh
brew bundle --file=./Brewfile
````

現在の管理対象:

* gh
* tree

確認:

```sh
brew leaves --installed-on-request
brew bundle check --file=./Brewfile
```

更新:

```sh
brew update
brew upgrade
brew cleanup
```

## Volta

Node.js関連はVoltaで管理する。

```sh
export VOLTA_HOME="$HOME/.volta"
export PATH="$VOLTA_HOME/bin:$PATH"
```

```sh
volta install node
volta install pnpm
volta list all
```

Homebrewでは以下をインストールしない。

* node
* npm
* yarn
* pnpm
* nvm

## インストールルール

インストール前に確認する。

1. macOS標準で利用できないか
2. 既にインストールされていないか
3. HomebrewとVoltaで重複しないか
4. プロジェクトローカルで管理できないか

以下は事前確認なしで実行しない。

```sh
brew install
brew uninstall
brew upgrade
volta install
npm install -g
sudo
```

## 現在の環境

* Shell: macOS標準zsh
* Terminal: Apple Terminal
* Homebrew: gh, tree
* Node.js管理: Volta
* curl: macOS標準 `/usr/bin/curl`

## 削除済み

* Docker Desktop
* iTerm
* Oh My Zsh
* Microsoft Office / OneDrive
* Google日本語入力
* Karabiner-Elements
* Homebrew版curl
* nvm
