category:: Note
type:: #CSS
alias:: CSS - 在 Flexbox 中顯示省略號

- > 在 Flexbox 中無法正常顯示省略號
- ## 解法
	- ```html
	  <div class="content">
	    <div class="text-ellipsis"></div>
	  </div>
	  ```
	- ### `overflow: hidden`
		- 在已設定省略號的父元素加上 `overflow: hidden`
	- ### `min-width: 0`
		- 在已設定省略號的父元素加上 `min-width: 0`
- ## Reference
	- [Flexbox and Truncated Text](https://css-tricks.com/flexbox-truncated-text/)