category:: Programing
type:: Typescript, Utility
alias:: Pick
version:: 2.1+

- ## `Pick<Type, keys>`
	- > 提取出指定的屬性，並返回一個新的 Type
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