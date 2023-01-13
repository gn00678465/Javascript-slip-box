category:: Programing
type:: React, Router, Hooks
alias:: useOutletContext

- > 從父層 component `Outlet` 傳遞數值到子層的 component 內
- `Outlet` 加上一個屬性 `context`，並帶入要傳遞的值
- 在需要接收資料的子層中引入 `useOutletContext`
- ```jsx
  import { useOutletContext } from "react-router-dom";
  
  export function Context() {
    const context = useOutletContext();
    return (<div></div>)
  }
  ```