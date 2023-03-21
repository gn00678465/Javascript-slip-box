category:: Programing
type:: Typescript, Utility
alias:: Pick
version:: 2.1+

- ## `Pick<Type, keys>`
	- > Constructs a type by picking the set of properties `Keys` (string literal or union of string literals) from `Type`.
	  >> 提取出指定的屬性，並返回一個新的 Type
	  與 [[Omit]] 互為相反
	- ```typescript
	  type Coord = {
	    x: number;
	    y: number;
	  };
	  
	  type CoordX = Pick<Coord, 'x'>;
	  
	  /*
	  {
	    x: number
	  }
	  */
	  ```
### 實作
	- ```typescript
	  type MyPick<T, K extends keyof T> = {
	    [P in K]: T[P];
	  }
	  ```