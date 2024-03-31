category:: Programming
type:: #Javascript, #API
alias:: Array.prototype.flat

- > 將 Array 依照傳入的 depth level 進行攤平，並回傳新的 Array 。
- ```javascript
  [1, 2, 3, [4, [5]]].flat(depth);
  ```
- **Parameters**
	- `depth` **options**: Array 攤平的深度。預設為 1 。
- **Return**
	- 回傳一個新的已進行攤平後的 Array 。
- ## 特性
	- 會移除 Array 裡面的 empty slots
	- 使用於 `non-array Objects`，`flat` 會讀取當前 object `this` 的 `length` 屬性
		- 沒有 `length`: 回傳 `[]`
		- 遍歷整數 index 的所有元素，如元素不為陣列直接回傳元素，如為陣列根據 depth level 回傳攤平後的結果。
		- `Array.prototype.flat.call(arrayLike)`
		- ```javascript
		  const arrayLike = {
		    length: 3,
		    0: [1, 2],
		    // 不為 Array
		    1: { length: 2, 0: 3, 1: 4 },
		    2: 5,
		    a: 'a'
		  };
		  Array.prototype.flat.call(arrayLike);
		  // [1, 2, {0: 3, 1: 4, length: 2}, 5]
		  ```