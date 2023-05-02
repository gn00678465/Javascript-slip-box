category:: Environment
type:: Git
alias:: Upstream

- ## 追蹤遠端的分支並上傳
- ```bash
  git push -u <remote name> <branch name>
  ```
	- > 參數 `-u` 等同於 `--set-upstream`，設定 upstream 可以使分支開始追蹤指定的遠端分支
- 設定好 upstream 後，第二次以後要上傳分支時，就只需要透過 `git push` 就可以了，不必再帶 `<remote name>` 跟 `<branch name>` 等參數
-
- ## 追蹤遠端的分支
- ```bash
  git branch -u <remote>/<remote branch> <branch name>
  # or
  git branch --set-upstream-to=<remote>/<remote branch> <branch name>
  ```
-
- ## 取消追蹤遠端分支
- ```bash
  git branch --unset-upstream
  ```
-
- ## Reference
	- [git Local 端與 Remote 端的分支操作](https://sean22492249.medium.com/git-local-%E7%AB%AF%E8%88%87-remote-%E7%AB%AF%E7%9A%84%E5%88%86%E6%94%AF%E6%93%8D%E4%BD%9C-3dc360be3b5b)