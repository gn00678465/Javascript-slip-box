category:: Programing
type:: Node.js
alias:: 取得環境路徑

- Node.js 中取得環境路徑的方式
	- `__dirname`: 總是回傳被執行 JS 檔**所在資料夾**的絕對路徑
	- `__filename`: 總是回傳被執行 **JS 檔**的絕對路徑
	- `process.cwd()`: 總是回傳**執行 node 指令**時所在的資料夾之絕對路徑
	- `./`: 同 `process.cwd()`