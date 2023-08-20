category:: Programing
type:: #Javascript
alias:: String.prototype.padEnd

- > 目前仍是一個**實驗中的功能**
  以重複的方式在字串的後綴補充字元，直到目標字串到達指定長度
- ## Syntax
	- ```js
	  str.padEnd(targetLength);
	  str.padEnd(targetLength [, padString]);
	  ```
	- **Parameters**
		- **`targetLength`**
			- Type: `number`
			- 字串目標長度
		- **`padString`** <span class="badge">Optional</span>
			- Type: `string`
			- 預設為 `" "` (U+0020)
	- **Return**
		- Type: `string`
		- 填充至指定長度後的新字串
- ## Function
	- ```ts
	  function padEnd(str: string, targetLength: number, padString?: string) {
	    if (typeof str !== 'string') {
	      throw TypeError(`${str} must be string type`);
	    }
	  
	    let targetLen = targetLength = Math.floor(targetLength) || 0;
	    if (str.length >= targetLen) return String(str);
	  
	    let padStr = String(typeof padString !== 'undefined' ? padString : ' ');
	    targetLen = targetLen - str.length;
	  
	    if (targetLen > padStr.length) {
	      padStr += padStr.repeat(targetLen / padStr.length);
	    }
	    return String(str) + padStr.slice(0, targetLen);
	  }
	  ```
- ## Polyfill
	- ```js
	  String.prototype.padEnd = String.prototype.padEnd
	    ? String.prototype.padEnd
	    : function(targetLength, padString) {
	  		targetLength = Math.floor(targetLength) || 0;
	    		if (targetLength < this.length) return String(this);
	    		const padStr = padString ? String(padString) : " ";
	  
	          let pad = "";
	          let len = targetLength - this.length;
	          let i = 0;
	  
	          while (pad.length < len) {
	            if(!padStr[i]) {
	              i = 0;
	            }
	            pad += padStr[i];
	            i++;
	          }
	    		return String(this).slice(0) + pad;
	  	}
	  ```
- ## Reference
	- [MDN - padEnd](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd)