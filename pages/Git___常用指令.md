category:: Environment
type:: Git
alias:: Git 常用指令

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