category:: Programming
type:: #Typescript, #Utility
alias:: NonNullable
version:: 2.8+

- ## `NonNullable<Type>`
	- > 將 `null` & `undefined` 從 Type 中剔除
	- ```typescript
	  type NullableID = string | number | undefined | null;
	  type ID = NonNullable<NullableID>;
	  // type ID = string | number
	  ```
- ### 實作
	- ```typescript
	  type MyNonNullable<T> = T & {};
	  
	  type MyNonNullable2<T> = Exclude<T, null | undefined>;
	  ```