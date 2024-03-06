category:: Note
type:: #Git, #Note
alias:: Git 設定值調整

- ## Global
	- 設定全域 `user.name` 與 `user.email` 資訊
	- ```bash
	  git config --global user.name <name>
	  git config --global user.email <email>
	  ```
	- 常用設定
	- ```bash
	  git config --global core.editor <editor>
	  git config --global core.autocrlf false
	  git config --global core.quotepath false
	  git config --global help.autocorrect 30
	  git config --global color.diff auto
	  git config --global color.status auto
	  git config --global color.branch auto
	  git config --global init.defaultBranch <name>
	  ```
	- alias 設定
	- ```bash
	  git config --global alias.ci commit
	  git config --global alias.reset-hard   "reset ORIG_HEAD --hard"
	  ```
- ## Local
	- 設定 `user.name` 與 `user.email` 資訊
	- ```bash
	  git config user.name <name>
	  git config user.email <email>
	  ```