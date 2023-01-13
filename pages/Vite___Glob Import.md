category:: Environment
type:: Vite
alias:: Glob Import
version:: 3.x+

- > Vite 特有功能，透過 file system 批次載入模組
- ```typescript
  const modules = import.meta.glob(pattern, config);
  ```
- **pattern**: 匹配的檔案名稱，可帶入多組
	- 路徑只支援：`./` 相對路徑、`/` 絕對路徑、使用 [`resolve.alias`](https://vitejs.dev/config/shared-options.html#resolve-alias) 所設定的路徑別名。
	- 未設定 `config` 為動態載入 `() => import(/* matched file */)`
	- 匹配多組(`string[]`): `['pattern_1', 'pattern_2']`
	- 排除特定(`string[]`): 要排除的比對前綴加上 **`!`** , `['pattern_1', '!pattern_2']`
- **config**
	- `eager`
	- `as`
	- `import`
	- `query`