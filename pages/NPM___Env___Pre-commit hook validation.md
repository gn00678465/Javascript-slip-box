## lint-staged
	- ```bash
	  pnpm add -D husky lint-staged
	  ```
	- **建立設定檔 .lintstagedrc.yaml**
		- ```yaml
		  '*.{js,ts,tsx}':
		    - eslint --fix
		  '**/*':
		    - 'prettier --write --ignore-unknown'
		  
		  ```
- ## commitlint
	- ```bash
	  pnpm add -D @commitlint/cli @commitlint/config-conventional
	  ```
	- **建立設定檔 .commitlintrc.yaml**
		- ```yaml
		  extends:
		    - "@commitlint/config-conventional"
		  ```
		- 其他的設定參數
		  collapsed:: true
			- ```yaml
			  
			  parserPreset: "conventional-changelog-conventionalcommits"
			  rules:
			    type-empty:
			      - 2
			      - "never"
			    type-case:
			      - 2
			      - "always"
			      - "lower-case"
			    type-enum:
			      - 2
			      - "always"
			      - [
			          "build",
			          "chore",
			          "ci",
			          "docs",
			          "feat",
			          "fix",
			          "perf",
			          "refactor",
			          "revert",
			          "style",
			          "test",
			          "types"
			        ]
			    subject-empty:
			      - 2
			      - "never"
			    subject-case:
			      - 2
			      - "never"
			      - ["sentence-case", "start-case", "pascal-case", "upper-case"]
			    subject-full-stop:
			      - 2
			      - "never"
			      - "."
			    body-leading-blank:
			      - 2
			      - "always"
			    header-max-length:
			      - 2
			      - "always"
			      - 100
			    footer-leading-blank:
			      - 1
			      - "always"
			    footer-max-line-length:
			      - 2
			      - "always"
			      - 100
			  prompt:
			    questions:
			      type:
			        description: "Select the type of change that you're committing"
			        enum:
			          feat:
			            description: "A new feature"
			            title: "Features"
			            emoji: "✨"
			          fix:
			            description: "A bug fix"
			            title: "Bug Fixes"
			            emoji: "🐛"
			          docs:
			            description: "Documentation only changes"
			            title: "Documentation"
			            emoji: "📚"
			          style:
			            description: "Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)"
			            title: "Styles"
			            emoji: "💎"
			          refactor:
			            description: "A code change that neither fixes a bug nor adds a feature"
			            title: "Code Refactoring"
			            emoji: "📦"
			          perf:
			            description: "A code change that improves performance"
			            title: "Performance Improvements"
			            emoji: "🚀"
			          test:
			            description: "Adding missing tests or correcting existing tests"
			            title: "Tests"
			            emoji: "🚨"
			          build:
			            description: "Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)"
			            title: "Builds"
			            emoji: "🛠"
			          ci:
			            description: "Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)"
			            title: "Continuous Integrations"
			            emoji: "⚙️"
			          chore:
			            description: "Other changes that don't modify src or test files"
			            title: "Chores"
			            emoji: "♻️"
			          revert:
			            description: "Reverts a previous commit"
			            title: "Reverts"
			            emoji: "🗑"
			          types:
			            description: "Type definition file changes"
			            title: "Types"
			            emoji: "🌟"
			  ```
- ### commitlint: Use prompt
	- ```bash
	  pnpm add -D @commitlint/prompt commitizen
	  ```
	- **設定**
	- ```bash
	  npm pkg set scripts.commit="git-cz"
	  npm pkg set config.commitizen.path="@commitlint/prompt"
	  ```
	- **Usage**
	- ```bash
	  git add .
	  pnpm commit
	  ```
- ## husky
	- ```bash
	  npx husky install
	  npm pkg set scripts.prepare="husky install"
	  ```
	- **建立 hooks 指令**
	- ```bash
	  npx husky add .husky/pre-commit "pnpm lint-staged"
	  npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'
	  ```
- ## Reference
	- [commitlint](https://github.com/conventional-changelog/commitlint)