category:: Environment
type:: #note
alias:: Linting - ESLint

- **ESLint**
	- ```bash
	  pnpm create @eslint/config
	  ```
	- 依照當前的專案做選擇
- **建立 `.eslintignore`**
	- ```plain
	  coverage
	  public
	  dist
	  npnm-lock.yaml
	  ```
- **整合 Prettier with ESlint**
	- ```bash
	  pnpm add -D eslint-config-prettier eslint-plugin-prettier
	  ```
	- 在 eslintrc 設定檔中 `estends` 屬性最後加上 `plugin:prettier/recommended`
- **新增 scripts**
	- ```bash
	  npm pkg set scripts.lint="eslint ."
	  ```