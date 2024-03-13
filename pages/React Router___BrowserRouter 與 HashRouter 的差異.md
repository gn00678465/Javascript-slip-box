category:: Programming
type:: #ReactRouter
alias:: BrowserRouter 與 HashRouter 的差異
title:: React Router/BrowserRouter 與 HashRouter 的差異

- ## BrowserRouter 與 HashRouter 的差異
	- 底層原理
		- **BrowserRouter**: 使用的是 HTML5 的 history API
		- **HashRouter**: 使用 URL 的 Hash 值
	- path 形式
		- **BrowserRouter**: BrowserRouter 的路徑中沒有`#`
		- **HashRouter**: HashRouter 的路徑包含`#`
	- 頁面重整後，對路由 state 參數的影響
		- **BrowserRouter**: state 保存在 history 物件中，頁面重整後沒有任何影響
		- **HashRouter**: 頁面重整後會導致路由 state 參數的丟失
- **MemoryRouter**: 不讀寫瀏覽器的網址列的狀況下導航頁面