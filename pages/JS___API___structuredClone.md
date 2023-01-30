category:: Programing
type:: Javascript, API
alias:: structuredClone

- > 使用稱為結構複製的演算法將給定的 value 進行深拷貝
- ```javascript
  const deepClone = structuredClone(value[, options])
  ```
- **Params**
	- `value`: 要拷貝的值，須為[結構複製支援的類型](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Workers_API/Structured_clone_algorithm#%E6%94%AF%E6%8C%81%E7%9A%84%E7%B1%BB%E5%9E%8B)
	- `options`:
		- `transfer`: 帶入 [transferable objects](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Transferable_objects) 類型的 Array
- **Return**
	- 傳入 value 的深拷貝
- ### 限制
	- **Prototypes**: 如果使用 `structuredClone()` 複製某類別物件實例 Class Instance 只會取得單純的物件不會包含 `prototype` 的部分
	- **Functions**: 如果 object 包含了函式則會被移除
	- **Non-cloneables**: 有些值是不可複製的例如 `Error` 和 DOM 節點
- ## Reference
	- [MDN Docs - structuredClone](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)