category:: Programming
type:: #Typescript, #Utility
alias:: ReturnType
version:: 2.8+

- ## `ReturnType<Type>`
	- > 提取出 function 回傳值的型別,並回傳一個新的型別
	- ```typescript
	  function sum(a: number, b: number): number {
	    return a + b;
	  }
	  
	  type SumReturnType = ReturnType<typeof sum>; // number
	  ```
- ### 實作
	- 運用 `infer` 進行推斷
	- ```typescript
	  type MyReturnType<T extends (...args: any[]) => any> = T extends (...args: any) => infer P
	  	? P
	  	: never;
	  ```