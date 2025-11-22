# 0. 準備するもの

## GitHub アカウントの用意 {#github}

- 翻訳作業を行うのに、[GitHub](https://github.com/) のアカウントが必要になります。
- 2020 年末より、MDN のシステムが Kuma から Yari に移行したことに伴い、全ての記事の管理に GitHub を使用することになりました。
- そのため GitHub アカウントをお持ちでない場合は作成する必要があります。GitHub アカウントを持っていない方はぜひ作成してみてください！
- 既に GitHub アカウントをお持ちの方はサインインして作業ができます。

## Node.js / Yarn のインストール {#yarn}
 ### （2025年12月1日(UTC)に、[yarn から npm への移行](https://github.com/mdn/content/pull/42048)が予定されています）

- 手元のブラウザで翻訳作業中の内容をローカルプレビューするために、Yarn が実行できる環境が必要になります。
- まずは Node.js がインストールされている必要があります。
  - Node.js のインストールは nodenv を使うなど様々な方法があります。
  - ご自身に合った方法でインストールを行ってみてください。分からなければ Slack でお気軽にご質問ください。
- Node.js がインストールできていれば、次のページを参考に Yarn をインストールしてください。
  - https://yarnpkg.com/getting-started/install
- **Yarn についての注意事項**

  - 動作保証のバージョンは、**`v1.x`** です。
  - yarn v2.x 以上の場合は、content/package.json の script の変更が必要です。
  - content/package.json の script の変更は、**`絶対にプッシュしない`** で下さい

    ```diff
    - "start": "yarn -s info:rari && yarn up-to-date-check && env-cmd --silent cross-env CONTENT_ROOT=files REACT_APP_DISABLE_AUTH=true BUILD_OUT_ROOT=build rari-server",
    + "start": "yarn info:rari && yarn up-to-date-check && env-cmd --silent cross-env CONTENT_ROOT=files REACT_APP_DISABLE_AUTH=true BUILD_OUT_ROOT=build rari-server",
    ```
