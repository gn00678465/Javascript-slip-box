- ## config 設定檔路徑
	- 主要設定檔放置於 `/etc/nginx/nginx.conf`
	- 其他 domain 放置於 `/etc/nginx/conf.d/*.conf`
	- 再於主設定檔新增
		- ```plain
		  include /etc/nginx/conf.d/*.conf;
		  ```
- ## config 設定檔
	- ```plain
	  ```