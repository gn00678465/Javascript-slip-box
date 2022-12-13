- 定義：定義一系列演算法，將它們封裝起來，並使它們可以互相替換。
- 原則：將**不變的部分與變化的部分隔開**
- ## Example
	- ```typescript
	  // 變化的
	  const strategy: Array<Array<boolean, () => void>> = [
	    [type === 'A', () => { //do A }],
	    [type === 'B', () => { //do B }],
	    [type === 'C', () => { //do C }]
	  ]
	  
	  // 不變的
	  function execStrategy(type, strategy) {
	    [...strategy].some(([flag, action]) => {
	      if (flag) { action() }
	      return flag
	    })
	  }
	  ```