category:: Programing
type:: #Note, #React
alias:: React - Compound Component Pattern

- ## 適合使用的時機
	- 多個元件需要相依在一起才能使用時
	  logseq.order-list-type:: number
	- CSS 彼此之間有父層和子層的相依關係
	  logseq.order-list-type:: number
	- 都需要在某個 Provider 內才能作用
	  logseq.order-list-type:: number
- ## 實作
	- 建立主要 component
	  logseq.order-list-type:: number
	- 使用 useContext 管理 state
	  logseq.order-list-type:: number
	- 將 subcomponent 掛載於主要 component 底下
	  logseq.order-list-type:: number
- ## Example
	- ```tsx
	  // List.tsx
	  import { FC } from 'react';
	  import ListContext, { useListContext } from './context';
	  import { Item } from './item'
	  
	  const List: FC = ({ children, data }) => {
	    return (
	      // 使用 useContext 管理 state
	    	<ListContext.Provider value={data}>
	        <ol>
	            {children}
	        </ol>
	      </ListContext.Provider>
	    )
	  }
	  
	  // 將 subcomponent 掛載於主要 component 底下
	  List.Item = Item;
	  
	  export default List;
	  ```
	- ```tsx
	  // usage
	  import List from './List';
	  
	  const App = () => {
	    <List data={data}>
	      <List.Item>Test</List.Item>
	    </List>
	  }
	  ```
- ## Reference
	- [Compound Component Pattern](https://pjchender.dev/react/react-compound-component-pattern/)