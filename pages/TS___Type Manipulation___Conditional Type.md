category:: Programing
type:: Typescript
alias:: Conditional Type

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
	- > T[number] 使用的是 indexed 的方式來存取某陣列型別內元素的型別