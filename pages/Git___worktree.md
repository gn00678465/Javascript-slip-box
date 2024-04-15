- > 同一個專案之中，開啟多個不同的 branch
- ## command
	- ```bash
	  // 查看目前工作目錄
	  git worktree list
	  // 建立全新 branch，並做為新的工作目錄
	  git worktree add -b <new_branch_name> <folder_path> <source_branch>
	  // 從已有的 branch，並做為新的工作目錄
	  git wroktree add <folder_path> <source_branch>
	  // 重新整理工作目錄
	  git worktree prune
	  ```
	- **git worktree list**
	-
	- **git wroktree add <folder_path> <source_branch>**
	-
	- **git worktree prune**
-
- ## Reference
	- [git worktree 簡單介紹與使用]([git worktree 簡單介紹與使用. 現在可以在同一個專案之中，一次開啟多個不同的 branch 了。 | by Ray Yuan Liou | Medium](https://louis383.medium.com/git-worktree-%E7%B0%A1%E5%96%AE%E4%BB%8B%E7%B4%B9%E8%88%87%E4%BD%BF%E7%94%A8-876897c797bf))