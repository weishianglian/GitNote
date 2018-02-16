# 為你自己學 Git 筆記

## 使用者設定
### 設定指令
```
$ git config --global user.name "NAME"
$ git config --global user.email "EMAIL"
```
### 檢視設定
```
$ git config --list
```
### 設定檔位置
```
~/.gitconfig
```
### 每個專案設定不同的的作者
```
$ git config --local user.name "LOCAL"
$ git config --local user.email "LOCAL"
```

## 其他方便的設定
### 更換預設編輯器
```
$ git config --global core.editor emacs
```

### Git 指令縮寫
```
$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.st status
$ git config --global alias.l "log --oneline --graph"
$ git config --global alias.ls 'log --graph --pretty=format:"%h <%an> %ar %s"'
```

## 新增、初始 Repository
```
$ git init
```
## 把檔案交給 Git
```
$ git status
$ git add .
$ git commit -m "init commit"
```

### 允許 Commit Empty
```
$ git commit --allow-empty -m "Empty"
```

## 工作區、暫存區與儲存庫
|Working Directory|Staging Area|Repository|
|:-:|:-:|:-:|
|git add|git commit||

### 示意圖
![git all status](images/git-all-states.png)


## 檢視紀錄
```
$ git log
$ git log --oneline --graph
```

### 進階用法
#### 找某人的 Commit
```
$ git log --oneline --author="NAME"
```
#### 找 Commit 訊息的關鍵字
```
$ git log --oneline --grep="MESSAGE"
```
#### 找 Commit 檔案內容中有提到的關鍵字
```
$ git log --oneline -S "KEYWORD"
```

#### 依 Commit 時間查詢
```
$ git log --oneline --since="9am" --until="12am" --after="2017-01"
```

## 刪除或更名檔案
```
$ rm FILE && git add . 
# == $ git rm FILE

$ mv FILE && git add . 
# == $ git mv FILE
```

## 修改 Commit 紀錄
```
$ git commit -amend -m "REPLACE_MESSAGE"
```

## 追加檔案到上一次的 Commit
```
$ git commit --amend --no-edit
```

## 將檔案從 Git 中移除
```
$ git rm --cached FILE
```

## 將特定檔案忽略
```
.gitignore
```

## 看到檔案在每次 Commit 的修改
```
$ git log -p FILE
```

## 檔案是誰寫的！
```
$ git blame
```

## 從 Staging Area 救回誤刪的檔案
```
$ git checkout FILE
$ git checkout .
```

## 拆掉重做 Commit 
```
$ git reset HEAD^
$ git reset master^
4 git reset HEAD~1
```

### Git Reset 模式
```
$ git reset --mixed
$ git reset --soft
$ git reset --hard
```
模式|mixed 模式|soft 模式|hard 模式
:-|:-:|:-:|:-:|
工作目錄|不變|不變|丟掉
暫存區|丟掉|不變|丟掉

---

模式|mixed 模式（預設）|soft 模式 |hard 模式
:-|:-:|:-:|:-:|
Commit 拆出來的檔案| 丟回工作目錄|丟回暫存區| 直接丟掉

## 找到所有的紀錄
```
$ git reflog
$ git log --oneline -g
```

## HEAD 是現在所在的分支位置
```
$ cat .git/HEAD
```

## Git 分支
```
$ git branch
```

### 建立分支
```
$ git branch cat
```

### 更名分支
```
$ git branch -m cat tiger
```

### 刪除分支
```
$ git branch -d dog
```

#### 強制刪除
```
$ git banch -D dog
```

### 切換分支
```
$ git checkout tiger
```

#### 切換並建立分支
```
$ git checkout -b god
```

## 合併分支
```
$ git merge cat
$ git merge cat --no-ff
```

## 修改歷史
```
$ git rebase BRANCH
$ git rebase -i COMMIT
```

## 放下手邊工作
```
$ git stash
$ git stash list
$ git stash pop
```

## 推向遠端
```
$ git remote add origin URL
$ git push -u origin master
```

## 產生 ssh key
```
$ ssh-keygen
$ cat ~/.ssh/id_rsa.pub
$ pbcopy < ~/.ssh/id_rsa.pub
```
