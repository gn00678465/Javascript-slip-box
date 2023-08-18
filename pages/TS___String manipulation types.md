category:: Programing
type:: #Typescript
alias:: String manipulation types
version:: 4.1+

- ## `Uppercase<StringType>`
	- > 轉換所有字母至大寫字母
	- ```ts
	  type Greeting = "Hello, world";
	  type UppercaseGreeting = Uppercase<Greeting>;
	  	// HELLO, WORLD
	  ```
- ## `Lowercase<StringType>`
	- > 轉換所有字母至小寫字母
	- ```ts
	  type Greeting = "Hello, world";
	  type LowercaseGreeting = Lowercase<Greeting>;
	  	// "hello world"
	  ```
- ## `Capitalize<StringType>`
	- > 轉換第一個字母至大寫字母
	- ```ts
	  type LowercaseGreeting = "hello, world";
	  type CapitalizeGreeting = Capitalize<LowercaseGreeting>;
	  	// "Hello, world"
	  ```
- ## `Uncapitalize<StringType>`
	- > 轉換第一個字母至小寫字母
	- ```ts
	  type UppercaseGreeting = "HELLO, WORLD";
	  type UncapitalizeGreeting = Upcapitalize<UppercaseGreeting>;
	  	// "hELLO, WORLD"
	  ```