category:: Programming
type:: #Typescript
alias:: Discriminated Unions

- ## Benefits
	- Improved Type Safety: With discriminated unions, TypeScript can ensure that all possible variants of a type are accounted for, eliminating the risk of undefined or unexpected behavior at runtime.
	  logseq.order-list-type:: number
	- Enhanced Autocompletion: IDEs and code editors can leverage the discriminators to provide accurate autocompletion suggestions based on the specific variant being handled.
	  logseq.order-list-type:: number
	- Better Code Maintainability: Discriminated unions make code easier to read and understand by explicitly indicating the possible cases for a given type.
	  logseq.order-list-type:: number
	- Comprehensive Error Handling: TypeScript's static type checking can help us catch missing or mismatched discriminators, reducing the likelihood of introducing bugs.
	  logseq.order-list-type:: number
- ## Discriminated Union
- ```ts
  interface Successful {
    status: 'success';
    data: {
      id: string
    }
  }
  
  interface Failure {
    status: 'error';
    message: string;
  }
  
  type State = Successful | Failure;
  ```
- If use a type guard style check (`==`, `===`, `!=`, `!==`) or `switch` on the *discriminant property* TypeScript will realize that the object must be of the type that has that specific literal and do a type narrowing for you
- ```ts
  function andThen(state: State) {
    return new Promise((resolve, reject) => {
      if (state.status === 'success') {
        // This means you can safely access state.data
        // because it's the only type inside State
        // where status is "success"
        resolve(state.data);
      }
      if (state.status === 'error') {
        reject(new Error(state.message));
      }
    })
  }
  ```
- ## Reference
	- [Discriminated Union](https://basarat.gitbook.io/typescript/type-system/discriminated-unions)