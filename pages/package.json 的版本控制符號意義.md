category:: Environment
type:: #Node.js
alias:: package.json 的版本控制符號意義

- ## 語意化版本 （**Semantic Versioning**）
	- 版本號: `x.xx.xx`
	- | Code status | Stage | Rule | Example version |
	  | ---- | ---- | ---- |
	  | First release | New product | Start with 1.0.0 | 1.0.0 |
	  | Backward compatible bug fixes | Patch release | Increment the third digit | 1.0.1 |
	  | Backward compatible new features | Minor release | Increment the middle digit and reset last digit to zero | 1.1.0 |
	  | Changes that break backward compatibility | Major release | Increment the first digit and reset middle and last digits to zero | 2.0.0 |
	- 第一段為大版本號**（major）**: 重大改變（**BREAKING CHANGE**）
	- 第二段為次要版本號**（minor）**: 主要為功能更新
	- 第三段為小修改**（patch）**: 修復BUG 等
## 版本控制符號
	- `^`: 鎖住**第一段**不得變更。如`^1.2.2`，則安裝範圍是`>=1.2.2` 且 `<2.0.0`。即須符合`1.*.*`。
	- `~`: 鎖住**第二段**不得變更。如`~1.2.2`，則安裝範圍是`>=1.2.2`且`<1.3.0`。即須符合`1.2.*`。
	- `~` 跟 `^` 最大差別就是鎖定的版本號位置**不得高於該版本號碼**
- ## Reference
	- [npm Docs - About semantic versioning](https://docs.npmjs.com/about-semantic-versioning)