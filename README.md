# Git/Github の最低限の使い方

## 必要なもの

- Githubのアカウント (<https://github.com>)  
- Git Bash (<https://gitforwindows.org>)  
- Visual Studio Code (<https://azure.microsoft.com/ja-jp/products/visual-studio-code/>) 

### Gitの初期設定

GitHubの名前とメールアドレスを入力
- `git config --global user.name name`
- `git config --global user.email git@gmail.com`

デフォルトブランチをmainに変更
- `git config --global init.defaultBranch main`

githubへの認証を回避する
- `git config --global credential.helper store`

## Linux(Git Bash)の便利なコマンド

- `ls` : カレントディレクトリのファイル一覧を取得  
- `cd` : ディレクトリを変更  
- `touch` : ファイルを作成  
- `mkdir` : ディレクトリを作成  
- `rm -rf`: ファイルを削除  

## 練習の流れ
### Gitでの作業
0.リポジトリをクローンする

- __`git clone https://github.com/sumeshi96/repositoryname.git`__  
このリポジトリをクローンするには  
- `git clone https://github.com/sumeshi96/git_test.git`

1-1.現在のブランチを確認  

- __`git branch`__  
`*main`と表示されていればOK  

1-2.ブランチを作る

- __`git branch name`__  
ex)`git branch sumeshi`  
   `git branch puranari`  
   `git branch tantan`  

1-3.ブランチを移動  

- __`git switch name`__  

2.適当にファイルを作成  

コマンドでやるなら  

- __`touch filename`__  
ex) `touch sumeshi.md`  

3-1.gitにファイルをステージング  

- __`git add filename`__  
ex) `git add sumeshi.md`  

3-2.ステージングされているファイルを確認

- `git status -s`
  
  - `M_`:`git add`されているが、`git commit`されていないファイル
  - `_M`:編集、変更、削除されているが`git add`されていないファイル
  - `??`:gitで管理されていないファイル

4-1.gitにコミット  

- __`git commit -m "commit message"`__  
ex) `git commit -m "add: sumeshi.mdを追加"`  

4-2.コミット履歴を見る

- `git log`  
  終了するには`q`を入力

5.githubにプッシュ  

- __`git push origin name`__  
ex) `git push origin sumeshi`  

6.pullする
- `git pull`
  リモートリポジトリの変更内容をローカルリポジトリに反映させる。

### Githubでの作業
6.pullリクエストをしてみる  

自分の作業しているブランチを統合したいブランチに統合する作業の委託and機能追加の前にコードレビューを行うことでミスを減らしたい  
この場合プランチをmargeする作業はsumeshi担当なのでpullリクエストを発行しレビュー→修正→marge

[詳しくはここを参照](https://backlog.com/ja/git-tutorial/pull-request/10/)  
[メモ（間違いに気づいたとき）](https://masuyama13.hatenablog.com/entry/2020/07/22/235812)

7.Issueを立ててみる  
バグが直せないとき、困ったことがあったとき、他の人の間違いに気づいたときなど、Issueを書くと解決策を一緒に探すことができる。

## コミットメッセージについて  

コミット時にどんな変更をしたかを要約してわかりやすく記述する。  
メッセージにプレフィックスを付けることによってコミット種別を判別する。  

### コミット種別  

- fix : バグ修正  
- add : 新規ファイル（機能）追加  
- update : 機能修正（バグではない）  
- remove : 削除（ファイル）  

- `git commit -m "fix:bodyにcssが当たらない不具合の修正"`  
- `git commit -m "add:image.svgを追加"`  
- `git commit -m "update:bodyのcssに背景を追加"`  
- `git commit -m "remove:image.svgを削除"`
