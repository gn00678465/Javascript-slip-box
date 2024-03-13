category:: Programming
type:: #ReactRouter, #Hooks
alias:: useNavigate

- ```ts
  const navigate = useNavigate();
  navigate(to, [options]);
  ```
- > 實現路由導向的功能
- ## Type Declaration
	- ```typescript
	  interface NavigateFunction {
	    (
	      to: To,
	      options?: {
	        replace?: boolean;
	        state?: any;
	        relative?: RelativeRoutingType;
	      }
	    ): void;
	    (delta: number): void;
	  }
	  
	  ```
- `to: To`:
	- `string`: 帶入要導向的路徑
	- `number` **-1**: 上一頁, 以此類推
	- `number` **1**: 下一頁, 以此類推
- `options`: 傳遞變數到下一個頁面
	- 搭配 `useLocation` 取得傳遞的變數
- ## Reference
	- [useNavigate](https://reactrouter.com/en/main/hooks/use-navigate)