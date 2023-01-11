category:: Temp

- ## Unix timestamp
	- > 從 UTC + 0 的時區的 **1970-01-01 00:00:00** 開始，總共經過了多少毫秒
- ## 標準格式
	- ### ISO 8601
		- `YYYY-MM-DDTHH:mm:ssZ`
	- ### RFC 3339
		- [RFC 規則](https://www.rfc-editor.org/rfc/rfc3339#section-5.6)
		- `YYYY-MM-DDTHH:mm:ssZ` - 時區 UTC + 0:00 (Z 代表 UTC + 0)
			- 2023-01-11T04:00:00Z
		- `YYYY-MM-DDTHH:mm:ss+08:00` - 時區 UTC + 8:00 (Taiwan Standard Time)
			- 2023-01-11T12:00:00+08:00
- ## Reference
	- [淺談 JavaScript 中的時間與時區處理](https://blog.techbridge.cc/2020/12/26/javascript-date-time-and-timezone/)