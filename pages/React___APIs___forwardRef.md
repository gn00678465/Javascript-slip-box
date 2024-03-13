id:: 64a39106-3ebd-4a4c-822b-e6d06639c8ea
category:: Programming
type:: #React, #API
alias:: forwardRef

- > lets your component expose a DOM node to parent component with a [ref.](https://react.dev/learn/manipulating-the-dom-with-refs)
  > 讓父元件可以存取子元件的 **DOM**
- ## Syntax
	- ```ts
	  const render: ForwardRefRenderFunction<RefType, PropsType> = (props, ref) => {
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
	- forwardRef 包裹你的 component
	  logseq.order-list-type:: number
	- component 傳入 props 和 ref
	  logseq.order-list-type:: number
	- 在父元件透過 ref 來存取其 DOM
	  logseq.order-list-type:: number
	- ```ts
	  // children
	  const ForwardRefInput = forwardRef<HTMLInputElement, {}>((props, ref) => {
	    return <input ref={ref} type="search" />;
	  });
	  ForwardRefInput.displayName = ForwardRefInput;
	  
	  // parent
	  function App() {
	    const InputRef = useRef<HTMLInputElement | null>(null);
	  
	    return <ForwardRefInput ref={InputRef} />;
	  }
	  ```
- ## Referece
	- [forwardRef](https://react.dev/reference/react/forwardRef)