category:: Programming
type:: #React, #API
alias:: Lazy & Suspense
version:: 18.x+

- ## `React.Lazy`
- > 動態載入 react component ，可以將達到 code splitting 的效果，需要用到時再用 import 載入
- 減少第一次載入頁面所需的 bundle size。
- ## `React.Suspense`
- > 透過 `Suspense` 可以讓 component 在 render 前先「等待」 ，目前須搭配 `React.Lazy` 使用
- **props**
	- `fallback: React.FunctionComponent`: 傳入等待載入 component 時要顯示的 component
- ## Usage
- ```typescript
  import { Lazy, Suspense } from 'react';
  import { BrowserRouter, Routes, Route } from 'react-router-dom';
  
  const About = Lazy(() => import(path of about component))
  
  export default () => (
    <BrowserRouter>
    	<Suspense fallback={<Loading />}>
    		<Routes>
              <Route path="/" element={<Home />} />
    			<Route path="/about" element={<About />} />
    		</Routes>
    	</Suspense>
    </BrowserRouter>
  )
  ```