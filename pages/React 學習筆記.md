category:: programing
type:: react

- ## Intro basic
	- ### JSX 與 HTML 的標籤屬性
		- `class` 須改為 `className`
		- `inline style` 須使用 `object` 寫法
		- `Input` 標籤中
			- `checked` 須改為 `defaultChecked`
			- `value` 須改為 `defaultValue`
			- `label` 標籤的 `for` 屬性須改為 `htmlFor`
			- `textarea` 的值須使用 `defaultValue`
			- `select` 需使用 `defaultValue`，並綁訂於 `select` 標籤上
		- render HTML 因為安全性問題，須改為下列語法
			- ```jsx
			  <div dangerouslySetInnerHTML={{__html: 'First &middot; Second'}}></div>
			  ```
- ## Component
	- component 必須以大寫開頭