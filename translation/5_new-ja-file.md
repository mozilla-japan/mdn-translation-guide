# 5. 日本語記事ページを新規作成する

## 既に日本語記事が存在する場合（編集の場合） {#edit}

- このページで行うことはありません。次のページへスキップしてください。

## 新たに新規ページを翻訳する場合（新規作成の場合） {#new}

- 例えば https://developer.mozilla.org/en-US/docs/Glossary/Entity の日本語版が存在しないとします。
- 新たに https://developer.mozilla.org/ja/docs/Glossary/Entity のページを作る手順は以下の通りです。

```
// translated-content ディレクトリへ移動する
[~] $ cd ~/path/to/mdn_repos/translated-content

// main ブランチにいることを確認する
[translated-content] $ git branch

// ls しながら、URL に対応するディレクトリへ移動する
[translated-content] $ ls
[translated-content] $ cd files/ja
[ja] $ ls
[ja] $ cd glossary

// glossary ディレクトリ内に entity ディレクトリを新規作成する
[glossary] $ mkdir entity
[glossary] $ cd entity

// 英語版のページファイル index.md をここにコピーする
[entity] $ cp ~/path/to/mdn_repos/content/files/en-us/glossary/entity/index.md .
```

- ターミナルで別タブを開きます。

```
// content ディレクトリに移動する
[~] $ cd ~/path/to/mdn_repos/content

// ローカルプレビューを起動する
[content] $ yarn start    # （2025年12月1日(UTC)に、[yarn から npm への移行](https://github.com/mdn/content/pull/42048)が予定されています）
```


- ブラウザから http://localhost:5042/ja/docs/Glossary/Entity を開きます。
    - ja の URL で存在しなかったはずのページが表示できていることを確認できたら OK です。
    - 実際にはページが存在しているのに、初回アクセス時に Page not found となる場合があります。その場合はブラウザでページをリロードすれば表示されます。
- cp コマンドを打っていた元のターミナルのタブに戻ります。

```
// 一度、この状態で translated-content リポジトリをコミットする

// トピックブランチを切る（ブランチ名は GitHub Issue の番号にでもしておく）
// ※トピックブランチ名に特に決まりはありません。自由に決めてください。
[entity] $ git checkout -b issue-123

// ブランチが移動しているか確認する
[entity] $ git branch

// コミットする
// ※コミットメッセージも特に決まりはありません。自由に決めてください。
[entity] $ git add .
[entity] $ git status
[entity] $ git commit -m "copied index.md from en-us"
```

- ここまでできたら、記事を編集する場合と同じ手順で作業を進めます。
