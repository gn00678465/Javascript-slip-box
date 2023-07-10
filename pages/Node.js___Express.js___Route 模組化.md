category:: Programing
type:: #Node.js
alias:: Route 模組化

- > 將 Express 的 Route 依照不同的路徑模組化
- 在根目錄下建立資料夾 `routes`
- `routes` 內依照需求建立個別的檔案
	- 需要引入 `express`
	- ```javascript
	  // admin.js
	  const express = require('express');
	  const router = require.Router();
	  
	  router.get(path, (req, res) => {
	    // req → request
	    // res → response
	  });
	  
	  router.get('/', (req, res) => {});
	  
	  module.exports = router;
	  ```
- 在主要檔案引入模組化的 `route`
	- ```javascript
	  // app.js
	  
	  const adminRoute = require('./route/admin');
	  
	  app.use('/admin', adminRoute);
	  // 第一個參數類似命名第一層的網址 /admin/XXXX
	  ```