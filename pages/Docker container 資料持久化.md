- ## 概述
- Docker 將資料儲存於 container 外的方法
	- ![](https://miro.medium.com/max/501/0*NP2huq9XtEMxn1YG.png)
	- Bind Mount: 資料存在 Filesystem 中。
	- Volume: 資料存在 Filesystem 內的 Docker Area 中。
	- Tmpfs Mount: 資料存放在記憶體中。
- 查看 Container 綁定的 Volume 或 Bind Mount 狀態
	- 使用 `docker inspect` 會有一個 Mount 的區塊，描述了資料綁定的細節。
- ## --mount 與 -v/ --volume
	- 建立 docker container 皆可以使用 `--mount` 或 `-v` 來綁定資料。
	- ```bash
	  -v, --volume list      Bind mount a volume
	      --mount mount      Attach a filesystem mount to the container
	  ```
- ## Volume
	- > Docker 用來存放持久化資料的空間。
	- ### 建立 Volume
		- ```bash
		  docker volume create [OPTIONS] [VOLUME]
		  
		  -d, --driver string   Specify volume driver name (default "local")
		      --label list      Set metadata for a volume
		  -o, --opt map         Set driver specific options (default map[])
		  ```
	- ### 綁定 Volume
		- ```bash
		  # -v
		  
		  # -
		  ```
- ## Bind Mount
- ## Tmpfs Mount
- ## Reference
- [Docker筆記 - 讓資料遠離Container，使用 Volume、Bind Mount 與 Tmpfs Mount](https://medium.com/alberthg-docker-notes/docker%E7%AD%86%E8%A8%98-%E8%AE%93%E8%B3%87%E6%96%99%E9%81%A0%E9%9B%A2container-%E4%BD%BF%E7%94%A8-volume-bind-mount-%E8%88%87-tmpfs-mount-6908da341d11)