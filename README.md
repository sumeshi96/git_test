# git/github の最低限の使い方

## 必要なもの

[Git Bash](https://gitforwindows.org)  
[Visual Studio Code](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)  

## Linux(Git Bash)の便利なコマンド
`ls` : カレントディレクトリのファイル一覧を取得  
`cd` : ディレクトリを変更  
`touch` : ファイルを作成  
`mkdir` : ディレクトリを作成  
`rm -rf`: ファイルを削除  

## 練習の流れ

0.リポジトリをクローンする

__`git clone https://github.com/sumeshi96/repositoryname.git`__
このリポジトリをクローンするには
`git clone https://github.com/sumeshi96/git_test.git`

1-1.現在のブランチを確認
__`git branch`__
`*main`と表示されていればOK

1-2.ブランチを作る

__`git branch name`__  
ex)`git branch sumeshi`  
   `git branch puranari`  
   `git branch tantan`  

1-3.ブランチを移動  
__`git switch name`__  

2.適当にファイルを作成  

コマンドでやるなら  
__`touch filename `__  
ex) `touch sumeshi.md`  

3.gitにファイルをステージング  

__`git add filename`__  
ex) `git add sumeshi.md`  

4.gitにコミット  

__`git commit -m "commit message"`__  
ex) `git commit -m "add: sumeshi.mdを追加"`  

5.githubにプッシュ  

__`git push origin name`__  
ex) `git push origin sumeshi`  

6.pullリクエスト  

## コミットメッセージについて  

コミット時にどんな変更をしたかを要約してわかりやすく記述する。  
メッセージにプレフィックスを付けることによってコミット種別を判別する。  


### コミット種別  

- fix : バグ修正  
- add : 新規ファイル（機能）追加  
- update : 機能修正（バグではない）  
- remove : 削除（ファイル）  

`git commit -m "fix:bodyにcssが当たらない不具合の修正"`  
`git commit -m "add:image.svgを追加"`  
`git commit -m "update:bodyのcssに背景を追加"`  
`git commit -m "remove:image.svgを削除"`  