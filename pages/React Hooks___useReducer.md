category:: Programing
type:: react,Hooks
alias:: useReducer

- ```typescript
  const [state, dispatch] = useReducer(reducer, initialState[, initStateFn]);
  ```
- **Parameter**
	- `reducer`: 為一個 callback function，內部定義了操作 state 的方法，由 dispatch 呼叫
	- `initialState`: 初始化的 state
	- `initStateFn`: 初始化 state 的函式，非必要
- **Return**
	- 為一個陣列
	- `state`: 當前的 state
	- `dispatch`: 呼叫 `reducer`，