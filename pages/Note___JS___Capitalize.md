category:: Note
type:: #Note, #Javascript
alias:: JS - String Capitalize

- > 轉換第一個字母為大寫字母
- **Function**
	- ```ts
	  function capitalize(str: string) {
	    return str.charAt(0).toUpperCase() + str.slice(1);
	  }
	  ```
- **Prototype**
	- ```js
	  String.prototype.capitalize = function() {
	    return this.charAt(0).toUpperCase() + this.slice(1);
	  }
	  ```