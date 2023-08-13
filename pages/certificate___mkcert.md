category:: Environment
type:: Certificate
alias:: mkcert

- ## 安裝
	- 安裝 **mkcert**
	  logseq.order-list-type:: number
	- 輸入指令 `mkcert -install`
	  logseq.order-list-type:: number
		- 建立一個本地的憑證頒發機構 (Certificate authority)
- ## 建立憑證
	- ```bash
	  mkcert localhost
	  ```
	- **新增多網域憑證**
	- ```bash
	  mkcert <subdoamin.domain> <domain_2> <domain_3> ...
	  
	  mkcert example.com localhost 127.0.0.1 ::1
	  ```
	- **新增 wildcard 憑證**
	- ```bash
	  mkcert "*.domain"
	  ```
- ## Reference
	- [FiloSottile/mkcert](https://github.com/FiloSottile/mkcert)