category:: Programing
type:: Javascript, Window
alias:: window.matchMedia

- ## Syntax
	- ```javascript
	  window.matchMedia(mediaQueryString)
	  ```
	- **parameter**
		- `mediaQueryString: string`:  用於 media query 的字串。ex: CSS的 `@media`
	- **return**
		- [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
- ## Example
	- ```css
	  @media (max-width: 768px) {
	    div {
	      background-color: red;
	    }
	  }
	  ```
	- ```javascript
	  const mql = window.matchMedia("(max-width: 768px)");
	  ```
- ## Reference
	- [MDN Window: matchMedia() method](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)