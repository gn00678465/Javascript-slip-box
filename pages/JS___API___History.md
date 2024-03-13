category:: Programming
type:: Javascript, API
alias:: History

- > History 是一個瀏覽器提供的歷史紀錄操作介面，可以透過 `window.history` 來取得該物件。
- ## Properties
	- `length: number`: **Read-only** 取得目前瀏覽器分頁的歷史紀錄總數。
	- `scrollRestoration: 'auto' | 'manual'`: 影響捲動行為。
		- `auto`: 當使用者離開某個頁面時，瀏覽器會紀錄離開時的卷動距離，並在使用者到該頁時，自動卷動到記錄的位置。
		- `manual`: 瀏覽器不會紀錄捲動距離，每次頁面更換時都會回到頂部。
	- `state: any`:
- ## Methods
	- `back: void`: 相當於瀏覽器介面上的「上一頁」。
	- `forward: void`: 相當於瀏覽器介面上的「下一頁」。
	- `go: (arg: number) => void`: 傳入一個數字來代表要往前或往後至相對於目前頁面的哪個歷史位置。
		- -1: 相當於「上一頁」
		- 1: 相當於「下一頁」
		- 0: 瀏覽器會重新整理目前的頁面
	- ### `pushState`
		- > 在不移動頁面的情況下，添加一筆歷史紀錄。
		- ```javascript
		  history.pushState(state, unused)
		  history.pushState(state, unused, url)
		  ```
		- **Parameters**
			- `state: object`: 可以接受一個物件，該物件裡可以存放任何資料，當 `popstate` event 被觸發，event 的 `state` 屬性，它存放的就會是此時設定的 `state` 參數副本。
			- `unused: string | null`: 被暫時保留的參數，實際上沒有任何用途，不可省略。
			- `url?: string`: **optional** 用來設定添加的這筆歷史紀錄的網址，必須為相同的 origin，否則會拋出錯誤。
		- **Return**: `undefined`
	- ### `replaceState`
		- > 在不移動頁面的情況下，修改最新一筆的歷史紀錄。
		- ```javascript
		  history.replaceState(state, unused)
		  history.replaceState(state, unused, url)
		  ```
		- **Parameters**
			- `state: object`: 可以接受一個物件，該物件裡可以存放任何資料，當 `popstate` event 被觸發，event 的 `state` 屬性，它存放的就會是此時設定的 `state` 參數副本。
			- `unused: string | null`: 被暫時保留的參數，實際上沒有任何用途，不可省略。
			- `url?: string`: **optional** 用來設定添加的這筆歷史紀錄的網址，必須為相同的 origin，否則會拋出錯誤。
		- **Return**: `undefined`
- ## Events
	- ### `popstate`
		- > 這個事件會在使用者進行歷史紀錄操作（例如上一頁、下一頁）時觸發。
		- ```typescript
		  window.addEventListener('popstate', (event: PopStateEvent) => {
		    console.log(event.state)
		  })
		  ```
		- `PopStateEvent`: [PopStateEvent](https://developer.mozilla.org/en-US/docs/Web/API/PopStateEvent) 繼承至 [Event](https://developer.mozilla.org/en-US/docs/Web/API/Event)
		- `PopStateEvent.state`: 從 `pushState` 或 `replaceState` 所帶入 `state` 的副本。
-
- ## Reference
	- [MDN History API](https://developer.mozilla.org/en-US/docs/Web/API/History)