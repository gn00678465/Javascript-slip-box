- > 利用 `Outlet` and [[React Router/Hooks/useNavigate]] 的功能來達到路由的權限管理
- ```tsx
  import { Outlet, useNavigate } from 'react-router-dom';
  
  const ProtectedRoutes = ({ permission }) => {
    const navigate = useNavigate();
    return permission ? <Outlet> : navigate('login');
  };
        
  export default ProtectedRoutes
  ```
- ```tsx
  <Route path={/* path */} element={<ProtectedRoutes permission={/* permission */} />}>
  	<Route path={} element={/* protected page */}></Route>
  </Route>
  ```