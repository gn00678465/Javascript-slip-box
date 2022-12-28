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
	      root /var/www/html;
	  
	      proxy_set_header Host $http_host;
	      proxy_set_header X-Real-IP $remote_addr;
	      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	  
	      location / {
	              proxy_pass http://api/;
	      }
	  }
	  ```
	- {{embed [[upstream]]}}
	- {{embed [[server]]}}
	- {{embed [[location]]}}
	- {{embed [[https]]}}
- ## Reference
	- [[基礎觀念系列] Web Server & Nginx — (2)](https://medium.com/starbugs/web-server-nginx-2-bc41c6268646)
	- [NGINXConfig](https://www.digitalocean.com/community/tools/nginx)