category:: Programing
type:: #Javascript, #Note
alias:: JS - 判斷資料類型

- > 使用 `typeof` 判斷資料類型只能區分基本類型 (`number`, `object`, `string`, ...)
- ## **`Object.prototype.toString.call(arg)`**
	- 此方式會回傳一個字串
	  logseq.order-list-type:: number
	- 字串為 `[object <type>]`, `<type>` 為判斷出的類型
	  logseq.order-list-type:: number
		- `[object Number]`, `[object Function]`, `[object AsyncFunction]`, ...
		  logseq.order-list-type:: number
- ## **`<target>.constructor.name`**
	- `<target>` 為要判斷類型的資料, 可以為基本類型的資料或變數
	  logseq.order-list-type:: number
	- 無法使用 `.`, 可以改為 `<target>['constructor'].name` 方式取得類型
	  logseq.order-list-type:: number
	- 回傳類型為字串
	  logseq.order-list-type:: number
		- `Number`, `String`, `Function`, `AsyncFunction`, ...
		  logseq.order-list-type:: number
	- logseq.order-list-type:: number