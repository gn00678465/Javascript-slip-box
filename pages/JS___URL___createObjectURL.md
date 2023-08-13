category:: Programing
type:: #Javascript
alias:: URL.createObjectURL

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