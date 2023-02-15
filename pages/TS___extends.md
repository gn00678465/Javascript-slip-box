category:: Programing
type:: Typescript
alias:: extends

- ## extends
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