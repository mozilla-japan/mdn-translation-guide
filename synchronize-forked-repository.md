# 3-4.fork元のリポジトリと同期する

原文はこちら：[setup](https://github.com/mdn/content#setup)  
こちらも参考に：[MDN Web Docs ドキュメント翻訳の始め方](https://github.com/mozilla-japan/translation/wiki/Get-started-with-translation-of-Mozilla-documentations)

## 翻訳した内容についても、他の人からの更新を取り込みます。

#### ※2回目以降の翻訳や、forkしてから時間がたった場合、以下のようにして fork したリポジトリを最新の状態にしてください。
#### こちらもウェブ上でできます。自分のtrnaslated-contentリポジトリのページにある「Fetch upstream」ドロップダウンを押すと表示される「Fetch and merge」ボタンを押してください。
##### 前提：fork元のリポジトリをリモート参照先として追加してあること： (git remote -v で確認できる)
```
# forkしたリポジトリをチェックアウトしたディレクトリに移動
$ cd ~/repos/mdn/trnaslated-content

# リモート参照先として fork元のリポジトリを transmdn という名前で追加
$ git remote add transmdn git@github.com:mdn/translated-content.git 

# forkしたリポジトリをチェックアウトしたディレクトリに移動
$ cd ~/repos/mdn/translated-content  

# 手元の作業コピーを main ブランチに切り替える（チェックアウト）
$ git checkout main                             

# 手元の作業コピーに、fork 元の main の最新を取り込む
$ git pull transmdn main                      

# 自分の作業ブランチに切り替える（チェックアウト。なければ作成される。※my-workは任意のブランチ名）
$ git checkout -b my-work                   

# 最新にした main を作業ブランチに merge
$ git merge main                                 
```
その後、作業をすすめて push -> pull request します。
