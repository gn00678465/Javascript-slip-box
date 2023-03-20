category:: Programing
type:: Typescript
alias:: Infer

- ## Infer
- ### Within Conditional Types
	- > 用於推斷某型別的內容物的型別
	- `extends ... infer ? ... : ...`
	- ```typescript
	  type Flatten<T> = T extends Array<infer P> ? P : T;
	  ```
### 實作
	- 1. 先思考 **`extends` 要放置的位置**，以及要做的條件判斷為何?
	  2. 在思考 **`infer` 放置的位置**，要推斷的是哪個部分?
	  3. 思考條件判斷，要 return 的型別為何?
	  4. 思考還有沒有其他的可能性需要判斷，是否需要一個以上的條件判斷?
	- ```typescript
	  type MyReturnType<T extends (...args: any[]) => any> = T extends (...args: any[]) => infer P
	    ? P
	    : never;
	  ```
- ### 內置型別
	- [[Parameters]]
	- [[ReturnType]]