category:: Programing
type:: Javascript, API
alias:: window.open

- ```javascript
  window.open([url[, target[, windowFeatures]]]);
  ```
- **Parameters**
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
		  | `popup`| 以彈出式視窗開啟 |
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
- **Return Value**
	- 回傳開啟視窗的 [`WindowProxy`](https://developer.mozilla.org/en-US/docs/Glossary/WindowProxy) object
- ## Reference
	- [MDN Window: open() method](https://developer.mozilla.org/en-US/docs/Web/API/Window/open)
	- [iframe 與 window.open 黑魔法](https://blog.huli.tw/2022/04/07/iframe-and-window-open/#windowopen)