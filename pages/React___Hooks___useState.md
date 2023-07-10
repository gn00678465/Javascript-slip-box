category:: Programing
type:: React, Hooks
alias:: useState

- > 當 state 更新時，會觸發 re-render
- ## Syntax
	- ```ts
	  const [state, setState] = useState<Type>(initialValue);
	  ```
	- **Parameters**:
		- `initialValue: Type | (() => Type)`: 可帶入基本型別
	- **Return**:
		- `[Type, Dispatch<SetStateAction<Type>>]`
		- 使用解構方式取得的第 1 項，為當下的 state，且為 **read-only** 不可直接針對 state 做操作
		- 第 2 項，為一個方法，主要作為修改 state 之用
			- 可直接帶入要修改的 state
- ## 進階用法
	- ### Functional updates
		- > 新的資料需使用當前的原資料經過某些計算後產生, 可以在 `setState` 中帶入一個 callback function , previousState 作為參數傳入此 function 內計算
		- ```tsx
		  const [state, setState] = useState({});
		  setState((prevState) => {
		    // Object.assign would also work
		    return {...prevState, ...updatedValues};
		  });
		  ```
	- ### Lazy initial state
		- > 如果在 `useState` 內的 `initialValue` 是需要經過函式處理情況下, `initialValue` 改傳入 function, 此 function 只會在第一次 initialize 時執行, 之後的 re-render 都不會執行
		- ```tsx
		  const [state, setState] = useState(() => {
		    const initialState = someExpensiveComputation(props);
		    return initialState;
		  });
		  ```