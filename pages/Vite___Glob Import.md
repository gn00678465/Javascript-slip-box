category:: Environment
type:: #Vite
alias:: Glob Import
version:: 3.x+

- > Vite 特有功能，透過 file system 批次載入模組，編譯後會分離為獨立模組
- ```typescript
  const modules = import.meta.glob(pattern, options);
  ```
- **pattern** (`string | string[]`): 匹配的檔案名稱，可帶入多組
	- 路徑只支援：`./` 相對路徑、`/` 絕對路徑、使用 [`resolve.alias`](https://vitejs.dev/config/shared-options.html#resolve-alias) 所設定的路徑別名。
	- 未設定 `config` 預設以動態且為 lazy-loaded 方式載入, `() => import(/* matched file */)`
	- 匹配多組(`string[]`): `['pattern_1', 'pattern_2']`
	- 排除特定(`string[]`): 要排除的比對項目前綴加上 **`!`** , `['pattern_1', '!pattern_2']`
- **options**
	- ```typescript
	  interface ImportGlobOptions {
	    eager?: boolean;
	    as?: 'raw' | 'url';
	    import?: string | 'default';
	    query?: object;
	  }
	  ```
	- `eager`: 改為直接載入
	- `as`: 以字串方式載入
	- Named Imports (`{ import: string }`) : 載入對應的 Named exports
	- Default Imports  (`{ import: default }`) : 載入 Default exports
	- `query`: 帶入搜尋設定
- ## Useage
	- ```typescript
	  const modules: unknown[] = import.meta.glob('./**.ts', { eager: true });
	  
	  Object.keys(modules).forEach((module) => {
	    /** do something */
	  })
	  ```
- ## Reference
	- [Glob Import](https://vitejs.dev/guide/features.html#glob-import)
	- [importGlob.d.ts](https://github.com/vitejs/vite/blob/10757b84009b27744b0645b75e7951bbbac6a928/packages/vite/types/importGlob.d.ts)