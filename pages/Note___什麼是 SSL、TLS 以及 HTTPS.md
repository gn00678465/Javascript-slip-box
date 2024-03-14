category:: Note
type:: #Note
alias:: SSL、TLS 以及 HTTPS

- ## SSL
	- SSL 全名是 Secure Sockets Layer (安全通訊端層)，是一種標準的技術，用來保持網路連線安全，防止敏感資料被竊取或傳輸的資料被修改。此技術可使用加密演算法來混淆傳輸的資料，防止資料被竊取。
-
- ## TLS
	- TLS (Transport Layer Security, 傳輸層安全協議) 是 IETF 將 SSL 標準化，並將名稱改為 TLS.
-
- ## HTTPS
	- HTTPS (Hyper Text Transfer Protocol Secure, 超文字傳輸安全協定) 是一種安全的網路傳輸協議，經由 HTTP 進行通訊，但利用 SSL/TLS 來加密封包，保障資料傳輸的安全性及完整性。
-
- ## 產生 SSL/TLS 憑證
- ### 自行簽署憑證
	- 使用 triple DES 演算法加密，產生長度為 2048 bits 的 RSA key
	  logseq.order-list-type:: number
		- ```bash
		  openssl genrsa -des3 -out server.enc.key 2048
		  ```
	- 產生 csr file
	  logseq.order-list-type:: number
		- ```bash
		  openssl req -new -key server.enc.key -out server.csr
		  ```
	- 產生未加密的 key
	  logseq.order-list-type:: number
		- ```bash
		  openssl rsa -in server.enc.key -out server.key
		  ```
	- 自行簽屬憑證
	  logseq.order-list-type:: number
		- ```bash
		  openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
		  ```
- ### mkcert
	- [[certificate/mkcert]]
-
- ## Reference
	- [[Node.js] 使用 SSL/TLS 憑證](https://wshs0713.github.io/posts/819b05c6/)