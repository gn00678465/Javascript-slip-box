category:: Programing
type:: #React, #ReactRouter
alias:: Picking a Router
version:: 6.4.x+

- > React Router Dom 版本 6.4 以上新增了 Data APIs，可以方便快速建立 Router
  > 可將 Router 設定獨立為一個檔案方便管理
	- [`createBrowserRouter`](https://reactrouter.com/en/main/routers/create-browser-router) - same as `BrowserRouter`
	- [`createMemoryRouter`](https://reactrouter.com/en/main/routers/create-memory-router) - same as `MemoryRouter`
	- [`createHashRouter`](https://reactrouter.com/en/main/routers/create-hash-router) - same as `HashRouter`
- 以 `createBrowserRouter` 取代 `BrowserRouter`
- 以 `createRoutesFromElements` 取代 `Routes`
- 內部為主要的 `Route` 結構
- 將定義好的結構傳入 `RouterProvider` 的 `router` props 內
- ```jsx
  import {
    createBrowserRouter,
    createRoutesFromElements,
    Route,
    RouterProvider,
  } from "react-router-dom";
  
  const router = createBrowserRouter(
    createRoutesFromElements(
      <Route path="/" element={/* component */} />
    )
  );
  
  // 將建立的 router 傳入 RouterProvider 內
  
  <RouterProvider router={router} />
  
  ```
- ## 使用 Object 結構建立 Router
- version:: 6.8.x+
- 將 Router 以 Object 的結構建立
- 將定義好的結構傳入 `RouterProvider` 的 `router` props 內
- ```jsx
  import {
    createBrowserRouter,
    RouterProvider,
  } from "react-router-dom";
  
  const router = createBrowserRouter([
    {
      path: "/",
      element: <Root />,
      children: [
        {
          path: "dashboard",
          element: <Dashboard />,
        },
        {
          path: "about",
          element: <About />,
        },
      ],
    },
  ]);
  
  // 將建立的 router 傳入 RouterProvider 內
  
  <RouterProvider router={router} fallbackElement={<BigSpinner />} />
  ```
- ## Type Declaration
- ```typescript
  interface RouteObject {
    path?: string;
    index?: boolean;
    children?: React.ReactNode;
    caseSensitive?: boolean;
    id?: string;
    loader?: LoaderFunction;
    action?: ActionFunction;
    element?: React.ReactNode | null;
    errorElement?: React.ReactNode | null;
    handle?: RouteObject["handle"];
    shouldRevalidate?: ShouldRevalidateFunction;
  }
  
  type RemixRouter = {
    routes: RouteObject[],
    opts?: {
      basename?: string;
      window?: Window;
    }
  }
  ```
- ## Referenct
	- [React Router Dom - Route](https://reactrouter.com/en/main/route/route)
	- [Picking a Router](https://reactrouter.com/en/main/routers/picking-a-router)
	- [React Router Dom - RouterProvider](https://reactrouter.com/en/main/routers/router-provider)