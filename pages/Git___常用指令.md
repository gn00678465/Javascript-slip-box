category:: Environment
type:: #Git
alias:: Git 常用指令

- ## 切換分支
	- `git checkout [branch name]`
	- `git checkout -b [branch name]`
		- 建立新分支並切換至新建立的分支
- ## 合併
	- `git merge [branch name]`
	- `git rebase`
		- [[rebase]]
- ## 交互模式
	- `git rebase -i`
		- [[合併提交]]
		- [[修改歷史訊息]]
- ## 回復
	- `git reflog`
	- `git reset HEAD~[number]`
	- `git reset [SHA-1] --hard`
	- `git reset ORIG_HEAD --hard`