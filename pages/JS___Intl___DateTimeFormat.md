category:: Programing
type:: #Javascript
alias:: Intl.DateTimeFormat

- > 可以根據不同的語言和地區來格式化日期和時間。
  > 使用 `new` 或不使用，皆可以建立實體
- ## Syntax
	- ```ts
	  Intl.DateTimeFormat();
	  Intl.DateTimeFormat(locales);
	  Intl.DateTimeFormat(locales, options);
	  new Intl.DateTimeFormat(locales, options);
	  ```
	- **Parameters**
		- **`locales`** <span class="badge">optional</span>
			- Type: `string | string[]`
			- BCP 47 Language Tags
		- **`options`** <span class="badge">optional</span>
			- Type: `Object`
	- **Return**
		- Type: `Intl.DateTimeFormat`
		- `Intl.DateTimeFormat` object
- ### Methods 方法
	- `resolvedOptions()`: 可以獲取目前設置下的一些訊息，例如日期格式、時間格式和時區等。
		- `locales`: 語系
		- `calendar`:
		- `timeZone`: 時區
		- `hour12`:
		- `weekday`, `era`, `year`, `month`, `day`, `hour`, `minute`, `second`, `timeZoneName`
- ## Reference
	- [Intl.DateTimeFormat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)