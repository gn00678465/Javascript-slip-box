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
	- ``