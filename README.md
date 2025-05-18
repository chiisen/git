# git
git 進階實戰開發

---

我要建立一個新的 branch 作為新功能的 branch 使用
```bash=
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