category:: Programming
type:: #Node.js, #Express
alias:: Express.js - 使用靜態檔案

- 將含有靜態資產的目錄名稱傳遞給 Middleware `express.static`
- ```javascript
  app.use(express.static('public'));
  app.use(express.static('files'));
  ```
- ## 虛擬路徑
- > 隱藏真實的路徑，為靜態檔案提供一個事實上不存在的資料夾
- ```javascript
  app.use('/static', express.static('public'));
  ```
- 提供給 `express.static` 函數的路徑，是相對於您從中啟動 `node` 程序的目錄。
- 當從另一個目錄執行 Express 應用程式時，靜態檔案的路徑會錯誤
- 保險的做法是提供一個絕對路徑給 `express.static` 。
- ```javascript
  app.use('/static', express.static(__dirname + '/public'));
  ```