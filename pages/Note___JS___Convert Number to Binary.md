category:: Note
type:: #Javascript, #Note
alias:: JS - Convert Number to Binary

- > 將數字轉為 Binary 的不同方式
- ### Approach 1: Using `toString()` method
	- ```ts
	  function decimalToBinary(n: number): string {
	    return n.toString(2);
	  }
	  
	  const number = 25;
	  console.log(decimalToBinary(25)); // "11001"
	  ```
- ### Approach 2: Using unsigned `right shift operator (>>>)`
	- ```ts
	  function decimalToBinary(n: number): string {
	    return (n >>> 0).toString(2);
	  }
	  
	  const number = 25;
	  console.log(decimalToBinary(25)); // "11001"
	  ```
- ### Approach 2: Using Loop and String Concatenation
	- Initialize an empty string say binary.
	  logseq.order-list-type:: number
	- Run a while loop until the decimal number i.e. **n** is greater than 0.
	  logseq.order-list-type:: number
	- Inside the loop find the remainder of **n** by 2 and concatenate it with a binary string.
	  logseq.order-list-type:: number
	- Update the number **n** after dividing it by 2 in each iteration and use the floor function for it.
	  logseq.order-list-type:: number
	- ```ts
	  function decimalToBinary(n: number): string {
	    let binary = '';
	    
	    while (n > 0) {
	      binary = (n % 2) + binary;
	      n = Math.floor(n / 2);
	    }
	    
	    return binary;
	  }
	  
	  const number = 25;
	  console.log(decimalToBinary(25)); // "11001"
	  ```
- ## Reference
	- [# JavaScript Program to Convert a Number to Binary](https://www.geeksforgeeks.org/javascript-program-to-convert-a-number-to-binary/)