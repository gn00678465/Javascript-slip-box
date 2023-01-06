category:: Programing
type:: Typescript,Utility
alias:: Partial

- > 複製 `Type` 的結構並將內部的 properties 設為 optional
- ## Partial<Type>
	- ```typescript
	  interface Todo {
	    title: string;
	    description: string;
	  }
	  type OptionalTodoField = Partial<Todo>;
	  /**
	  {
	    title?: string;
	    description?: string;
	  }
	  */
	  ```
- ## Reference
	- [Utility Types - Partial](https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype)
	- [到底是什麼意思？Typescript Partial<Type>](https://ithelp.ithome.com.tw/articles/10273198?sc=rss.iron)