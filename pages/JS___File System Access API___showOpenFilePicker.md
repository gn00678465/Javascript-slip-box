category:: Programming
type:: #Javascript, #[[File System Access API]]
alias:: showOpenFilePicker

- > 呼叫此方法會開啟一個檔案選擇器, 允許使用者選擇一個或多個檔案，並返回這些檔案的 `FileSystemFileHandle` 物件
- ## Syntax
	- ```js
	  showOpenFilePicker(options)
	  ```
	- **Parameters**
	  collapsed:: true
		- `options`: [optional]
			- `multiple`: 是否允許選擇多個檔案, 預設為 `false`
			- `excludeAcceptAllOption`: 是否排除 types 所設定的檔案類型, 預設為 `false`
			- `types`: 可選擇的檔案類型，為一個陣列
				- `description`: 表示檔案或資料夾的描述
				- `accept`: 過濾的檔案類型, 為一個陣列, 值為檔案的 [MIME 類型](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types)
		- ```typescript
		  interface Type {
		    description: string;
		    accept: {
		      [key: string]: string[];
		    };
		  }
		  
		  interface Options {
		    multiple: boolean;
		    excludeAcceptAllOption: boolean;
		    types: Type[];
		  }
		  ```
	- **Return**
		- 回傳一個 **Promise** 物件,  陣列內包含 [[FileSystemFileHandle]] 的物件
		- ```typescript
		  Promise<Array<FileSystemFileHandle>>
		  ```
- ## Reference
	- [MDN - Window: showOpenFilePicker() method](https://developer.mozilla.org/en-US/docs/Web/API/window/showOpenFilePicker)