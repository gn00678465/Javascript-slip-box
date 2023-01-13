category:: Programing
type:: React, Router, Hooks
alias:: useNavigate

- ```ts
  const navigate = useNavigate();
  
  navigate(path);
  ```
- `path` (`string | number`):
	- 帶入要導向的路徑
	- -1: 上一頁
	- 1: 下一頁