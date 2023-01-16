category:: Programing
type:: Javascript, API
alias:: IntersectionObserver

- > 本身為建構式，需使用 `new` 建立實體
- ```javascript
  const observer = new IntersectionObserver(callback, options);
  ```
- **params**
	- `callback: (entries, owner) => viod`
		- `entries:  IntersectionObserverEntry[]`: 關於觀察 Dom 與 可視範圍交互的相關資訊，[IntersectionObserverEntry](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry)
		- `owner: IntersectionObserver`: 呼叫 callback 的 IntersectionObserver 實體
	- options:
		- `root: HTMLElement | null`:
			- 以特定元素的可視視窗作為觀察依據。
			- `null` 則以 Viewport 作為判斷依據。
		- `rootMargin: string`: 代表窗口的縮放，與 CSS `margin` 設定相同
		- `threshold: number | number []`: 設定觸發的**比例**，範圍由 0 ~ 1
			- **0**(預設值): 當相交範圍的比例「開始大於 0%」或「開始小於 0%」 的瞬間會觸發。
			- **1**: 當相交範圍的比例「開始大於 100%」或「開始小於 100%」 的瞬間會觸發。
- **Methods**
	- `observer(target: HTMLElement)`: 指定觀察 Dom 元素
	- `unobserve(target: HTMLElement)`: 註銷某 Dom 元素的觀察
	- `disconnect()`: 一次性的註銷所有元素的觀察
	- `takeRecords()`:
- ## Reference
	- [Intersection Observer API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)