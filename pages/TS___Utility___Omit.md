category:: Programing
type:: #Typescript, #Utility
alias:: Omit
version:: 3.5+

- ## `Omit<Type, keys>`
	- > Constructs a type by picking all properties from `Type` and then removing `Keys` (string literal or union of string literals).
	  >> 排除指定的屬性，並返回一個新的 Type
	  與 [[Pick]] 互為相反
	- ```typescript
	  type Coord = {
	    x: number;
	    y: number;
	  };
	  
	  type CoordY = Omit<Coord, 'x'>;
	  
	  /*
	  {
	    y: number
	  }
	  */
	  ```
- ### 實作
	- #### 方法 1
		- Mapped Types
		- ```typescript
		  type MyOmit<T> = {
		    [P in keyof T]: T[P];
		  }
		  ```
		- 透過 `Exclude` 將不需要的 keys 排除
		- ```typescript
		  type MyOmit<T, K> = {
		    [P in Exclude<keyof T, K>]: T[P];
		  }
		  ```
	- #### 方法 2 - 使用 `Pick` 改寫
		- ```typescript
		  type MyOmit<T, K> = Pick<T, Exclude<keyof T, K>>
		  ```
		- 確保 `K` 一定是可以被放入 Mapped Types 中使用, 對`K`  多加上了 `extends keyof any` 的泛型限制
		- ```typescript
		  type MyOmit<T, K extends keyof any> = Pick<T, Exclude<keyof T, K>>
		  ```
- ## Reference
	- [[Day18]   TS：理解 Omit 的實作](https://pjchender.dev/ironman-2021/ironman-2021-day18/)