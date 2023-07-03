category:: Programing
type:: Javascript, Window
alias:: window.open

- ## Syntax
	- ```javascript
	  window.open([url[, target[, windowFeatures]]]);
	  ```
	- **Parameters**
	  collapsed:: true
		- `url?:string`: **optional** 新視窗要引用的網址。
		- `target?:string`: **optional** 新視窗的名稱，也可以帶入 `_self`, `_blank`, `_parent`, and `_top`。
		- `windowFeatures?:string`: **optional**
			- 新視窗的相關設定，不能包含空白符號，須以 `,` 相隔。
			- **位置與尺寸**
			- | **參數** | **參數值與說明** |
			  |`width` or `innerWidth`| 設定新視窗的寬度，單位是 pixels，最小數值需要 100|
			  |`height` or `innerHeight`| 設定新視窗的高度，單位是 pixels，最小數值需要 100|
			  | `left` or `screenX` | 距離左邊的距離，單位是 pixels。 |
			  | `top` or `screenY` | 距離上面的距離，單位是 pixels。 |
			  | `popup`| 以彈出式視窗開啟，寫法為 `popup`, `popup=yes`, `popup=1`；不以彈出式視窗開啟，寫法為 `popup=no` |
			- **Toolbar and chrome features**
			- > All features can be set to yes, 1 or just be present to be "on", set to *no* or *0* or in most cases just not present to be "off".
			  下列 features 在 chrome 皆不支援。
			- | **參數** | **參數值與說明** |
			  | `toolbar` | 指定工具列是否顯示，預設是顯示，如果要設為不顯示，寫法是 `toolbar=no`。 |
			  | `scrollbars` | 指定 scroll bars 是否顯示，要顯示寫法是 `scrollbars=yes`，不顯示寫法是 `scrollbars=no`。 |
			  | `resizable` | 訪客是否可以自己調整視窗大小，預設是可以，如果要設為不能調整，寫法是 `resizable=no`。 |
			  | `location` | 是否顯示網址列，預設是顯示，如果不要顯示，寫法是`location=no` 。 |
			  | `menubar` | 是否顯示目錄欄位，預設是會顯示，如果不要顯示，寫法是 `menubar=no`。 |
			  | `status` | 是否顯示狀態列，預設是顯示，如果不要顯示，寫法是 `status=no`。 |
	- **Return**
		- 回傳開啟視窗的 [`WindowProxy`](https://developer.mozilla.org/en-US/docs/Glossary/WindowProxy) object
- ## Event
	- ### onbeforeunload
		- > 當 window, body, frameset 物件「被卸載之前」會觸發這個事件
		  > 關閉瀏覽器或者是頁面時觸發
		  > 觸發時間早於 `onunload`
		- ```javascript
		  window.addEventListener("beforeunload", (event) => {
		    console.log(event)
		  });
		  
		  window.onbeforeunload = (event) => {
		     console.log(event)
		  };
		  ```
	- ### onunload
		- > 當 window, body, frameset 物件「被卸載之後」才會觸發這個事件
		  > 關閉瀏覽器或者是頁面時觸發
		- ```javascript
		  window.addEventListener("unload", (event) => {
		    console.log(event)
		  });
		  
		  window.onunload = (event) => {
		    console.log(event)
		  }
		  ```
	- ### onload
		- > 當正常進入頁面時觸發
		  > **不包含**上一頁與下一頁按鈕的操作 ([[BFCache]])
		  > 觸發時間早於 `pageShow`
		- ```js
		  window.addEventListener("load", (event) => {
		    console.log(event)
		  });
		  
		  window.load = (event) => {
		    console.log(event)
		  }
		  ```
	- ### pageshow
		- > 當進入頁面時皆會觸發
		  > **包含**上一頁與下一頁按鈕的操作 ([[BFCache]])
		- ```js
		  window.addEventListener('pageshow', function(event) {
		      console.log('after , pageshow :',event);
		  });
		  
		  window.onpageshow = (event) => {
		    console.log('after , pageshow :',event);
		  };
		  ```
	- ### pagehide
		- > 重新整理頁面或 `target="_self"` 會觸發
		  > 可取代 `onunload` 事件
		- ```javascript
		  window.addEventListener("pagehide", (event) => {
		    console.log(event)
		  });
		  ```
- ## Reference
	- [MDN Window: open() method](https://developer.mozilla.org/en-US/docs/Web/API/Window/open)
	- [iframe 與 window.open 黑魔法](https://blog.huli.tw/2022/04/07/iframe-and-window-open/#windowopen)
	- [如何避免使用者在特定網頁表單在未經送出時意外離開](https://blog.miniasp.com/post/2009/08/12/How-to-avoid-page-reload-or-redirect-by-incident)