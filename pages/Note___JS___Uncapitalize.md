category:: Note
type:: #Note, #Javascript
alias:: JS - String Uncapitalize

- > 轉換第一個字母為小寫字母
- **Function**
	- ```ts
	  function uncapitalize(str: string) {
	    return str.charAt(0).toLowerCase() + str.slice(1);
	  }
	  ```
- **Prototype**
	- ```js
	  String.prototype.uncapitalize = function() {
	    return this.charAt(0).toLowerCase() + this.slice(1);
	  }
	  ```