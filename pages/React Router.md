category:: Programing
type:: React,Router
alias:: React Router
version:: 6.x

- ## Install
	- ```bash
	  pnpm add react-dom-router
	  ```
- ## 建立 Router
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
		- `path`：定義路徑
		- `element`：定義對應的 component
	- **切換頁面**
	- ```jsx
	  import { Link } from "react-router-dom";
	  
	  <Link to="/"">Link</Link>
	  ```
- ## 巢狀路由
	-
	-
- ## Reference
	- [Office Website](https://reactrouter.com/en/main)