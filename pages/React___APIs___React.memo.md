category:: Programing
type:: #React, #API
alias:: React.memo

- > 將元件 re-render 方式由**當父層元件 re-render 時，子層元件就會跟著 re-render**
  > 使用 React.memo 後，**當傳入子層元件的 props 更新時，才會觸發 re-render**
- ```typescript
  const Component = React.memo(() => {})
  ```