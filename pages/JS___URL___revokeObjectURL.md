category:: Programming
type:: #Javascript
alias:: URL.revokeObjectURL

- > 釋放由 [[URL.createObjectURL]] 所產生的 object URL
- ## Syntax
	- ```ts
	  URL.revokeObjectURL(objectURL)
	  ```
	- **Parameters**
		- **`objectURL`**
			- Type: `string`
			- 由 [[URL.createObjectURL]] 所產生
	- **Return**
		- `undefined`
- ## Reference
	- [MDN - revokeObjectURL](https://developer.mozilla.org/en-US/docs/Web/API/URL/revokeObjectURL_static)
	- [Do I always need to call URL.revokeObjectURL() explicitly?](https://stackoverflow.com/questions/49209756/do-i-always-need-to-call-url-revokeobjecturl-explicitly)