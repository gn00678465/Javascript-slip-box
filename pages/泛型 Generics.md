- 宣告一 **`Function`**、**`Interface`**、**`class`**，不預先指定具體的型別，而在使用時再給予實際的型別。
- 可提升程式的變化性。
- 宣告時給一不定型態，以 `<>` 包覆。
- ## Function
	- ```typescript
	  function createArray<T>(len: number, value: T):T[] {
	    return [...new Array(len)].fill(value)
	  };
	  
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
	- 當使用泛型變數時，無法事先得知型別，不能隨意操作屬性或方法：
	- ```typescript
	  function loggingIdentity<T>(arg: T): T {
	      console.log(arg.length);
	      return arg;
	  }
	  // 泛型 T 不一定包含屬性 length
	  // Property 'length' does not exist on type 'T'.
	  ```
	- 可以針對泛型進行約束，只允許傳入包含某特定屬性或方法的變數。
	- ```typescript
	  function loggingIdentity<T>(arg: T): T {
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
- ## Reference
	- [泛型 Generics](https://willh.gitbook.io/typescript-tutorial/advanced/generics)