category:: Programing
type:: react,hooks
alias:: useRef

- ```typescript
  const refContainer = useRef(initialValue);
  // { current: initialValue }
  ```
- > 應用 call by reference
- `useRef` 回傳一個 mutable 的 ref object，`.current` 屬性被初始為傳入的參數（`initialValue`）
	- **更新 current 值並不會觸發 re-render**
	- 可以取得 Previous 的值
- 取得 DOM 的 reference，並直接操作 DOM
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