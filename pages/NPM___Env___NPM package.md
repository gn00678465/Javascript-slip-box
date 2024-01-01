category:: Environment
type:: #Note, #Vite
alias:: Vite - NPM package

- **vite-plugin-dts**
	- ```bash
	  pnpm add vite-plugin-dts -D
	  ```
- **修改 vite.config.ts**
	- ```ts
	  // ...
	  import dts from 'vite-plugin-dts';
	  
	  export default defineConfig({
	    // ...
	    plugins: [dts({ rollupTypes: true })],
	    build: {
	      sourcemap: true,
	      lib: {
	        entry: resolve(__dirname, 'src/index.ts'),
	        name: 'main',
	        formats: ['es', 'cjs', 'umd', 'iife'],
	        fileName: (format) => `index.${format}.js`,
	      },
	    },
	  });
	  ```
- **修改 package.json**
	- 檔案路徑需對應 vite.config.ts 內的設定
	- ```bash
	  npm pkg set main="./dist/index.cjs.js"
	  npm pkg set module="./dist/index.es.js"
	  npm pkg set types="./dist/index.d.ts"
	  npm pkg set files[0]="dist"
	  ```
		- `main`: 對應 commonjs
		- `module`: 對應 ESModule
		- `types`: 對應型別定義檔
	- ```bash
	  npm pkg set exports["."].require="./dist/index.cjs.js"
	  npm pkg set exports["."].import="./dist/index.es.js"
	  npm pkg set exports["."].types="./dist/index.d.ts"
	  ```
		- `require`: 對應 commonjs
		- `import`: 對應 ESModule
		- `types`: 對應型別定義檔
- ## Reference
	- [vite-plugin-dts](https://github.com/qmhc/vite-plugin-dts/tree/6b9d94c8f9f496326425e42fb88bd8a0b12e9b81)