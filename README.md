# gitbook
Learning Git for myself

## User Setting
Set user name and email
```
git config --global user.name "UserName"
git config --global user.email "UserName@mail.com"
```
List configuration
```
git config -l
```
Convenient setting
```
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.st status
git config --global alias.l "log --oneline --graph"
git config --global alias.ls 'log --graph --pretty=format:"%h <%an> %ar %s"'
```

## Creating and Initialising Repository
```
git init
git status
git add .
git commit -m "Init Commit"
```

## Git Working Blocks
|Working Directory|Staging Area|Repository
|:-:|:-:|:-:|
||`git add`|`git commit`|

## Viewing Records
```
git log

```
