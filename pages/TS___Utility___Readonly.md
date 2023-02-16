category:: Programing
type:: Typescript, Utility
alias:: Readonly
version:: 2.1+

- ## `Readonly<Type>`
	- > 複製 `Type` 的結構並將所有屬性設定為 Readonly，即不能修改屬性的值
	- ```typescript
	  type Props = {
	    a: number;
	    b: string;
	  };
	  
	  type ReadonlyProps = Readonly<Props>;
	  ```
- ### 實作
	- ```typescript
	  type MyReadonly<T> = {
	    readonly [P in keyof T]: T[P]
	  }
	  ```