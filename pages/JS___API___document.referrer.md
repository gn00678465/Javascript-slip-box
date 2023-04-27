category:: Programing
type:: Javascript, API
alias:: document.referrer

- > 取得當前頁面的前一個頁面網址
- ```typescript
  const url: string = document.referrer
  ```
- **回傳**
	- 當前頁面的前一個頁面網址(url)
-
- 某些場景下無法取得上一個頁面 referrer 資訊
	- 在瀏覽器中直接輸入網址
	- 使用 `location.reload()` 重整頁面
	- 從 Https 進入 Http 協議的網頁
	- `a` 標籤設定 `rel="noreferrer"`
	- `meta` 標籤設定不讓瀏覽器傳送 `referrer`
		- ```html
		  <head>
		    <meta content="never" name="referrer">
		  </head>
		  ```
- ## Reference
	- [MDN Document: referrer property](https://developer.mozilla.org/en-US/docs/Web/API/Document/referrer)