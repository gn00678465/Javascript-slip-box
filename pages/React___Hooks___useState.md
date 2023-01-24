category:: Programing
type:: React, Hooks
alias:: useState

- ```typescript
  const [num, setNum] = useState(0);
  ```
- **Param**
	- `initialValue`: 可帶入基本型別
- **Return**
	- 使用解構方式取得的第 1 項，為當下的 state，且為 **read-only** 不可直接針對 state 做操作
	- 第 2 項，為一個方法，主要作為操作 state 之用
		- 直接帶入要修改的 state
		- 帶入一個 callback function ，previousState 作為參數傳入此 function 內操作
			- 帶入的參數為變更前的 state
- 當 state 更新時，會觸發 re-render