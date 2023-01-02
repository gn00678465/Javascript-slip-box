- ```typescript
  useEffect(function() {}, [option])
  ```
- 可帶入兩個參數，分別為
	- `callback function` 作為副作用更新後要執行的函式
	- `[options]` 監聽副作用的變化
		- 未帶入 `undefined`: 會一直重複執行 callback function
		- 帶入 `[]`: 畫面 render 後只執行一次
		- 帶入要監聽的 state `[state]`: 當監聽的 state 發生變化後，執行 callback function，可帶入多個 state
- useEffect callback 本身不能作為 `async function` 使用
	- 需使用 `async function` 的情況下，callback function 可使用 IIFE(立即函式)
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
		  })
		  ```