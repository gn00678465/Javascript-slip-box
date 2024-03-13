category:: Programming
type:: #React, #Hooks
alias:: useImperativeHandle

- > 讓父元件得到子元件某些自定義方法
  此 **hook** 應與 **[[forwardRef]]** 一起使用
- ## Syntax
	- ```ts
	  useImperativeHandle(
	    ref,
	    createHandle: () => any,
	    dependencies?: DependencyList
	  ): undefined
	  ```
	- **Parameters**
		- `ref`: [[forwardRef]] render function 中的第二個參數
		- `createHandle`: 為一個 function, 不須帶入參數, 回傳要暴露給父元件的方法或屬性
		- `dependencies`:
	- **Returns**: `undefined`
- ## Usage
	- ```ts
	  // children
	  const ForwardRefInput = forwardRef((prop, ref) => {
	    const inputRef = useRef();
	    useImperativeHandle(ref, () => {
	      return {
	        focus: () => {
	            inputRef.current.focus();
	        }
	      }
	    }, []);
	    
	    return <input ref={inputRef} type="search" />;
	  });
	  
	  // parent
	  function App() {
	    const InputRef = useRef<HTMLInputElement | null>(null);
	    
	    const clickHandler = () => {
	      console.log(parentInputRef.current);
	      /*
	        {
	          focus: () => { inputRef.current.focus() }
	        }
	      */
	    }
	  
	    return <ForwardRefInput ref={InputRef} />;
	  }
	  ```
- ## Referece
	- [useImperativeHandle](https://react.dev/reference/react/useImperativeHandle)
	- [使用 useImperativeHandle 來跟子元件互動](https://z3388638.medium.com/react-hooks-%E4%BD%BF%E7%94%A8-useimperativehandle-%E4%BE%86%E8%B7%9F%E5%AD%90%E5%85%83%E4%BB%B6%E4%BA%92%E5%8B%95-2b543bec3e8a)