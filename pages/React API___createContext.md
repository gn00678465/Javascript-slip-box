category:: Programing
type:: react,API
alias:: createContext

- ```typescript
  const ContextStore = React.createContext(defaultValue);
  
  // 使用 ContextStore
  function ContextStoreComponent = () => {
    // 定義狀態
    return (
    	<ContextStore.Provider value={{ //傳入狀態 }}>
  	</ContextStore.Provider>
    )
  }
  ```
- 建立 Context Object，並設定預設值 `defaultValue`
- Context object
	- `Provider`: 將指定的值傳給更下層的 `Consumer` 使用
		- `value`: 提供給 Provider 以下的 Consumer 使用的值
		- 可以巢狀使用 `Context.Provider`
		- value 更新時，下層的 `conssumer` 必定會 re-render
	- `Consumer`: 接收上層 `Provider` 傳下來的值
- 使用 [[React Hooks/useContext]] 取得特定 `Provider` 傳下來的值
- ## Reference
	- [ I Want To Know React - Context 語法](https://ithelp.ithome.com.tw/articles/10252519)