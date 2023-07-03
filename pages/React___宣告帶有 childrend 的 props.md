category:: Note
type:: React, Typescript
alias:: React 宣告帶有 childrend 的 props

- ## ReactNode
	- ```ts
	  import { ReactNode } from 'react';
	  
	  type Props = {
	    children?: ReactNode;
	  }
	  
	  function Component({children}: Props): ReactNode {
	    /* ... */
	  }
	  ```
- ## React.FunctionComponent | React.FC
	- ```ts
	  type Props = {
	    children?: ReactNode;
	  }
	  
	  export const Component: React.FC<Props> = ({ children }) => {/* ... */}
	  ```