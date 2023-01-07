category:: Environment
type:: Vite,Config
alias:: vite 使用 https 認證

- ## vite 使用 https 認證
- 需先安裝 [[Certificate/mkcert]] 產生本地端憑證
- 產生簽證後，需要於 `vite.config.js` 內設定
  ```ts
  // vite.config.ts
  import { defineConfig } from 'vite';
  import fs from 'fs';
  
  export default defineConfig({
  	server: {
      	https: {
          	key: fs.readFileSync('產生的憑證位址(key)'),
        		cert: fs.readFileSync('產生的憑證位址'),
          }
      }
  })
  ```
- 重新啟動開發 server，就可以使用 https 進入開發網址