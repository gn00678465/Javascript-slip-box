category:: Programing
type:: React, Hooks
alias:: useEffect

- ```typescript
  useEffect(function() {}, [effect])
  ```
- **Parameter**
	- `callback function` 作為副作用更新後要執行的函式
	- `[effect]` 監聽副作用的變化
		- 未帶入 effect: 會一直重複執行 callback function
		- 帶入 `[]`: 畫面 render 後只執行一次
		- 帶入要監聽的 effect `[effect]`: 當監聽的 effect 發生變化後，執行 callback function，可同時帶入多個 effect
- useEffect callback function 本身不能作為 `async function` 使用
	- 如需使用 `async function` 的情況下，callback function 可使用 IIFE(立即函式)
		- ```typescript
		  useEffect(() => {
		    (async function() {
		      try {
		        const res = await asyncFunction();
		        console.log(res);
		      }
		      catch(err) {
		        console.log(err)
		      }
		    })()
		  }, [])
		  ```
- ## 移除監聽
- 在 useEffect callback function 內定義一個 return function (cleanup)，將會是元件準備要卸載時會觸發的行為
	- 由於每次 re-render 時，執行的都是一個全新的 effect，因此在每次 re-render 前也都會執行 cleanup 的函式
	- ```typescript
	  useEffect(() => {
	    console.log('This is like componentDidMount')
	    return () => {
	    	console.log('This is like componentWillUnmount')
	    };
	  }, []);
	  ```