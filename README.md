# GitHub講座


## *Lesson0 Gitをinstallする*  

**Windows**  
`git bash`を使っていくと便利です。  
[【初心者向け】Gitのインストール方法](https://eng-entrance.com/git-install)  


**Mac**  
ターミナルを起動し
```
$ brew install git
```
をコマンドすればインストールされます。


**インストールの確認**  
それぞれの環境で
```
$ git --version
```
をコマンド





### **~GitHubのアカウント作成~**  
[GitHub](https://github.com/login)   にアクセス  
`New to GitHub? Create an account.` をクリック   
必要項目を入力して完成。   

---


## *Lesson1 GitHubからRepositoriesをClone*  

**講座用のRepositoriesをCloneしよう**  
[講座のテキストページ](https://github.com/kuniatsu/workShop) から自分のbranchのURLを調べる
```
$ git clone `URL`
```


---


## *Lesson2 Repositoriesの状態を確認*  

```
$ git diff
```

**差分のあるファイルがないことを確認しよう**  
```
$ git status
```

**新しくファイルを追加して変化をみよう**  
```
$ git diff
$ git status
```


---


## *Lesson3 LocalのRepositoriesに変更を反映させる*  

**新しいファイルを反映の対象しよう**  
```
$ git add `ファイル名`
$ git status
```

**新しいファイルを反映しよう**  
```
$ git commit
* コメントを書く
$ git status
```


**commitの履歴を確認しよう**  
```
$ git log
```


---


## *Lesson4 変更を元に戻す*  

**ファイルを編集して新しい差分を作ろう**  
```
$ git diff
$ git status
$ git add `ファイル名`
$ git status
$ git commit
* コメントを書く
$ git status
$ git log
```

**rollbackしよう**  
```
$ git log
* IDを調べる
$ git reset --hard `commitのID`
$ git log
```



---


## *Lesson5 GitHubの設定する*  

**ユーザ名・アドレス・URLを確認する**  
```
$ git config user.name
$ git config user.email
$ git remote -v
```

**ユーザ名・アドレス・URLを登録する**  
```
$ git config user.name `GitHubのユーザ名`
$ git config user.email `GitHubのアドレス`
$ git remote add origin `https://ユーザ名@github.com/kuniatsu/workShopoGitHub.git`
```

---


## *Lesson6　remoteのRepositoriesに変更を反映させる*  

**新しいファイルを反映の対象しよう**  
```
$ git push
```

---


## *Lesson7　新しいbranchを作る*  

GitHubの画面からbranchを作成する

**Localのbranchを確認しよう**  
```
$ git branch
$ git branch -a
```

**branchの情報を更新しよう**  
```
$ git fetch
$ git branch
$ git branch -a
```



---


## *Lesson8 新しいbranchに切り替えよう*  

```
$ git checkout `branch名`
```


---


## *Lesson9*  

### **~プルリクを出そう~** 
GitHubの画面からPullRequestをだす


