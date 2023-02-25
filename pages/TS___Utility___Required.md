category:: Programing
type:: Typescript, Utility
alias:: Required
version:: 2.1+

- ## `Required<Type>`
	- > 複製 `Type` 的結構並將所有屬性設定為必填，與 [[Partial]] 互為相反
	- ```typescript
	  type Props = {
	    a?: number;
	    b?: string;
	  };
	  
	  type RequiredProps = Required<Props>;
	  ```
- ### 實作
	- > 使用 `-?` 將 optional 移除
	- ```typescript
	  type MyRequired<T> = {
	    [P in keyof T]-?: T[P]
	  };
	  ```