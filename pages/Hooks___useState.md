category:: programing
type:: react

- ```typescript
  const [num, setNum] = useState(0);
  ```
- 使用解構方式取得的第 1 項，為當下的 state，且為 **read-only** 不可直接針對 state 做操作
- 第 2 項，為一個方法，主要作為操作 state 之用
	- 直接帶入修改後的 state
	- 帶入一個 function ，state 作為參數傳入此 function 內操作