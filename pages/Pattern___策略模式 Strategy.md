category:: Programming
type:: #Pattern
alias:: 策略模式 Strategy

- 定義：定義一系列演算法，將它們封裝起來，並使它們可以互相替換。
- 原則：將**不變的部分與變化的部分隔開**
- ## Example
	- ```typescript
	  type Strategy = [boolean, () => void]
	  
	  // 不變的
	  function execStrategy(strategy) {
	    [...strategy].some(([flag, action]) => {
	      if (flag) { action() }
	      return flag
	    })
	  }
	  
	  function useStrategy(type) {
	    // 變化的
	    const strategy: Array<Strategy> = [
	      [type === 'A', () => { /* do A */ }],
	      [type === 'B', () => { /* do B */ }],
	      [type === 'C', () => { /* do C */ }]
	    ];
	  
	    execStrategy(strategy);
	  
	  }
	  ```