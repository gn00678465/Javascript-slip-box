category:: Programing
type:: React
alias:: Error boundary
version:: 16.0+

- > 錯誤邊界是一個 React component，它**捕捉了任何在它的 child component tree 裡發生的 JavaScript 的錯誤，記錄那些錯誤，然後顯示在一個 fallback 的使用介面**
- ## Intro
	- 當子元件發生錯誤時就會被 Error Boundary 捕捉，不會讓錯誤影響到錯誤邊界外的任何元件。
	- Error Boundaries（錯誤邊界）**不會**捕獲以下錯誤：
		- 事件處理程序  (event handler)
		- 異步(非同步)代碼 (例如 `setTimeout` 或 `requestAnimationFrame` callback)
		- Server side rendering
		- 在錯誤邊界裡丟出的錯誤（而不是在它底下的 children）
	- Only class components can be error boundaries. (目前沒有任何 React 原生的 hooks 能取代 componentDidCatch)
- ## 基本觀念
	- 一個 class component 如果定義了 [`static getDerivedStateFromError()`](https://zh-hant.reactjs.org/docs/react-component.html#static-getderivedstatefromerror) 或 [`componentDidCatch()`](https://zh-hant.reactjs.org/docs/react-component.html#componentdidcatch) 其中一種（或兩種都有）生命週期，它就會變成錯誤邊界。
	- 使用 `static getDerivedStateFromError()` 來 render fallback 的 UI，以及使用 `componentDidCatch()` 來記錄錯誤的資訊。
- ## Usage
	- ```typescript
	  class ErrorBoundary extends React.Component {
	    constructor(props) {
	      super(props);
	      this.state = { hasError: false };
	    }
	  
	    static getDerivedStateFromError(error) {
	      // 更新 state 以至於下一個 render 會顯示 fallback UI
	      return { hasError: true };
	    }
	  
	    componentDidCatch(error, errorInfo) {
	      // 你也可以把錯誤記錄到一個錯誤回報系統服務
	      logErrorToMyService(error, errorInfo);
	    }
	  
	    render() {
	      if (this.state.hasError) {
	        // 你可以 render 任何客製化的 fallback UI
	        return <h1>Something went wrong.</h1>;
	      }
	  
	      return this.props.children;
	    }
	  }
	  ```
- ## Reference
	- [錯誤邊界](https://zh-hant.reactjs.org/docs/error-boundaries.html)