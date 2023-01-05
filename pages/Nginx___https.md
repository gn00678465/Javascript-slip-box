nginx:: https
title:: Nginx/https

- > 將 http 變為 https，必須搭配 **SSL certificate**
- 使用 [[certificate/certbot]] 取得來自 Let’s Encrypt 的免費憑證（有效期限 90 天）
- ## 設定
	- ```plain
	  # 將 http 導向到 https
	  server {
	      listen 80;
	      listen [::]:80;
	      server_name localhost;
	      return 301 https://localhost$request_uri;
	  }
	  
	  server {
	    listen *:443 ssl http2;
	    server_name  localhost;
	    root /var/www/html;
	    index index.html;
	    # 憑證檔
	    ssl_certificate /cert/cert.pem; 
	    ssl_certificate_key /cert/key.pem;
	    
	    # 代理請求 80
	      location / {
	          proxy_pass http://127.0.0.1;
	          proxy_set_header Host $proxy_host;
	          proxy_set_header X-Real-IP $remote_addr;
	          proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	          proxy_set_header Via "nginx";
	      }
	  }
	  ```
	- `ssl_certificate`: 憑證檔對應，依照環境修改設定
- ## Reference
	- [Nginx HTTP重定向HTTPS](https://www.myfreax.com/redirect-http-to-https-in-nginx/)