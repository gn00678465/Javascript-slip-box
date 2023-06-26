category:: Programing
type:: Javascript, File System Access API
alias:: showDirectoryPicker

- > 呼叫此方法會開啟一個目錄選擇器, 允許使用者選擇一個目錄
- ## Syntax
	- ```js
	  showDirctoryPicker(options)
	  ```
	- **Parameters**
		- `options`: [optional]
			- `id`: 指定 ID 名稱, 可使瀏覽器記住對應的目錄, 當使用已記錄的 ID 開啟目錄選擇器時, 會開啟已記錄的目錄
			- `mode`: 預設為 **read** 為只讀訪問, 可帶入 **readwrite** 為讀寫訪問
			- `startIn`: 為一個 `FileSystemHandle` 或者是常見的資料夾名稱(`"desktop"`, `"documents"`, `"downloads"`, `"music"`, `"pictures"`, or `"videos"`)
		- ```typescript
		  interface Options {
		    id: string;
		    mode: 'read' | 'readwrite';
		    startIn: FileSystemHandle | string;
		  }
		  ```
	- **Return**
		- 回傳一個 **Promise** 物件,  內包含 [[FileSystemDirectoryHandle]] 的物件
		- ```typescript
		  Promise<FilesSystemDirectoryHandle>
		  ```
- ## Reference
	- [MDN - Window: showDirectoryPicker() method](https://developer.mozilla.org/en-US/docs/Web/API/Window/showDirectoryPicker)