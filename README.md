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
`git version 0.00.0`
というようにバー




### **GitHubのアカウント作成**  
[GitHub](https://github.com/login)   にアクセス  
`New to GitHub? Create an account.` をクリック   
必要項目を入力して完成。   

---


## *Lesson1 GitHubからRepositoriesをClone*  

**講座用のRepositoriesをCloneしよう**  
[講座のテキストページ](https://github.com/kuniatsu/workShopGitHub) から自分のbranchのURLを調べる
```
$ git clone `URL`
```




---


## *Lesson2 branchの状態確認方法*  
変更のない状態のメッセージを見ておきましょう。  

**差分がないことを確認しよう**   
```
$ git diff
```
何も表示されない  

**branchに差分のあるファイルがないことを確認しよう**  
```
$ git status

On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

**branchのlogを確認してみよう**  
```
$ git log
```
これまでのlogを表示。  
ENTERキーでスクロール  
qキーを押して終了  

**repositoryのbrnachを確認してみよう**  
```
$ git branch
```
今作られているbranchを確認  
masterだけ表示される



```
repository
└── branch
    └── file
        └── diff(差分)
```
---

## *Lesson3 branchを切り替える*  

**Localのbranchを確認しよう**  
```
$ git branch
$ git branch -a
```

**branchを変更しよう**  
```
$ git checkout `branch名`
$ git branch
```

---

## *Lesson4 LocalのRepositoriesに変更を反映させる*  

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


## *Lesson5 変更を元に戻す*  

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


## *Lesson6 GitHubの設定する*  

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


## *Lesson7　remoteのRepositoriesに変更を反映させる*  

**Repositoriesに新しいファイルを反映をしよう**  
```
$ git push
```

---


## *Lesson8　新しいbranchを作る*  

GitHubの画面から新branchを作成する

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

**branchを切り替えよう** 
```
$ git checkout `新branch名`
```

---


## *Lesson9 Localのファイルの衝突*  

**同じ名前のファイルを作って衝突させる** 
```
$ vi 同じ名前のファイルを作成
$ git checkout `branch名`
```
↑エラーが発生する


**新branchを作り衝突回避** 
```
$ git add `ファイル名`
$ git commit
$ git checkout `branch名`
```
↑エラーは起きなくなる。

**強制的にチェックアウトする** 
もう一度エラーが起こる状態を作る
```
$ git checkout `branch(A)` 
$ vi ファイル作成
$ git add `ファイル名`
$ git commit
$ git push
```

同名のファイルを作り衝突を確認
```
$ git checkout `branch(B)` 
$ vi 同名のファイル作成
$ vi 別名のファイル作成
$ git checkout `branch(A)` 
```
↑エラーが発生する


同名のファイルを作り衝突を確認
```
$ git checkout -f `branch(A)` 
```
↑上書きされる。



---

## *Lesson10 リモートでコンフリクトを起こす*  

**同じ名前のファイルを作って衝突させる** 
```
$ git checkout master
```
國島が変更を行うので確認する  
・ファイル名  
・変更箇所  


同じ場所に別の修正を入れて衝突させるpush拒否される
```
$ vi ファイル名
$ git add `ファイル名`
$ git commit 
$ git push
```

コンフリクトを起こす
```
$ git pull
```
↑コンフリクトが発生する  


コンフリクトを解決する  
```
$ vi ファイル名
$ git push
```

---

## *Lesson11 mergeをする*  

branchをmergeする
```
$ git checkout `branch(A)`
$ git merge `branch(B)`
$ ls -l
```


---

## *Lesson12 プルリクを送る*  

![Lesson12_1](Lesson12_1.png)
「New pull request」を押します。    

![Lesson12_2](Lesson12_2.png)
どのブランチをどのブランチにマージするかを選択   
「Create pull request」を押下で作成完了です。   

