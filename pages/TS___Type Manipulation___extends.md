category:: Programing
type:: Typescript, Conditional Type
alias:: extends

- ## Narrow 收窄
	- ```ts
	  type NewType = SomeType extends OtherType ? TrueType : FalseType;
	  ```
	- > 當 **SomeType** 滿足 **OtherType**; **NewType** 為 **TrueType**, 否則為 **FalseType**
	  🔔: `T extends K`, T 為 K 的子集合 (subset), T 能滿足 K
	- ### Conditional Type Constraints
		- Flatten
		- ```ts
		  type Flatten<T> = T extends any[] ? T[number] : T;
		  type A = Flatten<string[]>;  // A 為 string type
		  type B = Flatten<number>;  // B 為 number type
		  ```
		- > `T[number]` 是使用 indexed 的方式來存取某陣列型別內元素的型別
		- Wrap
		- ```ts
		  type Wrap<T> = T extends { length: number } ? [T] : T;
		  type A = Wrap<string>;  // A 為 string[] type
		  ```
- ## 擴充
	- > 繼承型別做**擴充**使用，只能使用於 **interface**
	- ```typescript
	  interface A {
	    a: string
	  }	
	  
	  interface B {
	    b: number
	  }
	  
	  interface C extends A, B {
	    c: boolean
	  }
	  
	  /*
	  {
	    a: string;
	    b: number;
	    cL boolean;
	  }
	  */	
	  ```
- ## Reference
	- [Conditional Type](https://www.typescriptlang.org/docs/handbook/2/conditional-types.html#conditional-type-constraints)
	- [[TS] Type Manipulation](https://pjchender.dev/typescript/ts-type-manipulation/)