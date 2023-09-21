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
	- 回傳已**增加**或**減少**的值
- ## Postfix
	- |**Operator**|**Meaning**|
	  |--|--|
	  |`var++`|`var = var + 1`|
	  |`var--`|`var = var - 1`|
	- ```js
	  let count = 2;
	  console.log(count++); // 2
	  ```
	- 回傳**原本**未處理的值
-
- ## Reference
	- [Prefix vs Postfix for increment/decrement](https://www.linkedin.com/pulse/prefix-vs-postfix-incrementdecrement-haresh-kotkar)