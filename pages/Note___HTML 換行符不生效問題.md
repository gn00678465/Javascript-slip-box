category:: Note
type:: #CSS, #HTML, #Javascript
alias:: HTML 換行符不生效問題

- 在 HTML 中直接使用 `/n`，並無法換行，因 HTML 無法識別 `\n`，要讓其可以換行有下列方式
- ## Resolve
	- ### HTML
		- 使用 `<pre></pre>` 標籤
	- ### CSS
		- 設置 `white-space: pre-line` or `white-space: pre`
	- ### Javascript
		- 將 `\n` replace 成 `<br/>`
		- 使用 `innerHTML` 方法