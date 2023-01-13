category:: Environment
type:: Vite
alias:: Glob Import
version:: 3.x+

- > Vite 特有功能，透過 file system 批次載入模組，編譯後會分離為獨立模組
- ```typescript
  const modules = import.meta.glob(pattern, config);
  ```
- **pattern** (`string | string[]`): 匹配的檔案名稱，可帶入多組
	- 路徑只支援：`./` 相對路徑、`/` 絕對路徑、使用 [`resolve.alias`](https://vitejs.dev/config/shared-options.html#resolve-alias) 所設定的路徑別名。
	- 未設定 `config` 預設為動態載入且為 lazy-loaded, `() => import(/* matched file */)`
	- 匹配多組(`string[]`): `['pattern_1', 'pattern_2']`
	- 排除特定(`string[]`): 要排除的比對項目前綴加上 **`!`** , `['pattern_1', '!pattern_2']`
- **config** (`object`)
	- `eager` (`boolean`): 改為直接載入
	- `as` (`raw | url`): 以字串方式載入
	- `import` (`string | default`):
		- Named Imports (`{ import: string }`) :
		- default:
	- `query` (`object`):
- ## Useage
	- ```typescript
	  const modules = import.meta.glob('./**.ts', { eager: true });
	  
	  for (module in modules) {
	    console.log(module)
	  }
	  ```
- ## Reference
	- [Glob Import](https://vitejs.dev/guide/features.html#glob-import)