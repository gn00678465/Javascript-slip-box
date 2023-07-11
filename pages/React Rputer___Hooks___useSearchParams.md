category:: Programing
type:: #ReactRouter, #Hooks
alias:: useSearchParams

- > 操作 URL 的搜尋參數 (`?query=something`)
- ```tsx
  import { useSearchParams } from 'react-router-dom';
  const [searchParams, setSearchParams] = useSearchParams();
  ```
- **取得參數**
	- `searchParams.get(query: string)` => `string`
	- `searchParams.getAll(query: string)` => `string[]`
- **設定參數**
	- `setSearchParams({ query: value })`