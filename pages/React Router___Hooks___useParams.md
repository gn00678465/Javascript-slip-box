category:: Programming
type:: #ReactRouter, #Hooks
alias:: useParams

- ```tsx
  import { useParams } from 'react-router-dom';
  const params = useParams();
  ```
- > 取得動態路由傳入的參數
- ## useage
- ```tsx
  <Route path="/user" element={/* import component */}>
  	<Route path=":id" element={<UserInfo />}></Route>
  </Route>
  
  // UserInfo
  const { id } = useParams();
  ```