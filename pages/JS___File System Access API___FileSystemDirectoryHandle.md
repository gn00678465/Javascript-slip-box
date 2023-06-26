category:: Programing
type:: Javascript, File System Access API
alias:: FileSystemDirectoryHandle

- ## Properties
	- 繼承 [[FileSystemHandle]] 所有屬性
## Methods
	- 繼承 [[FileSystemHandle]] 所有方法
	- `entries`: 回傳 [async iterable objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#the_async_iterator_and_async_iterable_protocols), 用於取得目錄中所有的檔案與目錄, `[key, value]`
	- `keys`: 回傳 **async iterable objects**, 用於取得目錄中所有的檔案與目錄名稱
	- `values`: 回傳 **async iterable objects**, 用於取得目錄中所有的檔案與目錄的 [[FileSystemDirectoryHandle]] 物件
	- `getFileHandle`: 回傳 **Promise** 物件, 用於取得目錄中的特定檔案
		- **Parameters**:
			- `name`: 指定檔案名稱
			- `options`:
				- `create`: 預設為 `false`, 當檔案不存在會自動建立並回傳
		- **Return**: 回傳一個 **Promise**  [[FileSystemFileHandle]] 的物件
	- `getDirectoryHandle`: 回傳 **Promise** 物件, 用於取得目錄中的特定目錄
		- **Parameters**:
			- `name`: 指定目錄名稱
			- `options`:
				- `create`: 預設為 `false`, 當目錄不存在會自動建立並回傳
		- **Return**: 回傳一個 **Promise** [[FileSystemDirectoryHandle]] 的物件
	- `removeEntry`: 回傳 **Promise** 物件, 用於刪除目錄中的檔案或目錄
		- **Parameters**:
			- `name`: 指定檔案或目錄名稱
			- `options`:
				- `recursive`: 預設為 `false`, 設定為 `true` 會遞迴去移除符合的檔案或目錄
		- **Return**: 回傳一個 **Promise** `undefined` 的物件
	- `resolve`: [resolve](https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle/resolve)
- ## Reference
	- [MDN - Interface: FileSystemDirectoryHandle](https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle)