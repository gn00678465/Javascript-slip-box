category:: Environment
type:: #Git
alias:: Git 常用指令

- ## 切換分支
  collapsed:: true
	- `git checkout [branch name]`
	- `git checkout -b [branch name]`
		- 建立新分支並切換至新建立的分支
- ## 合併
  collapsed:: true
	- `git merge [branch name]`
	- `git rebase`
		- [[rebase]]
- ## 交互模式
  collapsed:: true
	- `git rebase -i`
		- [[合併提交]]
		- [[修改歷史訊息]]
- ## 回復
  collapsed:: true
	- `git reflog`
	- `git reset HEAD~[number]`
	- `git reset [SHA-1] --hard`
	- `git reset ORIG_HEAD --hard`
- ## Remote repository
	- `git remote -v`: 確認目前的 remote repo (包含 rul)
	- `git remote add <remote-name> <remote-url>`: 添加 remote repo
		- **remote-name**: remote repo name
		- **remote-url**: remote repo url
	- `git remote set-url <remote-name> <remote-url>`: 變更 remote repo
		- **remote-name**: remote repo name
		- **remote-url**: remote repo url