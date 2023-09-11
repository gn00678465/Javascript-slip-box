category:: Note
type:: #Typescript, #Note
alias:: TS - string & {}

- > The type `string & {}` is conceptually the same as`string`, since the empty type `{}` matches any `non-null` and `non-undefined` type.
- **允許 string 型別並可提供預設的字串**
- ## Example
	- ```ts
	  type Colors = "blue" | "green" | "red" | string & {};
	  
	  getColor("red"); // okay
	  getColor("mauve"); // okay
	  getColor(""); // okay
	  getColor(123); // error
	  ```
- ## Reference
	- [Literal String Union Autocomplete   #29729](https://github.com/microsoft/TypeScript/issues/29729)
	- [TypeScript union of string and string literals](https://stackoverflow.com/questions/61047551/typescript-union-of-string-and-string-literals)