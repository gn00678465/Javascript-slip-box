category:: Programing
type:: react,API
allas:: createContext

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
	- `Provider`
	- ``
	- `Consumer`