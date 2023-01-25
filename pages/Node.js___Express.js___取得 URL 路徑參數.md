category:: Programing
type:: Node.js
alias:: Express.js 取得 URL 路徑參數

- ## 取得 URL 路徑參數
	- ```javascript
	  const app = express();
	  
	  app.get('/path/:[param]', (res, req) => {
	    const params = req.params;
	  });
	  ```
	- **param**: 可以為自訂路徑名稱
	- 從 `req.params` 內取得上面所自訂的路徑名稱
- ## 取得 URL query
	- ```javascript
	  const app = express();
	  
	  app.get('/path', (res, req) => {
	    const query = req.query;
	  });
	  ```
	- 路徑後方帶入以 `?key=value` 格式的字串，多個參數以「`&`」隔開
	- 從 `req.query` 內取得上面所自訂的 query