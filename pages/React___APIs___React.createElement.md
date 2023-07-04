category:: Programing
type:: React, APIs
alias:: React.createElement

- > babel 會將 JSX 編譯成 React.createElement
- ```typescript
  React.createElement(component[, props[, ...children]])
  ```
- **Parameters**
	- `component: string | React.FunctionComponent`: HTML 的標籤，或者是 React component
	- `props: any | null`: HTML 的屬性或傳入 Component 的 props
	- `children: any[] | null`: 子節點
- **Return**
	- 給定類型的 ReactElement