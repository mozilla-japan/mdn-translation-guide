# 4-1.ローカルプレビュー環境の構築

1. 手元に作業用ディレクトリを用意します。
  ```
  $ mkdir ~/path/to/mdn_repos
  $ cd ~/path/to/mdn_repos
  ```
1. 作業に必要な3つのリポジトリを clone します。
  - https://github.com/mdn/yari
  - https://github.com/mdn/content
  - fork した translated-content リポジトリ
1. **確認** これで作業用ディレクトリの中に、3つのディレクトリ（リポジトリ）がある状態になっています。
  ```
  [mdn_repos] $ ls
  content    translated-content    yari
  ```
1. yari ディレクトリ内に .env ファイルを作成し、次のような内容を書き込みます。
  ```
  [yari] $ cat .env
  CONTENT_ROOT=../content/files
  CONTENT_TRANSLATED_ROOT=../translated-content/files
  ```
1. yari ディレクトリで、yarn install を一度実行した後、yarn dev を実行するとプレビュー環境が作られます。
  ```
  [yari] $ yarn install
  [yari] $ yarn dev
  ```
1. yarn dev は少し時間がかかりますが、完了すると http://localhost:3000/ にアクセスできるようになります。
