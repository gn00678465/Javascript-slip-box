category:: Programing
type:: React, Router, Hooks
alias:: useRoutes

- > 以 function 的方式建立 Routes 的結構
- ```typescript
  import { useRoutes } from "react-router-dom";
  
  const routes = useRoutes([
      {
        path: "/",
        element: <Dashboard />,
        children: [
          {
            path: "messages",
            element: <DashboardMessages />,
          },
          { path: "tasks", element: <DashboardTasks /> },
        ],
      },
      { path: "team", element: <AboutPage /> },
    ]);
  export default () => routes
  ```
- **Parameters**
	- `routes: RoutesObject[]`: 帶入與  Routes components 相同的結構(非 JSX)
- **Return**
	- 與 `Routes` 相同結構的 React DOM
- ## Reference
	- [useRoutes](https://reactrouter.com/en/main/hooks/use-routes)