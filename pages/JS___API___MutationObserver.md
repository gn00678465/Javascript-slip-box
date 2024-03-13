category:: Programming
type:: #Javascript, #API
alias:: MutationObserver

- > 本身為建構式，需使用 `new` 建立實體
- ## Syntax
	- ```javascript
	  const observer = new MutationObserver(callback)
	  ```
	- **Parameters**
		- `callback: (entries, owner) => viod`
			- `entries:  MutationRecord[]`: 觀察 Dom 元素的子節點、內容、等屬性變動資訊，[MutationRecord](https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord)
- ### Methods
	- `observe(target, [options])`: 觀察指定的 Dom 元素
		- `target: HTMLElement`: Dom 元素
		- `options`:  一個初始化設定物件，用來指定 DOM 節點的哪些項目需要被觀察等相關設定。
			- [observe - options](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/observe#syntax)
			- ```typescript
			  interface Options{
			    childList?: boolean;
			    subtree?: boolean;
			    attributes?: boolean;
			    characterData?: boolean;
			    attributeOldValue?: boolean;
			    characterDataOldValue?: boolean;
			    attributeFilter?: string[];
			  }
			  ```
			- |Properties|Explain|Default|
			  |childList|是否觀察節點的直屬子節點變動|`false`|
			  |subtree|是否觀察節點的所有子節點變動|`false`|
			  |attributes|是否觀察節點的屬性變動|`false`|
			  |characterData|是否觀察節點的內容變動|`false`|
			  |attributeOldValue|是否紀錄變動前的屬性值|`false`|
			  |characterDataOldValue|是否紀錄變動前的內容值|`false`|
			  |attributeFilter|需要觀察的屬性名稱，如果為空則全部觀察|`[]`|
	- `disconnect()`: 一次性的註銷所有元素的觀察
	- `takeRecords()`:
- ## Reference
	- [MutationObserver API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)