category:: Programing
type:: React, APIs
alias:: forwardRef
id:: 64a39106-3ebd-4a4c-822b-e6d06639c8ea

- > lets your component expose a DOM node to parent component with a [ref.](https://react.dev/learn/manipulating-the-dom-with-refs)
  > 讓父元件可以存取子元件的 **DOM**
- ## Syntax
	- ```ts
	  const render = (props: unknown, ref: unknown) => {
	    return /* component */
	  }
	  
	  const SomeComponent = forwardRef<RefType, PropsType>(render)
	  ```
	- **Parameters**
		- `render`: Render component 的函式, 呼叫時會帶入兩個參數 `props`、`ref`
			- `props`: 從父元件帶入的 `props`
			- `ref`: 從父元件帶入的 `ref`
	- **Return**
- ## Usage
	- 1. forwardRef包裹你的component
	  2. component傳入props和ref
	  3. 在父元件透過ref來存取其DOM
	- ```ts
	  // children
	  const ForwardRefInput = forwardRef<HTMLInputElement, {}>((props, ref) => {
	    return <input ref={ref} type="search" />;
	  })
	  
	  // parent
	  function App() {
	    const InputRef = useRef<HTMLInputElement | null>(null);
	  
	    return <ForwardRefInput ref={InputRef} />;
	  }
	  ```
- ## Referece
	- [forwardRef](https://react.dev/reference/react/forwardRef)