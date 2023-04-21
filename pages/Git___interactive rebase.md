category:: Environment
type:: Git
alias:: interactive rebase

- ## 使用 `rebase -i` 合併提交
- > 將瑣碎的 commit 整理合併，推送至 server 前可以執行此動作
- ```bash
  git rebase -i [hash]
  ```
	- `hash`: 特定的 commit，也可以使用相對引用
- ### example
- ```bash
  $ git log --oneline
  
  0408be7 (HEAD -> master) 添加pull的說明
  6684543 添加commit的說明
  88abe9b 添加add的說明
  283877f first commit
  ```
- ```bash
  $ git rebase -i 283877f
  ```
- 預設的文字編輯器會自動開啟，將看到帶入的 commit 之後的提交
- ```plain
  pick 88abe9b 添加add的說明
  pick 6684543 添加commit的說明
  pick 0408be7 添加pull的說明 # empty
  
  # Rebase 283877f..0408be7 onto 283877f (3 commands)
  #
  # ...
  ```
- > *在互動模式的紀錄由上而下是從最舊到最新，跟 `git log` 指令所呈現的結果是相反的*
	- ```plain
	  pick 88abe9b 添加add的說明
	  squash 6684543 添加commit的說明
	  pick 0408be7 添加pull的說明 # empty
	  
	  # Rebase 283877f..0408be7 onto 283877f (3 commands)
	  #
	  # ...
	  ```
		- 將 6684543 的 `pick` 修改為 `squash`
		  id:: 644224a3-fed4-4c8d-84df-aea5b4237545
		- **6684543** 會與 **88abe9b** 進行合併。
	- ```plain
	  pick 88abe9b 添加add的說明
	  squash 6684543 添加commit的說明
	  squash 0408be7 添加pull的說明 # empty
	  
	  # Rebase 283877f..0408be7 onto 283877f (3 commands)
	  #
	  # ...
	  ```
		- 將 **6684543**,  **0408be7** 的 `pick` 修改為 `squash`
		- **0408be7** 會與 **6684543** 先進行合併，再與 **88abe9b** 進行合併。
- 在 Squash 的過程中，還會跳出編輯器編輯一下合併後要顯示的訊息
- ```bash
  $ git log --oneline
  
  703bc7c (HEAD -> master) 添加pull的說明
  7b4638b 添加add的說明 添加commit的說明
  283877f first commit
  ```
-
- ## Reference
	- [【狀況題】把多個 Commit 合併成一個 Commit](https://gitbook.tw/chapters/rewrite-history/merge-multiple-commits-to-one-commit)