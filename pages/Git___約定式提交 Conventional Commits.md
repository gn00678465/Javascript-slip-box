category:: Note
type:: #Git, #Note
alias:: 約定式提交 Conventional Commits

- ## Commit Message Format
	- ```plain
	  <type>(<scope>): <subject>
	    │       │             │
	    │       │             └─⫸ <描述 subject>
	    │       │
	    │       └─⫸ Commit Scope: <作用範圍 scope>(optional)
	    │
	    └─⫸ Commit Type: <提交類型 type>
	    
	  [正文 body](optional)
	  
	  [頁腳 footer](optional)
	  ```
		- **<提交類型 type>**: commit 的類別
		  collapsed:: true
			- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
			- **ci**: 持續整合 (Continuous integration)
			- **docs**:文件（documentation）
			- **feat**: 新增或修改功能（feature）
			- **fix**: 修補 bug（bug fix）
			- **perf**: 改善效能 (Optimization/performance improvement)
			- **refactor**: 重構
				- 不是新增功能，也非修補 bug 的程式碼變動
			- **test**: Adding missing tests or correcting existing tests
			- **style**: 與格式有關
				- 不影響程式碼運行的變動，例如：white-space, formatting, missing semi colons
			- **workflow**: 工作流改善 (Workflow improvements)
			- **types**:  改變檔案的類型定義 (Type definition file changes)
			- **chore**: maintain
				- 不影響程式碼運行，建構程序或輔助工具的變動，例如修改 config、Grunt Task 任務管理工具
			- **revert**: 撤銷回覆先前的 commit
		- **<作用範圍 scope>**: commit 影響的範圍
		  collapsed:: true
			- **scope** 可以是任何描述性的字串，它可以是一個單獨的模組、一個功能、一個組件、一個文件等等。
			  
			  The following is the list of supported scopes:
				- `animations`
				- `bazel`
				- `benchpress`
				- `common`
				- `compiler`
				- `compiler-cli`
				- `core`
				- `elements`
				- `forms`
				- `http`
				- `language-service`
				- `localize`
				- `platform-browser`
				- `platform-browser-dynamic`
				- `platform-server`
				- `router`
				- `service-worker`
				- `upgrade`
				- `zone.js`
		- **<描述 subject>**
		  collapsed:: true
			- Summary in present tense. Not capitalized. No period at the end.
			- 總結現在時態。首字母小寫。句尾不加句號。
			- 盡量讓 Commit 單一化，一次只更動一個主題
		-
		- **structural 結構**
		  collapsed:: true
			- **fix:** 修正 bug 錯誤
			  logseq.order-list-type:: number
			- **feat:** 新增功能
			  logseq.order-list-type:: number
			- **BREAKING CHANGE:** 重大 API 變更
			  logseq.order-list-type:: number
				- footer 以 `BREAKING CHANGE:` 開頭
				  logseq.order-list-type:: number
				- 作用範圍後有 `!`: **type(scope)!**
				  logseq.order-list-type:: number
		- **Specification 規範**
		  collapsed:: true
			- 每個 commit 一定要有 type。type 後必須接一個冒號與空格。
			  logseq.order-list-type:: number
			- scope 為 commit 影響的範圍，可選擇性填寫 optional，若有 scope 則必須寫在括號內。
			  logseq.order-list-type:: number
			- subject  為必填。對於 commit 的簡短總結。
			  logseq.order-list-type:: number
			- 在 subject 之後可以加上詳細的描述(正文 body)。必須空一行後開始撰寫。body 為自由格式。
			  logseq.order-list-type:: number
			- body 後可以加上頁腳 footer。必須空一行後開始撰寫。
			  logseq.order-list-type:: number
			- footer 必須包含一個符記 (word token)，並接着以 `:<space>` 或 `<space>#` 分隔，再緊鄰一個字串值。例如：`Refs #133`
			  logseq.order-list-type:: number
			- footer 的符記必須使用 `-` 作為空白字元，如 `Acked-by` （這有助於區分出頁腳與多段落的正文）。 但 `BREAKING CHANGE` 則為例外，且也可以作為符記使用。
			  logseq.order-list-type:: number
			- 若放置於 footer，重大變更必須維持大寫文字 `BREAKING CHANGE`，而後緊鄰一個冒號與空格，並接着描述。如： *BREAKING CHANGE: environment variables now take precedence over config files* 。
			  logseq.order-list-type:: number
			- 若作為 type／scope 的前綴，重大變更必須以一個 `!` 識別，並緊鄰於 `:` 之前。若使用 `!`， 頁腳段落的 `BREAKING CHANGE:` 則可以被省略，且提交說明應當用來描述重大變更。
			  logseq.order-list-type:: number
- ## Reference
	- [Contributing to Angular](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)
	- [約定式提交](https://www.conventionalcommits.org/zh-hant/v1.0.0/)