category:: Programming
type:: #React, #API
alias:: React.createContext

- ## Syntax
	- ```ts
	  const Context = React.createContext<ContextType>(defaultValue);
	  ```
	- **Parameters**
		- `defaultValue`: 建立 Context 時的預設值，可帶入 `null`
	- **Return**
		- Context Object
- ## Usage
	- ```tsx
	  const ContextStore = React.createContext(defaultValue);
	  
	  // 使用 ContextStore
	  function ContextStoreComponent = () => {
	    // 定義狀態
	    return (
	    	<ContextStore.Provider value={/* some value */}>
	          {/* ... */}
	  	</ContextStore.Provider>
	    )
	  }
	  ```
	- 建立 Context Object，並設定預設值 `defaultValue`
	- Context Object
		- `Provider`: 將指定的值傳給更下層的 `Consumer` 使用
			- `value`: 提供給 Provider 以下的 Consumer 使用的值
			- value 更新時，下層的 `consumer` 必定會 re-render
		- `Consumer`: 接收上層 `Provider` 傳下來的值
	- 可以巢狀使用 `Context.Provider`
		- 當巢狀使用同一個 Provider 時，內層的 Provider 會覆蓋（非 Merge）外層 Provider 的 `value`。
	- 使用 [[React/Hooks/useContext]] 取得特定 `Provider` 傳下來的值
- ## Reference
	- [ I Want To Know React - Context 語法](https://ithelp.ithome.com.tw/articles/10252519)