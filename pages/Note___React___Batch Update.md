category:: Note
type:: #Note, #[[React]]
alias:: React - Batch Update
version:: 18.x+

- > 當 useState 的 state 或 props 發生變化, 皆會驅動 Component re-render, re-render 的次數一多就會造成資源耗損。
  React 會將所有改變 state 的操作蒐集起來執行, 再使用最後的 state 去 re-render, 從而達到 Batch Update 的效果
  React 會將呼叫的動作依序紀錄到一個待執行計算的佇列（queue）中
- ```tsx
  const [count, setCount] = useState(0);
  
  function increment() {
    setCount(count + 1);
  }
  
  function handleClick() {
    increment();
    increment();
    increment();
  }
  ```
	- <p style="font-size: 14px; color: #aaa">因 Batch Update , 呼叫 3 次 increment 會合併執行, 而此時對應的 count 為 0, 最終的輸出 <code>count: 1</code></p>
- ```tsx
  const [count, setCount] = useState(0);
  
  const increment: SetStateAction<number> = (prev: number) => prev + 1; // updater function
  
  function handleClick() {
    setCount(increment);
    setCount(increment);
    setCount(increment);
  }
  ```
	- <p style="font-size: 14px; color: #aaa">updater function 會被 react 放入 queue 並依序執行, 最終的輸出 <code>count: 3</code></p>
- ## Reference
	- [[useState]]
	- [React as a UI Runtime#batching](https://overreacted.io/react-as-a-ui-runtime/#batching)
	- [React 的 batch update 策略](https://lance.coderbridge.io/2021/06/10/react-batch-update-in-hooks-and-react18/)