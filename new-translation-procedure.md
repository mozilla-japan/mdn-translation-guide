# 4-2.新規翻訳の手順（index.md の作成）

1. 翻訳したい英語版の記事を決めます。
  - 例：https://developer.mozilla.org/en-US/docs/Glossary/Entity
1. 手元の content リポジトリから index.md ファイルを探します。
  ```
  [mdn_repos] $ ls content/files/en-us/glossary/entity/index.md
  ```
1. fork した translated-content リポジトリに、英語版の index.md をコピーします。
  ```
  [repos] $ cp -r content/files/en-us/glossary/entity/ translated-content/files/ja/glossary/
  ```
1. http://localhost:3000/ja/docs/Glossary/Entity にアクセスして、日本語版URLでページが開けることを確認します。
  - プレビュー環境を content リポジトリで作っている場合は http://localhost:5042/ja/docs/Glossary/Entity
  - 英語版 index.md をコピーしたので、内容は英語になっています。
1. ここまで確認できたら、一度 index.md をコミットします。コミットメッセージは自由ですが、適当に記載します。
  ```
  [translated-content] $ git add .
  [translated-content] $ git commit -m "copied index.md from en-us"
  ```
1. 日本語翻訳作業に移ります。（次のページへ）
