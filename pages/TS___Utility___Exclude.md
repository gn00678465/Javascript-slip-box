category:: Programing
type:: Typescript, Utility, Union
alias:: Exclude
version:: 2.8+

- ## `Exclude<UnionType, ExcludeMembers>`
	- > 與 [[Extract]] 互為相反, 剔除不要的型別
	- ```typescript
	  type ExcludeStr = Exclude<number | string | (() => void), string>;
	  // type ExcludeStr = number | () => void
	  type StrID = Exclude<number | string, number>;
	  // type StrID = string
	  ```
- ### 實作
	- ```typescript
	  type MyExclude<U, Members> = Members extends U ? never : T;
	  ```