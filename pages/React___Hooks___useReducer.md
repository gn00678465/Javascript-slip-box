category:: Programming
type:: #[[React]], #Hooks
alias:: useReducer

- > 適合處理較複雜的 state，可以將狀態的改變統一放在 reducer 去做管理
- ```typescript
  const [state, dispatch] = useReducer(reducer, initialState[, initStateFn]);
  ```
- **Types**
	- ```typescript
	  export interface InitialState {
	    // types
	  }
	  
	  export type Actions =
	    | { type: 'action1'; payload: any }
	    | { type: 'action2'; payload: any };
	  
	  function reducer(state: InitialState, actions: Actions) {
	    /** ... */
	  }
	  
	  const [state, dispatch] = useReducer(reducer, initialState);
	  ```
- **Parameter**
  collapsed:: true
	- `reducer`: 為一個 callback function，內部定義了操作 state 的方法，透過 dispatch 呼叫
		- ```typescript
		  function reducer(state, action) {
		    switch (action.type) {
		      case :
		      return { ...state, /* do something */ }
		    }
		    return state;
		  }
		  ```
		- **Parameter**
			- `state`: 當前的 state
			- `action`: 透過 dispatch 呼叫所傳入的參數
		- **Return**
			- **必須**回傳 `state` or 修改後的 `state`
	- `initialState`: 初始化的 state
	- `initStateFn`: 初始化 state 的函式，非必要
- **Return**
  collapsed:: true
	- 為一個陣列
	- `state`: 當前的 state
	- `dispatch`: 呼叫 `reducer` 的方法，可帶入一個參數
		- ```typescript
		  function fn() {
		    dispatch({
		      type: 'TYPE',
		      payload: 
		    })
		  }
		  ```
- ## Reference
	- [useReducer](https://zh-hant.reactjs.org/docs/hooks-reference.html#usereducer)