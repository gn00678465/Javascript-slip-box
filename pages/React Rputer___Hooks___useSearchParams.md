category:: Programing
type:: React, Router, Hooks
alias:: useSearchParams

- > 操作 URL 的搜尋參數 (`?query=something`)
- ```tsx
  import { useSearchParams } from 'react-router-dom';
  const [searchParams, setSearchParams] = useSearchParams();
  ```
- **取得參數**
	- `search`
		- `searchParams.get(query)`
- `setSearchParams({ query: value }