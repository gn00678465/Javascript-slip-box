category:: Environment
type:: #Git
alias:: 修改歷史訊息

- ## 使用 `rebase -i` 修改歷史訊息
- > 可修改其它更早的 commit 訊息
- ```bash
  git rebase -i [SHA-1]
  ```
	- `hash`: 特定的 commit，也可以使用相對引用
- ### 指令 `reword`
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
  reword 6684543 添加commit的說明
  pick 0408be7 添加pull的說明 # empty
  
  # Rebase 283877f..0408be7 onto 283877f (3 commands)
  #
  # ...
  ```
	- 將 6684543 的 `pick` 修改為 `reword` 後存檔
- 會跳出編輯器編輯一下需要變更的訊息
-
- ## Reference
	- [【狀況題】修改歷史訊息](https://gitbook.tw/chapters/rewrite-history/change-commit-message)