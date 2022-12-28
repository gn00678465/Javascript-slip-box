- ## config 設定檔路徑
	- 主要設定檔放置於 `/etc/nginx/nginx.conf`
	- 其他 domain 放置於 `/etc/nginx/conf.d/*.conf`
	- 再於主設定檔新增
		- ```plain
		  include /etc/nginx/conf.d/*.conf;
		  ```
- ## config 設定檔
	- ```plain
	  upstream api {
	      server localhost:5000;
	      server localhost:5001;
	  }
	  
	  server {
	      listen 80;
	      listen [::]:80;
	      server_name SERVER_IP;
	      root /home/ryan;
	  
	      proxy_set_header Host $http_host;
	      proxy_set_header X-Real-IP $remote_addr;
	      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	  
	      location / {
	              proxy_pass http://api/;
	      }
	  }
	  ```
	- ### upstream
		- > upstream block 定義了要將 request proxy 過去的應用。
	- ### server
		- > server block 定義 proxy server 的相關設定。
			- 要監聽的 port
			- 規定那些 domain 或 Ip 的 request 會被 nginx server 處理
	- ### location
		- > 設定不同的 path 要對應到的設定
	- ### https
		- > 將 http 變為 https，必須搭配 **SSL certificate**
		- 使用 [[certbot]] 取得來自 Let’s Encrypt 的免費憑證（有效期限 90 天）
- ## Reference
	- [[基礎觀念系列] Web Server & Nginx — (2)](https://medium.com/starbugs/web-server-nginx-2-bc41c6268646)
	- [NGINXConfig](https://www.digitalocean.com/community/tools/nginx)