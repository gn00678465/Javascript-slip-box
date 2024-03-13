category:: Programming
type:: #Typescript, #Utility
alias:: Partial

- ## `Partial<Type>`
	- > 複製 `Type` 的結構並將內部的 properties 設為 optional
	- ```typescript
	  interface Todo {
	    title: string;
	    description: string;
	  };
	  
	  type PartialToDo = Partial<Todo>;
	  ```
- ### 實作
	- ```typescript
	  type MyPartial<T> = {
	    [P in keyof T]?: T[P]
	  };
	  ```
- ## Reference
	- [Utility Types - Partial](https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype)
	- [到底是什麼意思？Typescript Partial<Type>](https://ithelp.ithome.com.tw/articles/10273198?sc=rss.iron)