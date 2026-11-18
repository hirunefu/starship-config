# starship-config

[starship](https://starship.rs/) 用の2行プロンプトの設定です。配色は Tokyo Night で、色が切り替わる所を矢印の形でつないでいます。

```
╭─[ ユーザー名 か (venv) ][ ディレクトリ ][ (ブランチ stash数) か 時刻 ]
╰─❯
```

## 表示される内容

1行目には左から次の3つが並びます。

- ユーザー名: Python の仮想環境が有効なときは、ユーザー名の代わりに `(仮想環境の名前)` を出します。
- ディレクトリ: 今いるディレクトリのパスを省略せずに出します。書き込みできないディレクトリでは鍵のアイコンが付きます。
- git の情報か時刻: git リポジトリの中ではブランチ名と stash の数を出します。ブランチではなくコミットを直接チェックアウトしているときは、コミットのハッシュとタグを出します。リポジトリの外では時刻を出します。

2行目は `╰─❯` です。直前のコマンドが失敗すると `❯` が赤くなります。

時刻の表示には bash だけを使い、git や date のコマンドは起動しません。

## 必要なもの

- starship（1.27.0 で動作を確認しています）
- [Nerd Font](https://www.nerdfonts.com/)（アイコンと区切りの矢印に使います）
- bash 4.2 以降（時刻の表示に使います。macOS に最初から入っている bash 3.2 では、時刻が出ません）

## 使い方

`~/.config/starship.toml` がすでにある場合は、先に別の名前に変えておいてください。そのあと、次のコマンドを実行します。

```sh
git clone https://github.com/hirunefu/starship-config.git
ln -s "$PWD/starship-config/starship.toml" ~/.config/starship.toml
```

リンクではなくコピーしても使えます。

色を変えたいときは、`[palettes.tokyo_night]` の値を書き換えてください。

## クレジット

この設定は ViegPhunt さんの oh-my-posh のテーマ [viet.omp.json](https://github.com/ViegPhunt/Dotfiles/blob/main/.config/ohmyposh/viet.omp.json)（MIT License, Copyright (c) 2025 ViegPhunt）を、starship 用に作り直したものです。区切りのつなぎ方は starship 公式の [tokyo-night プリセット](https://starship.rs/presets/tokyo-night) を参考にしました。

## ライセンス

[MIT](LICENSE)
