id:: 63c0a348-2799-4311-ab7a-f821a61943d2
category:: Programing
type:: React, Router
alias:: React Router
version:: 6.x+

- ## Install
	- ```bash
	  # npm
	  npm install react-dom-router
	  # yarn
	  yarn add react-dom-router
	  # pnpm
	  pnpm add react-dom-router
	  ```
- ## 建立 Router
  collapsed:: true
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
- ## 切換路由
	- ### `Link`
		- 必須放在 `BrowserRouter` 內部
		- ```tsx
		  import { Link } from "react-router-dom";
		  
		  <Link to="/">Link</Link>
		  ```
		- `to`: (string | object)要切換到的路由路徑
	- ### `NavLink`
		- ```tsx
		  <NavLink to="/" className={({ isActive }) => { return /* css */ }}></NavLink>
		  ```
		- 預設會加入 `active` 的 className
		- **className** or **style** 可帶入 function 自訂要使用的 className
- ## Nested Router 巢狀路由
	- 使用巢狀路由需要將 `Route` 包在 `Route` 中
	- 在巢狀路由的父層 component，必須加上 `<Outlet />` 的 component 才可以顯示子層的 component
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
	    	<div><Outlet context={/* pass value */} /></div>
	    )
	  }
	  ```
	- ### 資料傳遞
		- [[useOutletContext]]
- ## 動態路由
	- ```tsx
	  <Route path=":[params]" element={/* import component */}></Route>
	  ```
	- `params`: 名稱可以自訂
	- component 內引入 [[React Router/Hooks/useParams]] 即可取得資料
- ## Hooks
	- [[React Router/Hooks/useOutletContext]]
	- [[React Router/Hooks/useParams]]
	- [[React Rputer/Hooks/useSearchParams]]
	- [[React Router/Hooks/useNavigate]]
- ## Other
	- 404 頁面
		- ```tsx
		  <Route path="*" element={/* import 404 component */}></Route>
		  ```
- ## Reference
	- [Office Website](https://reactrouter.com/en/main)