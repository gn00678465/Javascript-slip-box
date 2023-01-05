category:: Environment
type:: certificate
alias

- ## 安裝 certbot
	- 參考 [Certbot 官方網站](https://certbot.eff.org/) 的指引。
		- **My HTTP website is running  on**
- ## 手動建立
	- ```bash
	  certbot certonly --manual -m [youremail@example.com] -d [DOMAIN_NAME] -d [DOMAIN_NAME_2]
	  ```
	- `--manual`: 手動建立，接下來的操作都將會以「互動式」的方式完成設定。
- ## 自動建立
	- ```bash
	  certbot certonly --standalong -d [DOMAIN_NAME] -d [DOMAIN_NAME_2]
	  ```
- ## Reference
	- [Certbot 官方網站](https://certbot.eff.org/)
	- [如何使用 Certbot 命令列工具建立免費的 TLS/SSL 頂層網域憑證](https://blog.miniasp.com/post/2021/02/11/Create-SSL-TLS-certificates-from-LetsEncrypt-using-Certbot)