# ガイドライン

GitHub の Issue および Pull Request の書き方についてのガイドライン。

## Markdown

`Prettier` でフォーマットする。
ファイル保存時に自動フォーマットするようにしておく。

```config
"[markdown]": {
    "editor.formatOnSave": true
}
```

## プレフィックス

視認性を高めるためコミットメッセージや _Pull Request_ で使用する。

| Prefix       | Description                                                            |
| ------------ | ---------------------------------------------------------------------- |
| **feat**     | 新しい機能                                                             |
| **fix**      | バグ修正                                                               |
| **docs**     | ドキュメント **のみ** の変更                                           |
| **style**    | コードの目的に影響しない変更（空白やフォーマットなど）                 |
| **refactor** | バグの修正や機能の追加を **行わない** コードの変更                     |
| **pref**     | パフォーマンス改善のためのコード変更                                   |
| **test**     | テストの追加・修正                                                     |
| **chore**    | ビルドプロセスやツール、ライブラリの変更（ドキュメント生成ツールなど） |

## Issue & Pull Request

テンプレートを作成する。

GitHub ではそれぞれのテンプレートファイルをプロジェクトルート直下に配置、
または `.github/` ディレクトリに配置すれば、_Issue_ ないし _Pull Request_ の作成時にテンプレートが挿入される。
（なお BitBucket では現在未対応。）

Example:

- [.github/ISSUE_TEMPLATE.md](.github/ISSUE_TEMPLATE.md)
- [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md)

また _Pull Request_ の場合はタイトルにプレフィックスをつける。

参考:

- [チームタスクを 3 倍スムーズに進める Git/Github のコメントフォーマット](https://www.wantedly.com/companies/kurashicom/post_articles/92756)
- [stevemao/github-issue-templates: A collection of GitHub issue and pull request templates](https://github.com/stevemao/github-issue-templates)
- [pull request, issue の雛形](https://qiita.com/yoichi22/items/1116d338e29b38d2de8e)

### Pull Request の些細な修正

`git rebase` の使用について合意が取れていること前提。

_typo_ の修正など単純ミスについての修正はコミットに残したくない。
でも既存コミットを修正して `git push -f` すると、Pull Request で修正箇所がわからなくなって悲しい。

よって `fixup` コミットと `git rebase` を使う方法。

1. 単純なミスの修正には `fixup` コミットを利用
1. マージできるようになったら `git rebase` によりコミットを整理
1. 整理したコミットを `git push -f` であげなおす

参考:

- [Pull Request の指摘修正でコミットログが汚れていく問題への対処法の一案](https://qiita.com/thinca/items/44ff57ed56a1f8c7efa2)

## コミット

- コミットメッセージにおいて先頭にプレフィックスをつける

- コミットメッセージのフォーマット

  タイトルおよび本文の後には空白行を入れる。

  ```txt
  <prefix>: <subject>

  <body>

  <#issue_num>
  ```

参考：

- [angular.js/DEVELOPERS.md](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#type)
- [【今日からできる】コミットメッセージに 「プレフィックス」 をつけるだけで、開発効率が上がった話](https://qiita.com/numanomanu/items/45dd285b286a1f7280ed)

## バッジ

こういう ![badge](https://img.shields.io/badge/badge-sample-blue) バッジをペタペタ貼ってシャレオツにしたい。

下記のフォーマットで自分独自のバッジを作成できる。
`<LABEL>` や `<MESSAGE>` は省略可能。

- `https://img.shields.io/badge/<LABEL>-<MESSAGE>-<COLOR>`

参考:

- [Shields.io: Quality metadata badges for open source projects](https://shields.io/)
- [プルリクエストへのコメントでは Text Blaze でラベルバッジをつけよう！](https://qiita.com/iganin/items/aee297eade84849cc9cd)
