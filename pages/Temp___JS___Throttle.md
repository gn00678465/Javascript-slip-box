category:: Programming
type:: Javascript
alias:: Throttle

- > throttle(節流)
  > 在某段時間內只執行觸發的**一次**事件
- ## 簡易 Throttle 實作
	- Throttle 可帶入兩個參數
		- `callback: (...args: unknown[]) => unknown`: 觸發的 function
		- `delay: number`: 延遲時間
	- ```javascript
	  function throttle(callback, delay = 1000) {};
	  ```
	- Throttle 內部回傳一個 function (閉包)，並取得 closure 內的 `arguments`
	- ```javascript
	  function throttle(callback, delay = 1000) {
	    return function() {
	      const context = this;
	      const args = [].slice.call(arguments);
	    }
	  };
	  ```
	- 閉包內使用 `setTimeout`，根據 delay 的時間觸發 `callback`，並帶入 closure 內的參數
	- ```javascript
	  function throttle(callback, delay = 1000) {
	    return function() {
	      const context = this;
	      const args = [].slice.call(arguments);
	      setTimeout(() => {
	        callback.apply(context, args);
	      }, delay)
	    }
	  };
	  ```
	- 當 closure 不斷重新觸發，return 不進行後續的工作
	- ```javascript
	  ```
- ## Reference
	- [Debounce vs Throttle](https://redd.one/blog/debounce-vs-throttle)