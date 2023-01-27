category:: Programing
type:: Node.js
alias:: Cookie、session

- ## Cookie
	- 可存在 client 瀏覽器內，單一 value 的容量上限約 4k
	- 可於 client 或 Server 端刪除 修改
	- 以 name-value pair 為一組組成，多組須使用**分號**與**空格**相隔
	- ### Useage
		- 需安裝 cookieParser
			- ```bash
			  npm install cookie-parser
			  ```
		- Example
			- ```javascript
			  app.use(cookieParser([secret]));
			  
			  app.get('/', (req, res) => {
			    let cookies = req.cookies; // 讀取
			    res.cookie([name], [value], options); // 寫入
			    res.clearCookie([name]); // 刪除
			  })
			  ```
			- `[secret]`: 加簽字串
			- |屬性|type|描述|
			  |--|--|--|
			  |HttpOnly|`boolean`|無法使用 Javascript 存取|
			  |Secure|`boolean`|只要網站開頭不是 https 開頭的網站都沒有辦法獲得 Cookie 中的資訊|
			  |Max-Age|`number`|指定 cookie 可存活的時間|
			  |Expires|`string`|指定時間後 cookie 失效|
			  |Domain|`string`|指定網域|
			  |Path|`string`|指定網域下的路徑|
			  |Signed|`boolean`|啟用加簽，但 cookie-parser 也必須要有加簽的字串|
- ## Session
	- 暫存資料在伺服器記憶體內，重啟伺服器就會消失
	- 可以搭配 cookie 和 DB  保留資料
	- ### Useage
		- 安裝
			- ```bash
			  npm install express-session
			  ```
		- 設定
			- ```javascript
			  app.use(session(options);
			  ```
			-
- ## Reference
	- [白話 Session 與 Cookie：從經營雜貨店開始](https://hulitw.medium.com/session-and-cookie-15e47ed838bc)