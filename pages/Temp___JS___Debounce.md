category:: Programing
type:: Javascript
alias:: Debounce

- > debounce(防抖)
  > 在某段時間內只執行觸發的**最後一次**事件
- ## 簡易 Debounce 實作
	- Debounce 可帶入兩個參數
		- `callback: (...args: unknown[]) => unknown`: 觸發的 function
		- `delay: number`: 延遲時間
	- ```javascript
	  function debounce(callback, delay = 1000) {};
	  ```
	- Debounce  內部回傳一個 function (閉包)，並取得 closure 內的 `arguments`
	- ```javascript
	  function debounce(callback, delay = 1000) {
	    // closure
	    return function() {
	      const context = this;
	      const args = [].slice.call(arguments);
	    }
	  };
	  ```
	- 閉包內使用 `setTimeout`，根據 delay 的時間觸發 `callback`，並帶入 closure 內的參數
	- ```javascript
	  function debounce(callback, delay = 1000) {
	    return function() {
	      const context = this;
	      const args = [].slice.call(arguments);
	      setTimeout(() => {
	        callback.apply(context, args)
	      }, delay)
	    }
	  };
	  ```
	- 當 closure 不斷重新觸發，清除既有的 `setTimeout`，並重新開始計時
	- ```javascript
	  function debounce(callback, delay = 1000) {
	    let timer;
	    return function() {
	      const context = this;
	      const args = [].slice.call(arguments);
	      if (timer) { clearTimeout(timer); }
	      timer = setTimeout(() => {
	        callback.apply(context, args)
	      }, delay)
	    }
	  };
	  ```
- ## Reference
	- [Debounce vs Throttle](https://redd.one/blog/debounce-vs-throttle)