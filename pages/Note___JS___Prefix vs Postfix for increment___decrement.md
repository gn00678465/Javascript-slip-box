category:: Note
type:: #Javascript, #Note
alias:: JS - Prefix vs Postfix for increment/decrement

- ## Prefix
	- |**Operator**|**Meaning**|
	  |--|--|
	  |`++var`|`var = var + 1`|
	  |`--var`|`var = var - 1`|
	- ```js
	  let count = 2;
	  console.log(++count); // 3
	  ```
		- **先**進行運算，**再**回傳運算後的結果
	- ```js
	  let a = 0;
	  let b = ++a;
	  
	  console.log(a === b); // true
	  ```
- ## Postfix
	- |**Operator**|**Meaning**|
	  |--|--|
	  |`var++`|`var = var + 1`|
	  |`var--`|`var = var - 1`|
	- ```js
	  let count = 2;
	  console.log(count++); // 2
	  ```
		- **先**回傳**原本**未處理的值，**再**處理後續的運算
	- ```js
	  let a = 0;
	  let b = a--;
	  
	  console.log(a === b); // false
	  ```
- ## Reference
	- [Prefix vs Postfix for increment/decrement](https://www.linkedin.com/pulse/prefix-vs-postfix-incrementdecrement-haresh-kotkar)