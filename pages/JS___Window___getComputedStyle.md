category:: Programing
type:: #Javascript
alias:: window.getComputedStyle

- > 取得給定元素的所有 CSS 屬性值
- ## Syntax
- ```javascript
  getComputedStyle(element[, pseudoElt])
  ```
- **Parameters**
	- **`element`**
		- Type: `Element`
		- DOM 元素
	- **`pseudoElt`** <span class="badge">optional</span>
		- Type: `string | null | undefined`
		- 偽元素名稱
- **Return** <span class="badge">read-only</span>
	- Type: `CSSStyleDeclaration`
	- `CSSStyleDeclaration` object
- **Methods**
	- ```javascript
	  getComputedStyle(element[, pseudoElt]).getPropertyValue(property)
	  ```
	- **`getPropertyValue(property)`**: 取得給定 CSS  property 的值
		- **Parameters**:
			- **`property`**: CSS  property (**不支援 Camel-Case**) 或 CSS 變數名稱
		- **Return**: `string`
			- CSS  property 值
	- **`setProperty(property, value)`**
		- **Parameters**:
			- **`property`**: CSS  property
			- **`value`**: CSS  property 值
- ## Reference
	- [MDN Docs - getComputedStyle](https://developer.mozilla.org/zh-TW/docs/Web/API/Window/getComputedStyle)
	- [CSSStyleDeclaration](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)