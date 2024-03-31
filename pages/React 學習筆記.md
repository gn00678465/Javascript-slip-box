id:: 63b0def7-3b40-4903-b8c2-502d3dff5ec1
category:: Programming
type:: #[[React]]
alias:: React 學習筆記
version:: 18.x+

- ## Intro basic
	- ### JSX 與 HTML 的標籤屬性
	  collapsed:: true
		- `class` 須改為 `className`
		- `inline style` 須使用 `object` 寫法
		- `Input` 標籤中
			- `checked` 須改為 `defaultChecked`
			- `value` 需與 `onChange` 事件一起使用
			- 若無使用 `onChange` 事件， `value` 須改為 `defaultValue`
			- `label` 標籤的 `for` 屬性須改為 `htmlFor`
			- `textarea` 的值須使用 `defaultValue`
			- `select` 需使用 `defaultValue`，並綁訂於 `select` 標籤上
		- render HTML 因為安全性問題，須改為下列語法
			- ```jsx
			  <div dangerouslySetInnerHTML={{__html: 'First &middot; Second'}}></div>
			  ```
	- ### Component
	  collapsed:: true
		- component 必須以**大寫**開頭
		- 傳入 component 內的資料以 `[property]="value"` 或者 `[property]={value}` 方式傳入，component 內以 `props` 接收傳入的所有資料
			- `[property]="value"` 傳入以 string 為主
			- `[property]={value}` 傳入 string 以外的型別、變數或 function
		- 以 loop 方式 render component，每一個 component 必須帶入 key，且 key 必須為**唯一值**
		- **children 也是 props**，可直接將內容(並非 property )傳入 component 內
			- ```tsx
			  interface Props {
			    children: React.ReactNode;
			  }
			  
			  const Child = ({ children }: Props) => {
			    return <p>{ children }</p>
			  }
			  
			  <Child>pass data</Child>
			  ```
- ## React Hooks
	- > 所有 react hooks 的方法只能定義在 Component 的作用域內
	- [[React/Hooks/useState]]
	- [[React/Hooks/useEffect]]
	- [[React/Hooks/useRef]]
	- [[React/Hooks/useMemo]]
	- [[React/Hooks/useContext]]
	- [[React/Hooks/useReducer]]
- ## React API
  collapsed:: true
	- [[React/APIs/React.createElement]]
	- [[React/APIs/React.memo]]
	- [[React/APIs/React.createContext]]
	- [[Lazy & Suspense]]
- ## React Context
- {{embed [[React/React Context]]}}
- ## React Router
  collapsed:: true
	- {{embed [[React Router]]}}
- ## Third Party 狀態管理
  collapsed:: true
	- Redux
	- Zustand