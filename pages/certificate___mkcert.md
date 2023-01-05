category:: Environment
type:: certificate
alias:: mkcert
title:: certificate/mkcert

- ## 建立憑證
	- ```bash
	  docker run -d -e domain=[DOMAIN] --name mkcert \
	  -v [PATH]:/root/.local/share/mkcert \
	  vishnunair/docker-mkcert
	  ```
	- `-e`: [DOMAIN] 取代要產生憑證的 domain, 多個 domain 以 **,** 分隔
	- `-v`: [PATH] 產生憑證的路徑
- ## Reference
	- [FiloSottile/mkcert](https://github.com/FiloSottile/mkcert)