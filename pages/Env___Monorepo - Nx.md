category:: Environment
type:: #Env, #Monorepo
alias:: Monorepo - Nx

- ### 資料夾結構
	- ```plain
	  org/
	    ├── apps/
	    ├── libs/
	    ├── tools/
	    ├── nx.json
	    ├── package.json
	    └── tsconfig.base.json
	  ```
	- **org**: Nx專案名稱
	- **apps**: 存放各種專案，也是所有專案中主要的進入點
		- 建議所有此資料夾中的專案應該要越輕量越好
		- 檔案比較大的程式且可重複利用的程式碼應該要放在Libraries之中，並且在各個專案中進行載入
	- **libs**: 包含所有的library 專案
	- **tools**: 包含一些常使用的程式碼腳本，也可以將參數放置於此資料夾
		- 例如：資料庫的設定與腳本
	- **nx.json**: 根據Nx CLI去做配置，也會透過此檔案告知Nx有哪些需要進行快取，或是如何執行
	- **tsconfig.base.json**: 設定全域TypeScript，並且在每個library 之中建立別名（aliases）
- ## Reference
	- [Nx](https://nx.dev/)
	- [為何大公司都使用Nx ?](https://vocus.cc/article/62ef5c81fd89780001e0311e)