category:: Programing
type:: #Typescript
alias:: Typescript - keyof

- > 取出 **Object Types** 的 **key** 並組成一個新的 Type
  > 只可以使用於 Typescript 的 **Object Types**
- ```typescript
  // Object Types
  type Point = { x: number; y: number };
  type P = keyof Point; // x | y
  ```
- ## 搭配 `&` 使用
	- > Typescript 裡 **Object Types** 的 key 可能為 `string`、`number` 或 `symbol`
	- 搭配交集（`&`）的使用，如 `& string`，可讓 Typescript 明確知道要取出的型別為 string 的 key
- ## Reference
	- [Keyof Type Operator](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html)