# 4. fork リポジトリを clone する
  ## （2025年12月1日(UTC)に、[yarn から npm への移行](https://github.com/mdn/content/pull/42048)が予定されています）

## 初めてリポジトリを clone する場合 {#first}

```
// 作業用ディレクトリを作成する
[~] $ cd ~/path/to
[~/path/to] $ mkdir mdn_repos
[~/path/to] $ cd ~/path/to/mdn_repos

// fork リポジトリを 2 つとも clone する
[mdn_repos] $ git clone git@github.com:YOUR_NAME/content.git
[mdn_repos] $ git clone git@github.com:YOUR_NAME/translated-content.git

[mdn_repos] $ ls
content    translated-content

// content ディレクトリ内に .env を作成する
[mdn_repos] $ cd content
[content] $ echo 'CONTENT_TRANSLATED_ROOT=../translated-content/files' > .env
[content] $ cat .env
CONTENT_TRANSLATED_ROOT=../translated-content/files

// ローカルプレビューができるように yarn install しておく
[content] $ yarn install
```

## 既にリポジトリを clone している場合 {#already}

```
// 作業用ディレクトリに移動する
[~] $ cd ~/path/to/mdn_repos

// 最新の fork リポジトリを pull する
[mdn_repos] $ cd content
[content] $ git checkout main
[content] $ git pull

// content リポジトリでは yarn install し直しておく
[content] $ yarn install

// translated-content リポジトリも pull しておく
[content] $ cd ../translated-content
[translated-content] $ git checkout main
[translated-content] $ git pull
```
