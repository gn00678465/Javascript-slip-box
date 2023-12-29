category:: Environment
type:: #Npm, #Env
alias:: Formatter - Prettier

- **Prettier**
	- ```bash
	  pnpm add -D prettier
	  ```
- **建立 .prettierignore**
	- ```plain
	  coverage
	  public
	  dist
	  npnm-lock.yaml
	  ```
- **建立設定檔 .prettierrc.yaml**
	- ```yaml
	  singleQuote: true
	  ```
- **VS Code plugin**
	- 安裝 Extensions - [Link](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
	- 在 **.vscode/settings.json** 內設定
	- ```json
	  {
	    "editor.formatOnSave": true,
	    "editor.defaultFormatter": "esbenp.prettier-vscode",
	    "prettier.configPath": "",
	  }
	  ```
	- `prettier.configPaht`: 對應建立於當前專案的設定檔
- **新增 scripts**
	- ```bash
	  npm pkg set scripts.format="prettier --write ."
	  ```