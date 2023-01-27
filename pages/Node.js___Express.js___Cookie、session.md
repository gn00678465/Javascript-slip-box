category:: Programing
type:: Node.js
alias:: Cookie、session

- ## Cookie
	- 可存在 client 瀏覽器內，單一 value 的容量上限約 4k
	- 可於 client 或 Server 端刪除 修改
	- 以 name-value pair 為一組組成，多組須使用**分號**與**空格**相隔
	- |屬性|type|描述|
	  |--|--|--|
	  |HttpOnly|`boolean`|無法使用 Javascript 存取|
	  |Secure|`boolean`|只要網站開頭不是 https 開頭的網站都沒有辦法獲得 Cookie 中的資訊|
- ## session