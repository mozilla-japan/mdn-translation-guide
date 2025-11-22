# yari リポジトリでの環境構築

  ## （2025年12月1日(UTC)に、[yarn から npm への移行](https://github.com/mdn/content/pull/42048)が予定されています）
- ローカルプレビューを行うのに content リポジトリでの `yarn start` を使う以外に、yari リポジトリでの `yarn dev` を使う方法があります。
- yari リポジトリでローカルプレビューを行うことで、最新の yari リポジトリの状態を反映できます。
    - 例えば MDN Web Docs のデザインが変更された際や、BCD（Browser Compat Data; ブラウザーの互換性）テーブルの構造が変更された場合などに、最新の状態を反映することができます。

```
// 作業用ディレクトリに移動する
[~] $ cd ~/path/to/mdn_repos

// yari リポジトリを clone する
[mdn_repos] $ git clone git@github.com:mdn/yari.git

[mdn_repos] $ ls
content    translated-content    yari

// yari ディレクトリに移動する
[mdn_repos] $ cd yari

// yari ディレクトリ内に .env を作成する
[yari] $ echo -e 'CONTENT_ROOT=../content/files\nCONTENT_TRANSLATED_ROOT=../translated-content/files' > .env
[yari] $ cat .env
CONTENT_ROOT=../content/files
CONTENT_TRANSLATED_ROOT=../translated-content/files

// ローカルプレビューができるように yarn install しておく
[yari] $ yarn install

// ローカルプレビューを起動する（`yarn start` ではなく `yarn dev` を使います）
[yari] $ yarn dev
```

- yarn dev は少し時間がかかりますが、完了すると http://localhost:3000/ にアクセスできるようになります。
    - content リポジトリの場合は Port:5042 でした。yari リポジトリの場合は Port:3000 が使われます。
