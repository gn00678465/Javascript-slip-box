category:: Environment
type:: #Note, #Vite
alias:: Vite - Absolute path import support

-
	- ```bash
	  pnpm add -D @types/node
	  ```
- **建立 vite.config.ts 設定檔**
	- ```ts
	  import { defineConfig } from 'vite'
	  import { fileURLToPath, URL } from "node:url";
	  
	  // https://vitejs.dev/config/
	  export default defineConfig({
	    resolve: {
	      alias: {
	        "@": fileURLToPath(new URL("./src", import.meta.url))
	      }
	    },
	  })
	  ```