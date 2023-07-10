category:: Programing
type:: #React, #ReactRouter
alias:: Protected Routes

- > 利用 `Outlet` and [[React Router/Hooks/useNavigate]] 的功能來達到路由的權限管理
- ```tsx
  import { Outlet, useNavigate } from 'react-router-dom';
  
  const ProtectedRoutes = ({ permission }) => {
    const navigate = useNavigate();
    return permission ? <Outlet> : navigate('login');
  };
        
  export default ProtectedRoutes
  ```
- **useage**
- ```tsx
  <Route path={/* path */} element={<ProtectedRoutes permission={/* permission */} />}>
  	<Route path={} element={/* protected page */}></Route>
  </Route>
  ```