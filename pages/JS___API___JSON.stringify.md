category:: Programing
type:: Javascript, API
alias:: JSON.stringify

- ```javascript
  JSON.stringify(value[, replace[, space]]);
  ```
- **Params**
	- `value`: 要轉換為 JSON string 的值，可為 object 或其他的值。
	- `replace`: 可以是一個函式也可以是一個陣列。
		- `Function`: 帶入兩個參數，key 和 value，被序列化的值皆經此 function 處理。
		- `Array`: 此 Array 內的屬性名才會被序列化。
		- `null | undefined`: 所有的屬性都會序列化。
	- `space`: 指定縮進的空白字串，用一美化輸出。
		- `n > 0 | n <= 10`: 要縮進的空白字串數。
		- `n < -1`: 沒有縮進。
		- `string`: 長度上限為 10 個字串值，超過取前 10，該字串作為空白填入。
		- `null | undefined`: 沒有縮進。
- **Return**
	- JSON string
- ## 特性
- 1.
	- `undefined`、`function`、`symbol` 於 `object` 內轉換會被忽略
	- `undefined`、`function`、`symbol` 於 `Array` 內轉換會替換成 `null`
	- `undefined`、`function`、`symbol` 單獨轉換會回傳 `undefined`
- 2. `new Number`、`new Boolean`、`new String` 轉換後會轉換為對應的原始值。
  3. 以 `symbol` 作為屬性的轉換會完全忽略，使用 `replace` 參數也無效。
  4. `NaN`、`Infinity`、`null` 轉換會替換成 `null`
  5.當轉換值內有 `toJSON` 方法，會自動調用此方法
  6. `Date` 內有內建 `toJSON` 方法，轉換會自動調用此方法，返回字串
  7. 無法處理遞迴資料結構(裡面包含了自己的參考), 會拋出錯誤 `Converting circular structure to JSON`
  8. 無法處理 JS 一些內建型別例如 `Map`, `Set`, `Date`, `RegExp`, `ArrayBuffer`
  9. 無法處理 [`BigInt`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/BigInt) 類型，會拋出錯誤 `TypeError: Do not know how to serialize a BigInt`