category:: Programming
type:: Javascript, File System Access API
alias:: FileSystemFileHandle

- ## Properties
	- 繼承 [[FileSystemHandle]] 所有屬性
- ## Methods
	- 繼承 [[FileSystemHandle]] 所有方法
	- `getFile`: 回傳 **Promise** 物件, 用於取得 file 物件
	- `createSyncAccessHandle`: 回傳 **Promise** 內為 [`FileSystemSyncAccessHandle`](https://developer.mozilla.org/en-US/docs/Web/API/FileSystemSyncAccessHandle) 物件, 用於同步訪問檔案
	- `createWritable`: 回傳 **Promise** 內為 [`FileSystemWritableFileStream`](https://developer.mozilla.org/en-US/docs/Web/API/FileSystemWritableFileStream) 物件, 用於寫入檔案
- ## Reference
	- [MDN - Interface: FileSystemFileHandle](https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileHandle)