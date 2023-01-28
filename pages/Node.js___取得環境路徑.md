category:: Programing
type:: Node.js
alias:: 取得環境路徑

- Node.js 中取得環境路徑的方式
	- `__dirname`: 總是回傳被執行 JS 檔**所在資料夾**的絕對路徑
	- `__filename`: 總是回傳被執行 **JS 檔**的絕對路徑
	- `process.cwd()`: 總是回傳**執行 node 指令**時所在的資料夾之絕對路徑
	- `./`: 同 `process.cwd()`
- ## ESM(ES6 Modules)
- version:: 10.12+
- > 在 Node.js 使用 ES6 Modules, 使用 `__dirname` 會發生錯誤
- 替代 `__dirname` 的方式
- ```javascript
  import { dirname } from 'path';
  import { fileURLToPath } from 'url';
  
  const __filename = fileURLToPath(import.meta.url);
  const __dirname = path.dirname(__filename);
  ```
- ## 在 ESM 中使用 `require`
- ```javascript
  import { createRequire } from "module";
  const require = createRequire(import.meta.url);
  ```
- ## Reference
	- [Alternative for __dirname in Node.js when using ES6 modules](https://stackoverflow.com/questions/46745014/alternative-for-dirname-in-node-js-when-using-es6-modules)
	- [How to import JSON files in ES modules (Node.js)](https://www.stefanjudis.com/snippets/how-to-import-json-files-in-es-modules-node-js/)