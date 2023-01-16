category:: Programing
type:: Javascript, API
alias:: MutationObserver

- > 本身為建構式，需使用 `new` 建立實體
- ```javascript
  const observer = new MutationObserver(callback)
  ```
- **params**
	- `callback: (entries, owner) => viod`
		- `entries:  MutationRecord[]`: 觀察 Dom 元素的子節點、內容、屬性的變動，[MutationRecord](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord)
		- `owner: MutationObserver`: 呼叫 callback 的 MutationObserver 實體
- **Methods**
	- `observe(target, options)`
		- `target: HTMLElement`:
		- `options`:
	- `disconnect()`:
	- `takeRecords()`:
- ## Reference
	- [MutationObserver API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)