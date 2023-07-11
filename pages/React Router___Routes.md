category:: Programing
type:: #React, #ReactRouter
alias:: Routes
version:: 6.x+

## 建立 Router
	- ```jsx
	  import * as React from "react";
	  import * as ReactDOM from "react-dom";
	  import { BrowserRouter } from "react-router-dom";
	  
	  ReactDOM.render(
	    <BrowserRouter>
	      {/* The rest of your app goes here */}
	    </BrowserRouter>,
	    root
	  );
	  ```
	- [[React Router/BrowserRouter 與 HashRouter 的差異]]
	- **App.tsx**
	- ```jsx
	  import { Routes, Route } from 'react-router-dom';
	  
	  export default function App() {
	    return (
	    	<Routes>
	        <Route path="/" element={/* import component */}></Route>
	      </Routes>
	    )
	  }
	  ```
	- `Routes`: 必須在所有 `Route` 的最外層
	- `Route`:  定義路徑與對應的 component
		- `path`：(string | object)定義路徑
		- `element`：定義對應的 component
- ## Loader
- version:: 6.4.x+
- > 在 `Route` 可以設定一個 `loader` 並傳入一個 function，此 function 會在 `Route` render 前呼叫。
  > **只支援 6.4 以上的 Data APIs** [[Picking a Router]]
- 在 component 內引入 `useLoaderData`，便可以拿到 Route 所建立的 loader function 所取得的資料
	- ```typescript
	  import { useLoaderData } from 'react-router-dom';
	  
	  const data = useLoaderData();
	  ```
- ### params
	- 在動態路由 (Dynamic Segments) 中設定的 loader，`:param` 會以 `params` 傳入 `loader` 的 function 中。
	- ```jsx
	  <Route
	    path="/teams/:teamId"
	    loader={({ params }) => {
	      console.log(params.teamId);
	    }}
	    element={<Team />}
	  />;
	  ```