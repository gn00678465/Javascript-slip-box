category:: Programming
type:: #Typescript, #Utility
alias:: Extract
version:: 2.8+

- ## `Extract<Type, Union>`
	- > 提取要的型別
	- ```typescript
	  type ExtractFun = Extract<number | string | (() => void), Function>;
	  // type ExtractFun = () => void
	  type ExtractArr = Extract<number[] | string[] | boolean, any[]>;
	  // type ExtractFun = () => number[] | string[]
	  ```
- ### 實作
	- ```typescript
	  type MyExtract<T, U> = T extends U ? T : never;
	  ```