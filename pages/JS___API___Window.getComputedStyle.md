category:: Programing
type:: Javascript, API
alias:: window.getComputedStyle

- > 取得給定元素的所有 CSS 屬性值
- ```javascript
  getComputedStyle(element[, pseudoElt])
  ```
- **Parameters**
	- `element: Element`: DOM 元素
	- `pseudoElt: string | null`: 偽元素名稱
- **Return**
	- [`CSSStyleDeclaration`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration) object, read-only
- **Methods**
	- ```javascript
	  getComputedStyle(element[, pseudoElt]).getPropertyValue(property)
	  ```
	- `getPropertyValue(property)`: 取得給定 CSS  property 的值
		- **Parameters**:
			- property: CSS  property (**不支援 Camel-Case**) 或 CSS 變數名稱
		- **Return**: `string`
			- CSS  property 值
	- `setProperty(property, value)`
		- **Parameters**:
			- property: CSS  property
			- value: CSS  property 值
- ## Reference
	- [MDN Docs - getComputedStyle](https://developer.mozilla.org/zh-TW/docs/Web/API/Window/getComputedStyle)