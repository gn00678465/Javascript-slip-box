category:: Note
type:: #TOML, #Note
alias:: TOML 語法

- > 副檔名為 `.toml`
- ## 語法
	- key = "value"
	- [節名]
	- #: 注釋
- ## 資料類型
	- > 支援以下：字串、整數、浮點型、布林型、日期時間、陣列和表格
	- **布林型**: 永遠小寫 `true/false`
	- **Table 表格**
		- > Tables (also known as hash tables or dictionaries) are collections of key/value pairs.
		  表格（也叫雜湊表或字典）是鍵值對的集合
		- 建立一個 table，直到下一個 table 或 EOF 之前，皆是這個 table 的鍵值對
		  logseq.order-list-type:: number
		- 鍵值對是無序的
		  logseq.order-list-type:: number
		- 巢狀表格的表格名稱中使用`.`
		  logseq.order-list-type:: number
		  collapsed:: true
			- ```toml
			  [dog."tater.man"]
			  type.name = "pug"
			  
			  # { "dog": { "tater.man": { "type": { "name": "pug" } } } }
			  ```
		- 可以不用宣告所有的父表
		  logseq.order-list-type:: number
		  collapsed:: true
			- ```toml
			  [x.y.z.w] # { "X", { "y": { "z": { "w": {} } } } }
			  
			  [x] # defining a super-table afterward is ok
			  ```
		- 空表是允許的，其中沒有鍵值對
		  logseq.order-list-type:: number
		- 不可以重複定義表格，或是 Key
		  logseq.order-list-type:: number
	- **Array of Tables 表格陣列**
- ## Reference
	- [TOML](https://toml.io/en/)