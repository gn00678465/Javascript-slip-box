category:: Programing
type:: #Javascript
alias:: URL.createObjectURL

- ## Intro
	- 建立一個帶有 URL 的 DOMString 以代表參數中所傳入的物件
	  logseq.order-list-type:: number
	- 生命週期與創造它的 `window` 中的 document 相同
	  logseq.order-list-type:: number
	- 此物件 URL 代表了所指定的 File 物件、 Blob 物件「參考」
	  logseq.order-list-type:: number
	- 每次呼叫 `createObjectURL` 都會產生一個新的 URL
	  logseq.order-list-type:: number
	- 建議當物件不再被使用時，手動透過 [[URL.revokeObjectURL]] 釋放記憶體，藉此最佳化效能與記憶體用量
	  logseq.order-list-type:: number
- ## Syntax
	- ```ts
	  objectURL = URL.createObjectURL(object)
	  ```
	- **Parameters**
		- **`object`**: `Blob | File | MediaSource`
			- 轉換成一個帶有 **URL** 的 **DOMString** 以代表參數中所傳入的物件，處理上傳圖片數據、可以用來顯示影片或圖片，不需要將 **Blob** 物件轉換成 **Base64** 編碼或其他格式，可以節省 **Memory** 記憶體和效能。
	- **Return**
		- **`objectURL`**: `string`
- ## Reference
	- [MDN - createObjectURL](https://developer.mozilla.org/zh-TW/docs/Web/API/URL/createObjectURL_static)