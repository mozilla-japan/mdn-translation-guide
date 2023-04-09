# 6. 日本語記事ページを編集する

## 5. の手順をスキップした場合（編集の場合） {#local-preview}

- 例えば https://developer.mozilla.org/ja/docs/Glossary/Entity を編集する手順は以下の通りです。

```
// translated-content ディレクトリへ移動する
[~] $ cd ~/path/to/mdn_repos/translated-content

// main ブランチにいることを確認する
[translated-content] $ git branch

// ls しながら、URL に対応するディレクトリへ移動する
[translated-content] $ ls
[translated-content] $ cd files/ja
[ja] $ ls
[ja] $ cd glossary/entity

// トピックブランチを切る（ブランチ名は GitHub Issue の番号にでもしておく）
// ※トピックブランチ名に特に決まりはありません。自由に決めてください。
[entity] $ git checkout -b issue-123
```

- ターミナルで別タブを開きます。

```
// content ディレクトリに移動する
[~] $ cd ~/path/to/mdn_repos/content

// ローカルプレビューを起動する
[content] $ yarn start
```

- ブラウザから http://localhost:5042/ja/docs/Glossary/Entity を開きます。
    - ja の URL でページが表示できていることを確認できたら OK です。
    - 実際にはページが存在しているのに、初回アクセス時に Page not found となる場合があります。その場合はブラウザでページをリロードすれば表示されます。

## 共通の手順（編集または新規作成） {#edit-flow}

### メタデータ部分（Front-matter）の編集 {#front-matter}

- index.md ファイルは、Markdown によるコンテンツの記述部分より手前に、Yaml によるメタデータの記述があります。
    - そのメタデータ部分は Front-matter と呼ばれます。これは MDN に限らず一般的に用いられている記法の一つです。
- MDN では、翻訳ファイル側の Front-matter を特定のフォーマットにする必要があります。
    - そのフォーマットは英語版と異なります。そのため、作業者が編集する必要があります。
    - これは「[ja - フロントマターから不要なメタデータを削除](https://github.com/mdn/translated-content/issues/7858)」による要請です。
- 英語版が次のようになっていたとします。

```yaml
---
title: Entity
slug: Glossary/Entity
tags:
  - CodingScripting
  - Composing
  - HTML
---
```

- 日本語版では、`title` と `slug` 以外を削除し、`l10n` を追加します。
    - `tags`, `translation_of`, `browser-compat`, `spec-urls` などは全て削除してください。
    - `l10n` は「エル 10 エヌ」です。アイではありません。

```yaml
---
title: Entity
slug: Glossary/Entity
l10n:
  sourceCommit: 1cfa0cd49bb572480f014af3b15dee3bda974178
---
```

- `sourceCommit` のハッシュ値は、編集作業時点の content リポジトリの当該記事ページのファイル（英語版）の最新コミットハッシュ値（`git log` で確認できる）を記述します。
    - これにより、日本語版が英語版のいつのバージョンに追従しているかを把握することができるようになります。
    - つまり、これを記述する場合は、日本語版の記事の内容を英語版の最新の内容と同期させる必要があります。
        - 軽微な修正のみを行いたい場合で、`l10n` が記述されていない場合には上記の Front-matter の編集はしなくても構いません。
- 実際の参考PR：https://github.com/mdn/translated-content/pull/8025

### 本文部分（Markdown）の編集 {#body}

- 英語文を日本語文に翻訳していきます。
- その際、「英数字の前後には半角スペースを挿入する（例えば OK のように）」や、「-er、-or、-ar、-cy、-ry、-gy、-xy で終わる単語はすべて長音を付加する（ユーザーなど）」といった表記ルールを守る必要があります。
- 詳しくは以下のガイドラインを参照してください。
    - [表記ガイドライン](https://github.com/mozilla-japan/translation/wiki/Editorial-Guideline)
    - [L10N ガイドライン](https://github.com/mozilla-japan/translation/wiki/L10N-Guideline)
    - [Mozilla 用語集](https://github.com/mozilla-japan/translation/wiki/Mozilla-L10N-Glossary)
    - [日本語の文体](https://docs.google.com/spreadsheets/d/1y-hC-xMXawCgcYZwJDnvuSlAOTgMRLLyqXurpYkJbYE/edit#gid=0)
- 記事中にある別の MDN ページへのリンク URL も英語版から日本語版へ変更します。
    - このとき、別の MDN ページの日本語版が存在していなくても、URL は日本語版のものに書き換えてください。
    - MDN では翻訳ページ URL に翻訳記事が存在しない場合、自動で英語版記事へリダイレクトするような設定がされています。
    - URL を日本語版のものに書き換えておけば、後々その記事が日本語化されたときにリンクが正常に機能するようになります。
- 翻訳作業（編集作業）が終わったら、次の手順へ進みます。
