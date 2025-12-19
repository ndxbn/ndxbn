このディレクトリは、自分用のメモを適当においておく場所です。
運用に関することは、適宜専用のファイルを作るなり、ISSUE などの適当な機能やソリューションを使ってください。

## GitHub Pages や WebSite の使い分け

[個人アカウント](https://github.com/ndxbn) と [ndxbn.tokyo orgs](https://github.com/ndxbn-tokyo) を使い分ける基準は、orgs の profile を見てください。

- [`github.com/ndxbn/ndxbn/docs/`](https://github.com/ndxbn/ndxbn/tree/main/docs): 基本はここでいいかも。
- [ndxbn.github.io](https://ndxbn.github.io): public から手軽にダウンロードして使えるものを置いておく。 `rc.bash` とか。
- [ndxbn.tokyo](https://ndxbn.tokyo): 私個人の Main Web Site。
- [ndxbn-tokyo.github.io](https://ndxbn-tokyo.github.io): orgs 向けのドキュメント置き場。 `github.com/ndxbn/ndxbn/docs/` 相当かも？明確な「これをつかうっていう基準」は特に思いつかない。

| リポジトリ名          | Read/Write heavy | stability | Configure or Behavior |
| :-------------------- | ---------------- | --------- | --------------------- |
| ndxbn/ndxbn           | Write            | Devel     | Behavior              |
| ndxbn.github.io       | Read             | Devel     | Configure             |
| ndxbn.tokyo           | Read             | Prod      | Behavior              |
| ndxbn-tokyo.github.io | Write            | Prod      | Configure             |

こうやって見ると、ndxbn-tokyo.github.io が Write Heavy なことが他の要素と矛盾しており、使い道よくわからんと感じるのは正しいかも。

## `ndxbn.github.io` リポジトリについて

このリポジトリには、Gemini Gem で使っているプレプロンプトや、IDE の設定に関する情報、デスクトップの設定のバックアップなど、特定のリポジトリに依存しない、多岐にわたる様々なデータを置いています。それらのファイルは、利用する際には結局ブラウザからアクセスしてコピペするっていう手作業を伴うため、自分用のウェブサイトからも参照できるようにそのリポジトリにおいています。当然ですが、ターミナルや CLI ツールの設定であれば、 dotfiles リポジトリに置きます。

「これらのデータは、普段の私の行動や手癖に関するものが多いことなどから、知りたい人向けの自己紹介にもなり得る」っていうのも、ウェブサイト経由でアクセスできる場所においてる理由になるのかなーって後から思ったりもしました。

## リポジトリの運用・管理の方針

- `ndxbn/.github`: メタリポジトリ。テンプレートよりも抽象度が高い。Configure なので、Behavior な要素（Action の起動とか）は NG。
- `ndxbn/bun` や `ndxbn/php` などのテンプレート: 各言語で特有なファイルだけを置いておく。どこかからか持ってくる。ndxbn.github.io に置くのが正着か…？
- `ndxbn/node_modules`: `@ndxbn/` スコープのやつを置くモノレポ。
- `ndxbn-tokyo/node_modules`: スコープのないやつを置くモノレポ。
- PHP のライブラリ: `ndxbn/` アカウント以下にライブラリごとでリポジトリを作成。「開発はモノレポ、公開はポリレポ（Split-Repo）」。
