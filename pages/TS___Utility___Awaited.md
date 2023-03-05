category:: Programing
type:: Typescript, Utility
alias:: Awaited
version:: 4.5+

- ## `Awaited<Type>`
	- 類似於 ES7 的 `async`, `await` 的方式,或是 `Promise.then()`, 也可以遞迴處理巢狀的 `Promise`;
	- ```typescript
	  type PromiseData = Promise<string>;
	  
	  type AwaitData = Awaited<PromiseData>; // string;
	  
	  type NestedPromiseData = Promise<Promise<string>>;
	  
	  type AwaitNestedData = Awaited<NestedPromiseData> // string;
	  ```
### 實作
	- 需先判斷是否為 `undefined 或 null`
	- 再判斷是否為 `Promise` 物件 or 是否為 nested `Promise` 物件
	- ```typescript
	  type MyAwaited<T> = T extends undefined | null
	    ? T
	    : T extends Record<any, any> & {
	        then(onfulfilled: infer F, ...args: infer _): any;
	      }
	    ? F extends (val: infer V) => any
	      ? Awaited<V>
	      : never
	    : T;
	  
	  ```