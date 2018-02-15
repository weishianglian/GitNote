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
<table style="text-align: center;">
  <tr>
    <td colspan="2">Working Directory</td>
    <td colspan="2">Staging Area</td>
    <td colspan="2">Repository</td>
  </tr>
   <tr>
    <td></td>
    <td colspan="2">git add</td>
    <td colspan="2">git commit</td>
    <td></td>
  </tr>
</table>

### 示意圖
![git-all-status](images/git-all-status.png)

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




