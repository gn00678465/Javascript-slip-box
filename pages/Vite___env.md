- ## Env Variables
	- > Vite 的環境變數使用特定的 Object `import.meta.env` exposes 出來，在開發的時候可以使用這個變數
	- `import.meta.env.MODE`: {string} 當前的模式
	- `import.meta.env.BASE_URL`: {string} deploy 時的 URL
	- `import.meta.env.PROD`: {boolean} 判斷是否為 production 模式
	- `import.meta.env.DEV`: {boolean} 判斷是否為 development 模式
	- `import.meta.env.SSR`: {boolean} 判斷是否為 SSR 模式
- ## .env files
	- > 設定變數只能使用靜態的 string，動態的方式不會生效
	- `.env`: 所有模式下都會載入
	- `.env.local`: 會被 git 忽略
	- `.env.[mode]`: 指定模式下載入，優先於 `.env`
	- `.env.[mode].local`: 會被 git 忽略
- ## Typescript
	- 加入自定義的環境變數定義檔
	- `src` 下建立 `env.d.ts` 類型定義檔
		- ```typescript
		  /// <reference types="vite/client" />
		  
		  interface ImportMetaEnv {
		    readonly VITE_APP_TITLE: string
		    // 自定義的環境變數...
		  }
		  
		  interface ImportMeta {
		    readonly env: ImportMetaEnv
		  }
		  ```
- ## Reference
	- [Env Variables and Modes](https://vitejs.dev/guide/env-and-mode.html)