category:: Programing
type:: #Typescript
alias:: Overloads

- ## Overloads
- > Function Overloads 可擴充一個函式可以被執行的形式。
  > 不同的參數或 returnType 可以疊加在同一個 function 上。
  TypeScript 會優先從最前面的函式定義開始匹配，所以多個函式定義如果有包含關係，需要優先把精確的定義寫在前面。
- Function Overload 包含兩個部分
	- **overload signatures**: 定義型別， 通常會定義2種或以上。
	- **function implementation**: 執行 function 的，型別必須滿足所有的 `overload signatures`。
- ### 基本使用
	- ```typescript
	  // overload signatures
	  function add(a:number, b:number): number;
	  function add(a:string, b:string): string;
	  function add(a:string, b:number): string;
	  function add(a:number, b:string): string;
	  
	  // function implementation
	  function add(a:number | string, b:number | string): string | number {
	    if (typeof a === 'number' && typeof b === 'number') return a + b;
	    if (typeof a === 'string' && typeof b === 'string') return a + b;
	    if (typeof a === 'number' && typeof b === 'string') return a.toString() + b;
	    return a + b.toString();
	  }
	  
	  add(1,1); //2
	  add('a', 'b'); // ab
	  add(1, 'a'); // 1a
	  add('a', 1); // a1
	  ```
- ## 注意事項
	- Ordering: 順序必須由嚴謹到不嚴謹
	-
- ## Reference
	- [Overloads and Callbacks](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html#overloads-and-callbacks)