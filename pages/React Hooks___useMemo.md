category:: Programing
type:: react,hooks
alias:: useMemo

- ```typescript
  const memoizedValue = useMemo(() => {
    return // some value
  }, [effect])
  ```
- **Parameter**
	- `callback function` 作為副作用更新後要執行的函式
	- `[effect]` 監聽副作用的變化
		- 未帶入 effect: 會一直重複執行 callback function
		- 帶入 `[]`: 畫面 render 後只執行一次
		- 帶入要監聽的 effect `[effect]`: 當監聽的 effect 發生變化後，執行 callback function，可同時帶入多個 effect
- **Return**
	- 回傳一個 memoized 的值。