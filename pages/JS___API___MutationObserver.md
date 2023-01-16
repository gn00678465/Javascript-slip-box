category:: Programing
type:: Javascript, API
alias:: MutationObserver

- > 本身為建構式，需使用 `new` 建立實體
- ```javascript
  const observer = new MutationObserver(callback)
  ```
- **params**
	- `callback: (entries, owner) => viod`
		- `entries:  MutationRecord[]`: 觀察 Dom 元素的子節點、內容、等屬性變動資訊，[MutationRecord](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord)
		- `owner: MutationObserver`: 呼叫 callback 的 MutationObserver 實體
- **Methods**
	- `observe(target, options)`: 觀察指定的 Dom 元素
		- `target: HTMLElement`: Dom 元素
		- `options`:  一個初始化設定物件，用來指定 DOM 節點的哪些項目需要被觀察等相關設定。[observe - options](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/observe#syntax)
			- |Properties|Explain|Type|Default|
			  |childList||Boolean|`false`|
			  |subtree||Boolean|`false`|
	- `disconnect()`: 一次性的註銷所有元素的觀察
	- `takeRecords()`:
- ## Reference
	- [MutationObserver API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)