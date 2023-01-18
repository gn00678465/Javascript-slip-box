- > 取出 **object type** 的 **key** 並組成一個新的 Type
- ```typescript
  // object type
  type Point = { x: number; y: number };
  type P = keyof Point; // x | y
  ```
## 搭配 & string 使用
	- > **object type**
- ## Reference
	- [Keyof Type Operator](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html)