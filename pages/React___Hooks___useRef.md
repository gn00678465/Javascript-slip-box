category:: Programming
type:: #[[React]], #Hooks
alias:: useRef

- > 應用 call by reference (傳參考特性)
- ## Syntax
	- ```ts
	  // Generic
	  const ref  = useRef<T>(initialValue);
	  const ref: RefObject<T> = useRef(initialValue);
	  ```
		- **Parameters**:
			- `initialValue`: 初始值
		- **Return**:
			- ```ts
			  interface RefObject<T> {
			    readonly current: T | null;
			  }
			  
			  const ref = { current: }
			  ```
- `useRef` 回傳一個 mutable 的 ref object，`.current` 屬性被初始為傳入的參數（`initialValue`）
	- **更新 current 值並不會觸發 re-render**
	- 可以取得 Previous 的值
- 可取得 DOM 的 reference，並直接操作 DOM
	- ```typescript
	  const App = () => {
	    const inputRef = useRef(null);
	    function onChange() {
	      console.log(inputRef.current.value);
	    }
	    return (
	    	<input type="text" ref={buttonRef} onChange={onChange}></input>
	    )
	  }
	  ```
- ## Reference
	- [[React Hook 筆記] useRef](https://medium.com/hannah-lin/react-hook-%E7%AD%86%E8%A8%98-useref-c628cbf0d7fb)