category:: Programing
type:: #Typescript
alias:: Non-null assertion operator
version:: 2.0+

- > A new `!` post-fix expression operator may be used to assert that its operand is non-null and non-undefined in contexts where the type checker is unable to conclude that fact.
  >> 告知編譯器某值不會為 null 或 undefined，允許編譯器進行型別推斷並移除 null 或 undefined 的可能性。
- ```typescript
  interface Entity {
    name: string;
  }
  
  function processEntity(e?: Entity) {
    let n = e.name; // error
    let s = e!.name; // Assert that e is non-null and access name
  }
  ```
- ## Reference
	- [Non-null assertion operator](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html#non-null-assertion-operator)