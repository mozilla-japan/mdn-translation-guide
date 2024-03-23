# 3. fork リポジトリを用意する

## 初めてリポジトリを fork する場合 {#first}

1. https://github.com/mdn/translated-content リポジトリを fork します。
1. https://github.com/mdn/content リポジトリを fork します。

## 既にリポジトリを fork している場合 {#already}

1. fork したリポジトリ https://github.com/YOUR_NAME/translated-content のページへアクセスします。
1. 画面上部にある「Sync fork」を押して「Update branch」を実行します。
1. "This branch is up to date with mdn/translated-content:main." と表示されたことを確認します。
    - ここが異なる表示結果になった場合、リポジトリに不整合が生じている可能性があります。その場合は以下の Git コマンドを参考に問題を解決するか Slack で相談してください。
1. https://github.com/YOUR_NAME/content のページでも同様のことを行います。
    - 古い原文から翻訳してしまうリスクを避けるため、content リポジトリでも「Sync fork」するのを推奨します。
