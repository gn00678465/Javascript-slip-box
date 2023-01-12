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
		- `path`：(string | object)定義路徑
		- `element`：定義對應的 component
- ## 切換路由
	- 使用 Link component 來切換路由
	- `Link` 必須放在 `BrowserRouter` 內部
	- ```jsx
	  import { Link } from "react-router-dom";
	  
	  <Link to="/"">Link</Link>
	  ```
	- `to`: (string | object)要切換到的路由路徑
- ## 巢狀路由
	- 使用巢狀路由需要將 `Route` 包在 `Route` 中
	- 在巢狀路由的父層 component，必須加上 `<Outlet />` 的 component 才可以顯示內層的 component
	- ```jsx
	  <Route path="/nested" element={<Nested />}>
	  	<Route index element={/* import component */}></Route>
	      <Route path="page" element={/* import component */}></Route>
	  </Route>
	  ```
		- `index`: (boolean) 預設載入的路由
	- **Nested.tsx**
	- ```jsx
	  import { Outlet } from 'react-router-dom';
	  
	  export default function Nested() {
	    return (
	    	<div><Outlet /></div>
	    )
	  }
	  ```
-
- ## Reference
	- [Office Website](https://reactrouter.com/en/main)