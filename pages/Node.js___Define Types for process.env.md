category:: Environment
type:: #Node.js, #Typescript
alias:: Define Types for process.env

- Create a new file **process-env.d.ts** in the root of project folder
  logseq.order-list-type:: number
- add the following code into **process-env.d.ts**
  logseq.order-list-type:: number
	- ```ts
	  declare global {
	    namespace NodeJS {
	      interface ProcessEnv {
	        [key: string]: string | undefined;
	        PORT: string;
	        // add more environment variables and their types here
	      }
	    }
	  }
	  ```
- 調整 **tsconfig.json** 設定
  logseq.order-list-type:: number
	- ```json
	  {
	    "compilerOptions": {/* ... */},
	    "include": ["process-env.d.ts", "src"]
	  }
	  ```