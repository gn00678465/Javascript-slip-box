category:: Programing
type:: Javascript, API
alias:: ResizeObserver

- > 本身為建構式，需使用 `new` 建立實體
- ```javascript
  const observer = new ResizeObserver(callback);
  ```
- **params**
	- `callback: (entries, owner) => viod`
		- `entries:  ResizeObserverEntry[]`: 觀察的 Dom 元素尺寸變化的相關資訊，[ResizeObserverEntry](https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry)
- **Methods**
	- `observe(target, [options])`: 觀察指定的 Dom 元素
		- `target: HTMLElement`: Dom 元素
		- `options`: 初始化觀測的設定選項
			- ```typescript
			  interface Options {
			    box?: 'content-box' | 'border-box'
			  }
			  ```
	- `unobserve(target: HTMLElement)`: 註銷某 Dom 元素的觀察
	- `disconnect()`: 一次性的註銷所有元素的觀察
## Reference
	- [ResizeObserver - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver)
	- [检测DOM尺寸变化JS API ResizeObserver简介](https://www.zhangxinxu.com/wordpress/2020/03/dom-resize-api-resizeobserver/)