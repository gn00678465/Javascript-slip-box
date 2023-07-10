category:: Programing
type:: #Typescript
alias:: Generics(泛型)

- > 宣告一 **`Function`**、**`Interface`**、**`class`**，不預先指定具體的型別，而在使用時再給予實際的型別。
  宣告時給一不定型態，以 `<>` 包覆。
- ## Function
	- ```typescript
	  function createArray<T>(len: number, value: T):T[] {
	    return [...new Array(len)].fill(value)
	  };
	  const fn = <T>(param: T) => {/** do something */}
	  
	  createArray<string>(5, 'a'); // ["a", "a", "a", "a", "a"]: string[]
	  ```
- ## 多個型別引數
	- ```typescript
	  function swap<T, K>(arr: [T, K]): [K, T] {
	    const [arg0, arg1] = arr;
	    return [arg1, arg0]
	  };
	  
	  swap<number, string>([1, 'a']); // ["a", 1]: [string, number]
	  ```
- ## 型別約束
	- 當使用泛型變數時，**無法事先得知**型別，不能隨意操作屬性或方法：
	- ```typescript
	  function loggingIdentity<T>(arg: T): T {
	      console.log(arg.length);
	      return arg;
	  }
	  // 泛型 T 不一定包含屬性 length
	  // Property 'length' does not exist on type 'T'.
	  ```
	- 可以使用 extends ((63f9f301-c0d3-4161-9399-80ecda1f0a22)) 針對泛型進行**約束**，只允許傳入包含某特定屬性或方法的變數。
	- ```typescript
	  interface L {
	    length: number
	  }
	  
	  function loggingIdentity<T extends L>(arg: T): T {
	      console.log(arg.length);
	      return arg;
	  }
	  ```
- ## Interface
	- ```typescript
	  interface Animal<T> {
	    name: string,
	    age: T
	  };
	  
	  function cat<T>(age: T): Animal<T> {
	    return {
	      name: 'cat',
	      age
	    }
	  };
	  
	  cat(5);
	  ```
- ## class
	- ```typescript
	  class Store<State> {
	    private state: State;
	    
	    constructor(initState: State) {
	      this.state = initState;
	    }
	    /**
	    	other methods
	    */
	  }
	  ```
- ## Optional
	- > 當宣告的 Generics 使用預設值設為 `void`, 此 Generics 可不設定型別
	- ```typescript
	  type BaseFunctionType<T1, T2> = (a:T1, b:T2) => void;
	  
	  type FunctionType<T = void> = BaseFunctionType<{name: string}, T>;
	  
	  const someFunction:FunctionType = (a) => {
	  	/* do something */
	  }
	  
	  someFunction({ name: "name" })
	  
	  ```
- ## Reference
	- [泛型 Generics](https://willh.gitbook.io/typescript-tutorial/advanced/generics)