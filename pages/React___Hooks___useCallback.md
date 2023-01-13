category:: Programing
type:: React, Hooks
alias:: useCallback

- > 透過它對一個 function 重新執行的時機做出控制。
- ```typescript
  const memoizedCallback = useCallback(() => {
  	// do something
  }, [effect])
  ```
- **Parameters**
	- `callback function` 作為副作用更新後要執行的函式
	- `[effect]` 監聽副作用的變化
		- 未帶入 effect: 每次都會重新產生新的 function
		- 帶入 `[]`: function 不會改變
		- 帶入要監聽的 effect `[effect]`: 當帶入的 effect 發生變化後，產生新的 function，可同時帶入多個 effect
- **Return**
	- 回傳記憶的 function
- ## 使用情境
- 減少子元件不必要的 re-render
- 彌補 [[React.memo]] 的缺點
	- 當傳入的 props 為 function 時，可避免 React.memo 因"物件型別記憶體位置不同但值相同"而重新渲染的狀況