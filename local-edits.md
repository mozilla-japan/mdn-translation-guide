# ローカルで編集をする

原文はこちら：[setup](https://github.com/mdn/content#setup)  
こちらも参考に：[MDN Web Docs ドキュメント翻訳の始め方](https://github.com/mozilla-japan/translation/wiki/Get-started-with-translation-of-Mozilla-documentations)


[前ページ](simple-edits.md)で fork したリポジトリ を clone してローカルに置きます。
-  ※最新のmainブランチを取り込んでいる状態にします（[前ページ](simple-edits.md)を参照）
- 例：/Users/path/to/repos/mdn/content
- 例：/Users/path/to/repos/mdn/translated-content
- ターミナルで、以下のコマンドを実施します
    ```
    $ cd /Users/path/to/repos/mdn/content
    
    # 以下、yarn コマンドが使える環境である必要があります。yarn の使い方が分からなければSlackで聞いてください。
    $ yarn install 

    # .env ファイルを作成
    # CONTENT_TRANSLATED_ROOT={translated-contentリポジトリ内のfilesディレクトリ}

    # 例：/Users/path/to/repos/mdn/translated-content/files
    $ content git:(main) cat .env
    CONTENT_TRANSLATED_ROOT=/Users/path/to/repos/mdn/translated-content/files

    # http://localhost:5042 にアクセス
    $ yarn start
    ```
- MDN の Writer's home page が表示されます🎉  
  ![local-boot](images/local-boot.png)
