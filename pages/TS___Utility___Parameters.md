category:: Programing
type:: Typescript, Utility, Function
alias:: Parameters
version:: 3.1+

- ## `Parameters<Type>`
	- > 提取出 function 內所有的 parameter 的型別,並回傳一個 Array 包含提取的型別
	- ```typescript
	  function sum(a: number, b: number): number {
	    return a + b;
	  }
	  
	  type SumParams = Parameters<typeof sum>; // [a: number, b: number];
	  ```
- ### 實作
	- 運用 `infer` 進行推斷
	- ```typescript
	  type MyParameters<T extends (...args: any[]) => any> = T extends (...args: infer P) => any
	  	? P
	  	: never;
	  ```