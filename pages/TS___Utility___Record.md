category:: Programming
type:: #Typescript, #Utility
alias:: Record
version:: 2.1+

- ## `Record<Keys, Type>`
	- > Constructs an object type whose property keys are `Keys` and whose property values are `Type`. 
	  This utility can be used to map the properties of a type to another type.
	  >> 將一個物件結構的型別內所有的屬性以及值映射到另一個型別，並返回新的型別
	- ```typescript
	  type ApiKey = 'id' | 'createAt';
	  type ApiDateRecord = Record<ApiKey, string>;
	  /*
	  {
	  	id: string;
	      createAt: string;
	  }
	  */
	  ```
- ### 實作
	- ```typescript
	  type MyRecord<T extends keyof any, K> = {
	    [P in keyof T]: K;
	  };
	  
	  ```
- ## Reference
	- [Utility Types - Record](https://www.typescriptlang.org/docs/handbook/utility-types.html#recordkeys-type)
	- [[Day17] TS：理解 Pick、Record 的實作]([https://pjchender.dev/ironman-2021/ironman-2021-day17/](https://pjchender.dev/ironman-2021/ironman-2021-day17/#record))