category:: Programing
type:: React, Context
alias:: React Context

- > React Context 是一種利用向下廣播來傳遞資料的方式。
- ## 注意事項
	- 要將**全域性資料**傳遞給很多 components 時可使用。
	- 不應該只為了避免傳遞過多層 props 就使用 context。
	- 濫用 context 則可能造成 component 重用性降低，也可能造成追蹤程式碼不易。
	- 當想要傳遞一些只有特定（非全域性資料）下層 component 需要的資料時，可使用 [composition](https://ithelp.ithome.com.tw/articles/10251762) 技巧來解決。
- ## API
	- [[React/APIs/React.createContext]]
		- `Context.Provider`
		- `Context.Consumer`
		  collapsed:: true
			- 用途為接收上層 `Provider` 傳下來的值。
			- 有巢狀的 Provider 時，Consumer 接收到的值會是由最靠近自己的 Provider 所提供的。
			- ```tsx
			  <Context.Consumer>
			  	{value => /* render something based on the context value */}
			  </Context.Consumer>
			  ```
			- **prop**
				- `children: (value: any) => ReactElement`: 必須為一個 function，而非 React element
					- `value`：代表 Consumer 接收到的值，與 props 一樣，可能為任意的值。
					- 回傳 `React element` 代表要 render 出來顯示在畫面上的內容
		- `Context.displayName`
		  collapsed:: true
			- 可讓 React dev tool 上的 context 顯示為 `displayName` 設定的名稱。
			- 預設的 context displayName 為 Context，不好在 React dev tool 上區分個別的 Context。
	- [[React/Hooks/useContext]]
-
- ## Reference
	- [Passing Data Deeply with Context](https://react.dev/learn/passing-data-deeply-with-context)