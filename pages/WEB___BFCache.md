category:: Note
type:: Web
alias:: BFCache

- ## BFCache (Back Forward Cache)
- ### Waht
	- 瀏覽器為了在往返上下一頁有更好的效能，會使用 BFCache 的策略，會把離開前的 DOM 狀態、JavaScript 狀態都保存在記憶體中，當再次進入此頁面時會直接從記憶體取得，便不會重新載入頁面。
- ### 取消 BFCache 方式
	- 在 HTML 內加入以下 meta tag
	  logseq.order-list-type:: number
		- ```html
		  <meta http-equiv="cache-control" content="no-cache">
		  <meta http-equiv="expires" content="0">
		  ```
	- 於使用 `pageshow`, `pagehide ` 兩個事件, `event` 可以使用 `persisted` 來判斷是否使用 BFCache，當有使用 BFCache 時，`event.persisted` 就會回傳 true。
	  logseq.order-list-type:: number
		- ```js
		  window.onpageshow = (event) => {
		    if (event.persisted) {
		      window.location.reload()
		    }
		  }
		  ```