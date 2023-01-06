category:: Environment
type:: Vite,Config
alias:: alias

- ### vite
	- ```typescript
	  // vite.config.ts
	  
	  import { defineConfig } from "vite";
	  import path from "path";
	  
	  export default defineConfig({
	    resolve: {
	      alias: {
	        "@": path.resolve(__dirname, "./src"),
	      },
	    },
	  });
	  ```
- ### typescript
	- ```json
	  // tsconfig.json
	  {
	    "compilerOptions": {
	      "paths": {
	        "@/*": ["./src"]
	      }
	    }
	  }
	  ```
- ### vitest
	- ```typescript
	  // vitest.config.ts
	  import { defineConfig } from 'vitest/config';
	  import path from 'path';
	  export default defineConfig({
	    resolve: {
	      alias: {
	        src: path.resolve(__dirname, 'src')
	      }
	    }
	  })
	  ```
-
- ## Reference
- [How to configure import aliases in Vite, TypeScript and Jest](https://divotion.com/blog/how-to-configure-import-aliases-in-vite-typescript-and-jest)