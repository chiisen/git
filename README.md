# git
git 進階實戰開發

---

# 我要建立一個新的 branch 作為新功能的 branch 使用
```bash
// 切換到 develop 一般新功能，都是基於 develop
git checkout develop

// 建立新 branch
git branch fearure/funky_modify_add_wagers
// 刪除 branch
git branch -d fearure/funky_modify_add_wagers

//branch 的英文拼字打錯了，重建一個 branch

// 建立新 branch
git branch feature/funky_modify_add_wagers
git checkout feature/funky_modify_add_wagers
```

# 修改 Commit Message 的內容紀錄
```bash
git commit --amend -m "Welcome To Facebook"
```

## 抓取遠端專案內容
```shell
// 抓取遠端專案內容到目前目錄
git clone https://github.com/使用者名稱/專案名稱.git
```

## 拉取
```shell
// 【拉取】
// 拉取所有分支
git pull origin
//只拉取 company 分支
git pull origin company

// -v --progress 會有多一點資訊
git pull -v --progress origin
git pull -v --progress origin company

// origin 或 "origin" 都能接受
git pull -v --progress "origin"
git pull -v --progress "origin" company
```

## 推送
```shell
// 【推送】
// 拉取所有分支❓
git push origin
//只推送 company 分支
git push origin company

// -v --progress 會有多一點資訊
git push -v --progress origin
git push -v --progress origin company

// origin 或 "origin" 都能接受
git push -v --progress "origin"
git push -v --progress "origin" company:company
```

```shell
// 初始化
git init
```

## Commit
![Untracked files](https://hackmd.io/_uploads/BkyxoVJmp.png)

```shell
// status 的 Untracked files 尚未是 Git 追蹤的對象
// 新增所有變更檔案(. 表示所有,也可以指定檔案)加入到 Git 追蹤對象
git add .
// 查看一下檔案內容差異的狀態
git status
```

![git add .](https://hackmd.io/_uploads/rJYWiVJQa.png)

```shell
git commit -m "first commit"
```

![git remote show origin](https://hackmd.io/_uploads/rkN7TLJmp.png)

## git remote
```shell
// 查看該 remote repository 與 local repository 的連接
git remote -v

// 查看 remote repository
git remote show origin
```

## git branch
![git branch -a](https://hackmd.io/_uploads/ryrL081mp.png)

```shell
// 列出所有 branch (remote【紅色】 與 local【綠色】)
git branch -a

// 列出所有 branch (local【綠色】)
git branch

// 列出所有 branch (remote【紅色】)
git branch -r
```

![git branch -av](https://hackmd.io/_uploads/S1ONJvJQT.png)

```shell
// 列出所有 branch (remote【紅色】 與 local【綠色】)包含 commit 紀錄
git branch -av
```

## git merge
```shell
// 建立新 branch 為 issue1
git branch issue1

// 切換 branch
git checkout issue1

// 合併 branch(先切到 master 所以 issue1 會合併到 master)
git merge issue1

// 刪除 branch 為 issue1
git branch -d issue1
```

## git checkout
![git checkout --track origin/test1](https://hackmd.io/_uploads/S1gBxD1Xa.png)

```shell
// 取得 remote 的 test1 分支並追蹤
git checkout --track origin/test1
```

## 顯示 commit 紀錄

![git log --oneline -n 5](https://hackmd.io/_uploads/ry3CkTl76.png)

```shell
// 列出前 5 筆的 commit 紀錄(用一行的簡短樣式顯示)
git log --oneline -n 5
```

## 解決合併衝突❓
故意製造衝突
修改衝突檔案
```shell
連猴子都能懂的Git命令 issue1
<<<<<<< HEAD
連猴子都能懂的Git命令 issue2
=======
連猴子都能懂的Git命令 issue3
>>>>>>> 2d0d000 (add issue3)
```
砍掉 `<<<<<<< HEAD` 與 `=======`、`>>>>>>> 2d0d000 (add issue3)`
然後再 commit 一次(衝突無法 commit)
```shell
git add .
git commit -m "first commit"
```

## 取消合併
```shell
git reset --hard HEAD~
```