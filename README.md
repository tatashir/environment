# environment

Macの開発環境を管理する

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
